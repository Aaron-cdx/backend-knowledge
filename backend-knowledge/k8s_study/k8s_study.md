# k8s学习
> k8s学习，拓展自己的知识面！2021-11-28 深圳

## 1. 主要学习内容
* 第一部分: k8s的基本概念
* 第二部分: 搭建k8s集群
    * 基于集群部署工具kubeadm
    * 基于二进制包的方式
* 第三部分: k8s核心技术
    * Pod
    * 控制器
    * 存储
    * Service
    * 调度器
    * 安全机制RBAC
    * 包管理工具Helm等
* 第四部分: 部署统一日志管理
* 第五部分: 部署性能监控平台
* 第六部分: 搭建高可用的k8s集群
* 第七部分: K8S集群部署项目

## 2. k8s的基本概念
### 2.1 K8S概述和特征
**概述**
* k8s是谷歌在2014年开源的容器化集群管理系统
* 使用k8s进行容器化应用部署
* 使用k8s利于应用扩展
* k8s目标实施让部署容器化应用更加简洁和高效

**特征**
* 
### 2.2 K8S架构组件
**master组件**
* apiserver
    * 集群统一入口，以restful方式，交给etcd存储
* scheduler
    * 节点调度，选择node节点应用部署
* controller-manager
    * 处理集群中常规后台任务，一个资源的对应一个控制器
* etcd
    * 存储系统，用于保存集群相关的数据

**node组件**
* kubelet
    * master排到node节点代表，管理本机容器
* kube-proxy
    * 提供网络代理，负载均衡等操作


### 2.3 K8S核心概念
Pod/Controller/Service

Pod
* 最小的部署单元
* 一组容器的集合
* 共享网络
* 生命周期是短暂的

Controller
* 确保预期的pod副本数量
* 无状态应用部署(没有网络存储的相关要求)
* 有状态应用部署(有关于网络存储的相关要求)
* 确保所有的node运行同一个pod
* 一次性任务和定时任务

Service
* 定义一组Pod的访问规则

