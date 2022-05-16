---
title: 监控告警
sidebar_position: 3
---

[![License](https://img.shields.io/badge/license-Apache%202-4EB1BA.svg)](https://www.apache.org/licenses/LICENSE-2.0.html)

### 仪表盘
仪表盘用于展示集群各服务、主机的监控趋势，快速掌握集群运行的稳定性以及异常情况，及时运维。
#### 创建仪表盘
步骤一：创建仪表盘，填写仪表盘所属文件夹、名称、标签

![q1](/img/monitor/newBoard.png)
:::tip
仪表盘标签一般需要写产品名称、组件名称、服务名称，便于用标签筛选仪表盘。
:::

步骤二：在仪表盘中添加Panel
![q2](/img/monitor/addPanel.png)
仪表盘的Panel包含趋势图、单个指标、表格、文本、热点图、告警、饼图等，用户可根据需要自行选择。

步骤三：进入Panel编辑页面
![q3](/img/monitor/editPanel.png)
- 设置Panel基本信息
![q4](/img/monitor/panelBasic.png)
- 设置Panel查询条件
![q5](/img/monitor/panelCondition.png)
DataSource选择prometheus，下方写查询条件，按照Grafana的标准语句查询。
- 设置Panel坐标轴
![q6](/img/monitor/dimension.png)
- 设置Panel图例
![q7](/img/monitor/legend.png)
- 设置数据显示
![q8](/img/monitor/display.png)

#### 导入仪表盘
可通过JSON文件和上传仪表盘文件两种方式上传已有仪表盘。 
既然可以导入仪表盘，同样，仪表盘支持复制JSON语句，以及导出仪表盘。
![q9](/img/monitor/importDashboard.png)

### 告警

