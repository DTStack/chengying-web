---
title: 简介
sidebar_position: 1
---

[![License](https://img.shields.io/badge/license-Apache%202-4EB1BA.svg)](https://www.apache.org/licenses/LICENSE-2.0.html)

# 简介

承影是一个全自动化全生命周期的运维管家，提供大数据产品的一站式部署、运维、监控服务，其可实现产品部署、产品升级、版本回滚、扩缩节点、日志诊断、集群监控、实时告警等功能，致力于最大化节省运维成本，降低线上故障率与运维难度，为客户提供安全稳定的产品部署与监控。

## 系统架构

![q1](/img/intro/img.png)

产品部署之前需添加主机、及上传安装包，主机和安装包通过nginx进行服务转发，matinx是主程序服务，其中包含schema安装包文件解析，orchestrate组件依赖关系处理，instance exec执行引擎3部分。除此之外，promethus进行集群监控，以及通过grafana进行仪表盘展现，MySQL存储Easy Manager相关数据。Easy Manager所有的组件通过easyagent server服务与外部实体连接、调度。

![q1](/img/intro/img_1.png)

Easyagent Server通过标准的GPRC协议与sidecar进行双向通讯，通过GRPC全双工通讯，客户端网络环境不需要开监听端口，所有控制指令进行实时传输。Sidecar进行不同agent的服务管理，如kafaka、ES等服务，可实现对agent服务的cgroup分组以及tc控制，控制主机资源使用、上报监控资源使用情况，以及进行健康检查。同时Easyagent Server抽象出七大REST接口，安装、启动、停止、更新、配置修改、卸载、执行等与上层应用进行交互，使agent类别和功能可轻松无限扩展。
