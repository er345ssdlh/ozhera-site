---
# https://vitepress.dev/reference/default-theme-home-page
layout: home
title: Apache OzHera(Incubating) - Application Performance Monitoring (APM)
ozHera:
  title: Apache OzHera(Incubating)
  desc: Apache OzHera(Incubating) is an Application Performance Monitoring (APM) platform designed for the cloud-native era. It revolves around applications and integrates capabilities such as metric monitoring, distributed tracing, logging, and alerting. The platform's mission is to enhance the online stability of applications and enable businesses to detect and locate issues within 1 minute and 5 minutes, respectively, when problems occur.
  image:
    src: /images/architecture.png
    alt: architecture
  actions:
    - theme: brand
      text: Quick Start
      link: /en/guide/quick-start.md
features:
  title: Feature List
  items:
    - title: Embrace Cloud-Native
      details: Apache OzHera(Incubating) follows the Opentracing standard and integrates with various open-source stars like OpenTelemetry, Grafana, Prometheus, Elasticsearch (ES), CAdvisor, and more.
      icon:
        src: /images/icon/feature-cloudNative.svg
        alt: architecture
    - title: Precise Alerting
      details: Based on RPC and custom business error code parsing, Apache OzHera(Incubating) extracts business availability metrics (business availability = 1 - "abnormal" request count / total request count). This allows for accurate representation of the system's true health status and eliminates the interference of ineffective alerts.
      icon:
        src: /images/icon/feature-preciseAlerting.svg
        alt: architecture
    - title: Swift Issue Resolution
      details: Based on traceId, Apache OzHera(Incubating) establishes a closed-loop linkage between alerts, metrics, distributed tracing, and logs, significantly improving user issue resolution efficiency.
      icon:
        src: /images/icon/feature-architecture.svg
        alt: architecture
    - title: Cost-Effective
      details: Storage costs are less than one in a thousand, meeting 99.9% of tracing needs.
      icon:
        src: /images/icon/feature-costEffective.svg
        alt: architecture
    - title: Enterprise-Grade Observability Product
      details: Apache OzHera(Incubating) features comprehensive account, permission, application management, and message notification mechanisms. Core linkage modules are decoupled, ensuring minimal intrusion into business systems. It has undergone numerous stress tests at Xiaomi, handling over 1 PB of raw data daily.
      icon:
        src: /images/icon/feature-observability.svg
        alt: architecture
    - title: Artificial Intelligence
      details: The cutting-edge artificial intelligence technology has been introduced, using AI tools to help you quickly pinpoint issues, analyze the causes in-depth, and provide personalized repair suggestions. Let intelligence lead your application monitoring, achieving intelligent management and optimization.
      icon:
        src: /images/icon/feature-ai.svg
        alt: architecture
---
