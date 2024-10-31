---
# https://vitepress.dev/reference/default-theme-home-page
layout: home
title: Apache OzHera(Incubating)- 云原生时代的应用观测平台(APM)
ozHera:
  title: Apache OzHera(Incubating)
  desc: Apache OzHera(Incubating)是一个云原生时代的应用观测平台(APM)，以应用为核心，集指标监控、链路追踪、日志、报警等能力于一身。平台使命是提升应用线上稳定性，帮助业务在遇到故障时能做到1分钟发现、5分钟定位。
  image:
    src: /images/architecture.png
    alt: architecture
  actions:
    - theme: brand
      text: 快速开始
      link: /zh/guide/quick-start.md
features:
  title: 特色功能
  items:
    - title: 拥抱云原生
      details: 遵循Opentracing标准，集成OpenTelemetry、Grafana、Prometheus、ES、CAdvisor等多个开源明星产品
      icon:
        src: /images/icon/feature-cloudNative.svg
        alt: architecture
    - title: 报警准
      details: 基于RPC及业务自定义错误码解析，提取出业务可用性指标（业务可用性 = 1 - "异常"请求数/总请求数）。通过一个指标就能够很准确的表达系统真实的健康状况，告别无效告警的干扰。
      icon:
        src: /images/icon/feature-preciseAlerting.svg
        alt: architecture
    - title: 定位快
      details: 基于traceId打通报警->指标->链路->日志的闭环联动，大幅提升用户定位问题效率
      icon:
        src: /images/icon/feature-architecture.svg
        alt: architecture
    - title: 经济
      details: 小于千分之一存储成本，满足99.9%的tracing诉求
      icon:
        src: /images/icon/feature-costEffective.svg
        alt: architecture
    - title: 企业级可观测产品
      details: 完善的账号、权限、应用管理、消息触达机制；核心链路模块解耦、同时对业务系统做到最低侵入；在小米内部经历数次大促考验，每天处理原始数据量>1PB。
      icon:
        src: /images/icon/feature-observability.svg
        alt: architecture
    - title: 人工智能
      details: 引入了前沿的人工智能技术，利用AI工具帮助您快速定位问题、深入分析原因，并提供个性化的修复建议。让智能化引领您的应用观测，实现智能化的管理和优化。
      icon:
        src: /images/icon/feature-ai.svg
        alt: architecture
---
