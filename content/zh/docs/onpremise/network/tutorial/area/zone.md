---
title: "可用区"
weight: 2
description: >
    可用区代表区域内的数据中心名称。
---

可用区代表区域内的数据中心名称。

**可用区来源**

- 本地IDC：在部署云管平台过程中会设置本地IDC的区域和可用区信息，部署完成后只支持添加可用区。
- 私有云：同步已连接私有云账号上的区域和可用区信息。

## 新建可用区

该功能用于在指定区域中创建可用区。

1. 在可用区页面，单击列表上方 **_"新建"_** 按钮，弹出新建可用区对话框。
2. 设置名称、区域以及位置，单击 **_"确定"_** 按钮。

## 删除可用区

该功能用于删除可用区，当可用区下存在宿主机或物理机时不可删除。

**单个删除**

1. 在可用区页面，单击可用区右侧操作列 **_"删除"_** 按钮，弹出操作确认对话框。
2. 单击 **_"确定"_** 按钮，完成操作。

**批量删除**

1. 在可用区列表中选择一个或多个可用区，单击 **_"删除"_** 按钮，弹出操作确认对话框。
2. 单击 **_"确定"_** 按钮，完成操作。

## 查看可用区详情

该功能用于查看可用区的详细信息。

1. 在可用区页面，单击可用区名称项，进入可用区详情页面。
2. 查看以下信息。
    - 基本信息：包括云上ID、ID、名称、状态、域、项目、区域、物理机（数量）、可用物理机、宿主机（数量）、可用宿主机、存储（数量）、二层网络（数量）、IP子网（数量）、创建时间、更新时间、备注。
    - 其他信息：包括位置。

## 查看宿主机信息

该功能用于查看可用区下的宿主机信息。

1. 在可用区详情页面，单击“宿主机”页签，进入宿主机页面。
2. 查看宿主机信息，包括名称、启用、状态、服务、IP、平台、区域信息。


## 查看资源统计信息

该功能用于查看可用区下的资源统计信息。

1. 在可用区详情页面，单击“资源统计”页签，进入资源统计页面。
2. 以环形图的形式表示可用区中CPU分配率（已分配CPU/CPU总量）、内存分配率（已分配内存/内存总量）、磁盘分配率（已分配磁盘/磁盘总量）、私有IP分配率（已分配私有IP/私有IP总量）、宿主机启用与未启用数量与总数、处于不同状态（运行、关机、回收站以及其他状态）的虚拟主机数量与总数量、透传设备(GPU)使用和未使用数量与总数。


## 查看操作日志

该功能用于查看可用区相关操作的日志信息。

1. 在可用区详情页面，单击“操作日志”页签，进入操作日志页面。
    - 加载更多日志：在操作日志页面，列表默认显示20条操作日志信息，如需查看更多操作日志，请单击 **_"加载更多"_** 按钮，获取更多日志信息。
    - 查看日志详情：单击操作日志右侧操作列 **_"查看"_** 按钮，查看日志的详情信息。支持复制详情内容。
    - 查看指定时间段的日志：如需查看某个时间段的操作日志，在列表右上方的开始日期和结束日期中设置具体的日期，查询指定时间段的日志信息。
    - 导出日志：目前仅支持导出本页显示的日志。单击右上角![](../../../images/system/download.png)图标，在弹出的导出数据对话框中，设置导出数据列，单击 **_"确定"_** 按钮，导出日志。