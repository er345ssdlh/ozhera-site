#!groovy
/*
 * Licensed to the Apache Software Foundation (ASF) under one or more
 * contributor license agreements.  See the NOTICE file distributed with
 * this work for additional information regarding copyright ownership.
 * The ASF licenses this file to You under the Apache License, Version 2.0
 * (the "License"); you may not use this file except in compliance with
 * the License.  You may obtain a copy of the License at
 *
 *      https://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS,
 * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 */

pipeline {
  agent {
    // https://cwiki.apache.org/confluence/display/INFRA/ci-builds.apache.org
    label 'git-websites'
  }

  environment {
    DEPLOY_BRANCH = "${env.BRANCH_NAME == 'main' ? 'asf-site' : "${env.BRANCH_NAME}-staging"}"
    NODE_VERSION = '18.16.1' // Adjust to your desired Node.js version
    VITEPRESS_VERSION = '0.27.0'
  }

  stages {
    stage('Prepare') {
      steps {
        script {
          env.LAST_SHA = sh(script: 'git log -n 1 --pretty=format:\'%H\'', returnStdout: true).trim()
          env.NVM_DIR = sh(script: 'which nvm', returnStdout: true).trim()
          sh "echo NVM path: '${env.NVM_DIR}'"

          // Install Node.js if not present
          if (sh(script: "${env.NVM_DIR} version | grep -q ${env.NODE_VERSION}", returnStatus: true).trim() != 0) {
            sh "${env.NVM_DIR} install ${env.NODE_VERSION}"
          }
          sh "${env.NVM_DIR} use ${env.NODE_VERSION}"
          sh "echo Node.js version: $(node -v)"
        }
      }
    }
    stage('Install Dependencies') {
      steps {
        script {
          // Install VitePress
          sh "npm install -g vitepress@${env.VITEPRESS_VERSION}"
        }
      }
    }
    stage('Build') {
      steps {
        script {
          // Build the VitePress site
          sh "vitepress build"
        }
      }
    }
    stage('Deploy') {
      when {
        not {
          branch '**/*-staging'
        }
        anyOf {
          branch 'main'
          not {
            branch '*'
          }
        }
      }
      steps {
        script {
          // Checkout branch with generated content, creating it if necessary
          sh """
            if git checkout ${DEPLOY_BRANCH}
            then
              git pull origin ${DEPLOY_BRANCH}
            else
              echo "branch ${DEPLOY_BRANCH} is new; create basic site"
              git checkout --orphan ${DEPLOY_BRANCH} -f
              git rm -rf .
              # assume we have an asf.yaml file
              git checkout origin/${BRANCH_NAME} -- .asf.yaml
              git add .asf.yaml -f
            fi
          """

          // Remove the content of the target branch and replace it with the content of the temp folder
          sh """
            cp -rT ${WORKSPACE}/.vitepress/dist/* ${WORKSPACE}/content
          """

          // Commit the changes to the target branch
          env.COMMIT_MESSAGE1 = "Updated ${DEPLOY_BRANCH} from ${BRANCH_NAME} at ${env.LAST_SHA}"
          env.COMMIT_MESSAGE2 = "Built from ${BUILD_URL}"
          sh """
            git add -A
            git commit -m "${env.COMMIT_MESSAGE1}" -m "${env.COMMIT_MESSAGE2}" | true
          """

          // Push the generated content for deployment
          sh "git push -u origin ${DEPLOY_BRANCH}"
        }
      }
    }
  }

  post {
    always {
      script {
        sh """
          rm -rf dist
        """
      }
      deleteDir() /* clean up our workspace */
    }

    // If the build failed, send an email to the list.
    failure {
      script {
        if (env.BRANCH_NAME == 'main') {
          emailext(
            to: "dev@community.apache.org",
            recipientProviders: [[$class: 'DevelopersRecipientProvider']],
            from: "Jenkins <jenkins@ci-builds.apache.org>",
            subject: "[website] Jenkins job ${env.JOB_NAME}#${env.BUILD_NUMBER} failed",
            body: """
There is a build failure in ${env.JOB_NAME}.

Build: ${env.BUILD_URL}
"""
          )
        }
      }
    }

    // Send an email, if the last build was not successful and this one is.
    fixed {
      script {
        if (env.BRANCH_NAME == 'main') {
          emailext(
            to: "dev@community.apache.org",
            recipientProviders: [[$class: 'DevelopersRecipientProvider']],
            from: 'Jenkins <jenkins@ci-builds.apache.org>',
            subject: "[website] Jenkins job ${env.JOB_NAME}#${env.BUILD_NUMBER} back to normal",
            body: """
The build for ${env.JOB_NAME} completed successfully and is back to normal.

Build: ${env.BUILD_URL}
"""
          )
        }
      }
    }
  }
}
