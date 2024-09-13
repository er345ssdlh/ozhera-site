---
outline: deep
---

# 规范指南

## 提交pr规范

### 1.创建 Issues

#### （1）进入 Issues 的主页面
![图片](/images/about/coc/pr1.png)

#### （2）点击 New issue 绿色按钮，就可以去创建
![图片](/images/about/coc/pr2.png)
进入到如下边的页面
![图片](/images/about/coc/pr3.png)

#### （3）给予受托人（就是把这个需求给某个人来解决）(选填)
![图片](/images/about/coc/pr4.png)

#### （4）设置标签（标明是什么类型的需求）
一共有9大标签，可以有多个选择，但是一般情况，选一个。如果是bug的选择bug
![图片](/images/about/coc/pr5.png)

#### （5）选完标签，去写Title（标题）
标题是有格式要求，必须采取 [标签] 文字描述 的格式
比如我标签是bug,则我的标题是：[bug] 点击获取验证码的时候有问题
注意：[ ] 后面要有空格
![图片](/images/about/coc/pr6.png)

#### （6）编写内容
将标题进行拓展，把问题说清楚
可以是文字，可以是图片（图片复制进来就可以）
还可以是多个需求混在一起的时候，需要多个多选框，则需要这么写：(可选)
- [ ] 输入框 boolean
- [ ] 选择框 boolean
- [ ] 选择框 any
- [ ] 地址选择器 List
- [ ] 地址选择器 any
- [ ] 多选框 any
- [ ] 时间选择框 ‘请选择时间’
- [ ] 圆形单选框 any
- [ ] 基础选择框 any
![图片](/images/about/coc/pr7.png)

### 2.创建pr

#### (1).从开源项目fork项目到自己的远程仓库
![图片](/images/about/coc/pr8.png)

#### (2).在自己的仓库中clone项目到本地
![图片](/images/about/coc/pr9.png)

#### (3).记得定期同步远程代码到本地仓库
![图片](/images/about/coc/pr10.png)

#### (4).代码的commit message 后加上 （#issueId）
![图片](/images/about/coc/pr11.png)

#### (5).本地修改代码提交到远程仓库，然后点击pull request去创建pr
![图片](/images/about/coc/pr12.png)

#### (6).创建正确的pr
![图片](/images/about/coc/pr13.png)
在pr请求的时候的内容里面填写 #702,也可以填 close #702,这样当你的pr被合并后，issue也会被标记为closed状态
#702即为每个issue的编号，当你创建完issue后可以在url中看到，如
![图片](/images/about/coc/pr14.png)

### 3.关闭Issues
当你的pr被合并后，如果pr的内容中有close #issueId ，对应的issue也会被标记为closed状态
![图片](/images/about/coc/pr15.png)
![图片](/images/about/coc/pr16.png)
![图片](/images/about/coc/pr17.png)