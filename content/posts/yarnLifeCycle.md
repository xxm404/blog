---
title: "YarnLifeCycle"
date: 2019-12-19T16:31:32+08:00
draft: true
toc: false
images:
tags: 
  - untagged
---

## Yarn 生命周期
https://hadoop.apache.org/docs/current/hadoop-yarn/hadoop-yarn-site/YARN.html

![image.png](https://i.loli.net/2019/12/18/xNLOGZzpWwk8VJn.png)

> The ResourceManager has two main components: Scheduler and ApplicationsManager.

1. ResourceManager

   > The ResourceManager is the ultimate authority that arbitrates resources among all the applications in the system.

`ResourseManager` 管理集群资源的分配，由`Scheduler`和`ApplicationsManager`组成

2. NodeManager

   > The NodeManager is the per-machine framework agent who is responsible for containers, monitoring their resource usage (cpu, memory, disk, network) and reporting the same to the ResourceManager/Scheduler.

`NodeManager` 以 agent 的方式运行在集群中，负责监控节点的资源使用情况，并上报给 `ResourceManager/Scheduler`

3. ApplicationMaster

   > The per-application ApplicationMaster is, in effect, a framework specific library and is tasked with negotiating resources from the ResourceManager and working with the NodeManager(s) to execute and monitor the tasks.

请求，启动，监控用户提交应用程序资源的主要容器，可以理解为用户提交的代码的主程序`SparkContext`,负责申请应用程序所需资源等

4. 资源调度全流程







### References

> 1. https://hadoop.apache.org/docs/current/hadoop-yarn/hadoop-yarn-site/YARN.html
>
> 2. https://stackoverflow.com/questions/50402020/spark-driver-memory-and-application-master-memory
>
> 3. https://stackoverflow.com/questions/30967247/difference-between-application-manager-and-application-master-in-yarn
> 4. https://blog.csdn.net/qq_26442553/article/details/78699759

