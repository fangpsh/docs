---
title: "费率配置"
linktitle: "费率配置"
weight: 1
description: 用于配置本地IDC和私有云平台上的资源单价。
---

## 费率设置

费率用于配置资源的单价，即一天内指定规格资源的价钱。通过配置费率可以有效统计云管平台上的用户账单信息。

费率来源：

- 公有云平台上资源费率由各厂商决定；
- 本地IDC和私有云平台上的资源费率需要由管理员指定。

**入口**：在云管平台单击左上角![](../../../images/intro/nav.png)导航菜单，在弹出的左侧菜单栏中单击 **_"费用/高级配置/费率配置"_** 菜单项，进入费率配置页面。

  ![](../../../images/bill/rate.png)

云管平台上的费率主要包括3个部分：虚拟资源费率、裸金属服务器费率以及GPU卡费率，通过切换上方页签，配置不同资源的费率信息。

  - 虚拟资源费率：用于设置虚拟机使用的相关资源的费率，如CPU（元/核*天，即1天1核CPU的价钱）、本地硬盘（元/GB\*天）、云硬盘（元/GB\*天）、内存（元/GB\*天）等。
  - 裸金属服务器费率：用于设置云管平台上纳管的物理机的费率信息（元/台*天），列表包括物理机品牌、型号、规格等信息。
  - GPU卡费率：用于设置云管平台上纳管的GPU卡的费率（元/卡*天），列表包括GPU卡所属平台、品牌、型号等信息。

## 刷新资源类型

该功能用于手动刷新资源类型，当新增资源类型时可通过该功能显示对应资源类型的费率信息。

1. 单击列表上方 **_"刷新资源类型"_** 按钮，手动刷新资源类型。

## 费率管理

### 查看历史费率

该功能用于查看资源历史费率、当前生效费率以及未生效费率等信息。

1. 单击资源名称项，进入历史费率页面。
2. 查看资源的历史费率、当前生效费率、未生效费率等。

### 设置新费率

该功能用于设置资源的费率以及费率的生效时间。

1. 单击资源名称项，进入历史费率页面。
2. 单击列表上方 **_"设置新费率"_** 按钮，弹出设置新费率对话框。
3. 设置费率大小以及起始日期（费率生效的日期），单击 **_"确定"_** 按钮。

### 修改费率

该功能用于修改“未生效”费率信息，已过期和已生效的费率不支持修改。

1. 单击资源名称项，进入历史费率页面。
2. 单击“未生效”状态的费率右侧操作列 **_"修改"_** 按钮，弹出设置新费率对话框。
3. 设置费率大小以及起始日期（费率生效的日期），单击 **_"确定"_** 按钮。

### 删除费率

该功能用于删除“未生效”费率信息，已过期和已生效的费率不支持删除。

1. 单击资源名称项，进入历史费率页面。
2. 单击“未生效”状态的费率右侧操作列 **_"删除"_** 按钮，弹出操作确认对话框。
3. 单击 **_"确定"_** 按钮，完成操作。
