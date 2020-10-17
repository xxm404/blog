---
title: "名词解释"
date: 2019-08-09T16:52:40+08:00
draft: false
toc: true
images:
tags: 
  - wiki
---

### common

- 幂等性

  ```php
  在数学领域指的是，f(x) = f(f(x)) 的数学性质，在编程领域，则指的是对同一个系统，使用同样的条件，一次请求和重复多次请求对被调用方的影响是一致的
  ```

- at least once

  ```php
  数据传输过程中，接收端至少会正确收到一次，保证交付，但可能出现重复
  ```

- at most once

  ```php
  数据传输过程中，接收端最多会正确收到一次，不保证交付，不会出现重复收到同一条数据的情况，但可能会出现数据丢失
  ```

- exactly once

  ```php
  数据传输过程中，接收端恰好会收到一次，是最理想的状态
  ```

### 大数据处理 & 实时计算

- EventTime

```php
指每个单独事件在其设备上发生的事件
ex: 收集嵌入式系统的日志，日志产生于嵌入式设备，则 EventTime 为日志在此设备上产生的事件
```

- ProcessingTime

```php
执行相应操作系统的系统时间
ex: 收集嵌入式系统的日志，日志产生于嵌入式设备，则 ProcessingTime 为日志传输到收集系统时，此手机服务的系统时间
```

- ETL

  ```
  Extract-Transform-Load 的缩写，用来描述将数据从来源端经过萃取、转置、加载至目的端的过程。
  ```

- CDC

  ```
  Change data capture 修改改数据捕获，
  ```

  

### DEVOPS

- 蓝绿部署（Blue/Green Deployment）

  ```
  在不停止老版本（v1）的情况下，部署新版本（v2）进行测试。确认新版本无误后，切到新版本。蓝绿部署需要 double 的机器资源，流量切换为全量切换。
  ```

- 灰度部署/金丝雀部署（Canary Deployment）

  ```
  在黑与白之间平滑过渡的一种发布方式，A/B Test 就是一种灰度发布，流量切换由小到大，最终完全切换。
  ```

- SLA (Service Level Agreement)

  ```
  The agreement you make with your clients or users
  服务级别协议，是服务提供商和客户之间关于可衡量指标（如停机时间，响应能力和责任）的协议
  ```

- SLO (Service Level Objectives)

  ```
  服务级别目标，是 SLA 中有关特定指标（如停机时间或响应时间）的协议，SLOs 就是提供商向客户做出的承诺
  ```

- SLI (Service Level Indicators)

  ```
  服务级别指标，是测量 SLO 合规性的指标，如果 SLA 指定系统在 99.95% 时间可用，则 SLO 的可用时间就是 99.95%，SLI 将满足或超过该承诺
  ```

  