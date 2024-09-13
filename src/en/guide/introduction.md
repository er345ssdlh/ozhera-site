# OzHera

## What is OzHera

OzHera is an Application Performance Monitoring (APM) platform designed for the cloud-native era. It revolves around applications and integrates capabilities such as metric monitoring, distributed tracing, logging, and alerting. The platform's mission is to enhance the online stability of applications and enable businesses to detect and locate issues within 1 minute and 5 minutes, respectively, when problems occur.

## Architecture

![ozhera](/images/architecture.png)

## Features {#ozhera-features}

- <font color="red">Cloud-Native Embrace</font>
    - OzHera follows the Opentracing standard and integrates with various open-source stars like OpenTelemetry, Grafana, Prometheus, Elasticsearch (ES), CAdvisor, and more. Additionally, OzHera offers deep integration with Kubernetes (K8s) and provides a one-click operator deployment for K8s environments.
- <font color="red">Precise Alerting: Business Availability Metrics</font>
    - Business availability is calculated as 1 - "abnormal" requests / total requests. The definition of "abnormal" requests includes exceptions at the RPC level (e.g., HTTP 5xx) and exceptions encapsulated with business error codes. OzHera provides a standardized two-level error code system, supporting both default and custom business error codes. This allows for accurate representation of the system's true health status, eliminating the interference of ineffective alerts.
- <font color="red">Swift Issue Resolution: Metrics-Tracing-Logging Integration</font>
    - OzHera establishes a closed-loop linkage between alerts, metrics, distributed tracing, and logs using trace IDs. Starting from an alert card, users can quickly view the relevant traces and log information with a single click, significantly improving issue resolution efficiency.
- <font color="red">Cost-Effective: Storage Costs Less Than One in a Thousand, Meeting 99.9% of Tracing Needs</font>
    - Hera identifies exceptional calls (error spans, abnormal business error codes, error logs, spans exceeding 1 second, etc.) and ensures the retention of entire exceptional trace call chains. For normal traces, a default one in ten thousand (customizable) random sampling strategy is employed.
- <font color="red">Enterprise-Grade Observability Product</font>
    - OzHera features a comprehensive account, permission, and application management mechanism, facilitating rapid adoption within enterprises and integration with their internal account and application deployment systems. It also supports seamless integration with enterprise office software for alert notifications. The core linkage modules are decoupled, ensuring minimal intrusion into business systems. OzHera has undergone numerous stress tests at Xiaomi, handling over 1 PB of raw data daily.

## User List

If you are using OzHera and find it beneficial, or if you wish to contribute code, please add your company to the user list to help us understand your needs.

|![xiao mi](/images/userlist/mi.png)|![auchosaur games](/images/userlist/auchosaur_games.png)|![lingdong](/images/userlist/lingdong.png)|![airstar](/images/userlist/airstar.png)|
| :---: | :---: | :---: | :---: |
