# OzHera

## OzHera是什么

OzHera是一个云原生时代的应用观测平台(APM)，以应用为核心，集指标监控、链路追踪、日志、报警等能力于一身。平台使命是提升应用线上稳定性，帮助业务在遇到故障时能做到1分钟发现、5分钟定位。

## 架构

![ozhera](/images/architecture.png)

## 特性 {#ozhera-features}

- <font color="red">拥抱云原生</font>
  - 遵循Opentracing标准，集成OpenTelemetry、Grafana、Prometheus、ES、CAdvisor等多个开源明星产品; 同时OzHera深度适配K8S，提供一键在K8S部署的operator.
- <font color="red">报警准：业务可用性指标</font>
  - 业务可用性 = 1 - "异常"请求数/总请求数。"异常"请求的定义如下：包含为RPC层面的异常(比如HTTP 5xx)、及业务错误码封装的异常，我们内置了一套两层错误码规范也支持业务自定义，这样我们通过一个指标就能够很准确的表达系统真实的健康状况，从此告别无效告警的干扰。
- <font color="red">定位快：metrics-tracing-logging联动</font>
  - 基于traceId打通报警->指标->链路->日志的闭环联动，从报警卡片触达用户开始，用户直接点击就能够快速查看到本次报警相关的链路及日志情况，大幅提升用户定位问题效率
- <font color="red">经济：小于千分之一存储成本，满足99.9%的tracing诉求</font>
  - hera做到对异常调用(error span、异常的业务错误码、error 日志、单次span耗时超过1秒等)的识别，并保证异常trace整个调用链路数据的保留；对于正常的trace我们采用默认万分之一(可自定义)随机抽样策略。
- <font color="red">企业级可观测产品</font>
  - 完善的账号、权限、应用管理机制，方便用户在企业内部快速落地并打通企业自身的账号、应用部署系统等，还可快速对接企业办公软件实现告警触达；核心链路模块解耦、同时对业务系统做到最低侵入；在小米内部经历数次大促考验，每天处理原始数据量>1PB。


## 用户列表

如果您正在使用OzHera，并且认为它对您有所帮助，或者您希望为其贡献代码，请将您的公司添加到用户列表中，以便让我们了解您的需求。

|![xiao mi](/images/userlist/mi.png)|![auchosaur games](/images/userlist/auchosaur_games.png)|![lingdong](/images/userlist/lingdong.png)|![airstar](/images/userlist/airstar.png)|
| :---: | :---: | :---: | :---: |
