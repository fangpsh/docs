---
title: "GPU相关"
date: 2019-07-19T18:32:40+08:00
weight: 40
---

目前仅支持 {{<oem_name>}} kvm 虚拟机使用 GPU，使用的 PCI Passthrough 的方式将宿主机上的 Nvidia/AMD GPU 透传给虚拟机使用。

## 界面操作

### 设置GPU卡

该功能用于设置为虚拟机绑定或解绑GPU卡，绑定GPU卡之前请确保虚拟机所在宿主机上存在GPU透传设备。当虚拟机用于高性能计算、图形显示等用途时，建议绑定GPU卡。

{{% alert title="注意" color="warning" %}}
- 仅{{<oem_name>}}平台支持绑定、解绑GPU卡功能。
- 当宿主机上存在空闲的GPU设备时，宿主机上的虚拟机才可以绑定GPU卡。
- 虚拟机关机状态才可以绑定、解绑GPU卡。
- 批量绑定GPU卡操作仅支持关联同种型号的GPU卡，批量解绑会取消所有已关联的GPU卡。
- 目前仅管理员支持设置GPU功能。
{{% /alert %}}

**单个虚拟机设置GPU卡**

1. 在虚拟机页面，单击虚拟机右侧操作列 **_"更多"_** 按钮，选择下拉菜单 **_"实例设置-设置GPU卡"_** 菜单项，弹出设置GPU卡对话框。
2. 设置GPU卡页面支持绑定和解绑GPU卡。
    - 绑定GPU卡：勾选是否绑定，并选择GPU卡，支持选择为虚拟机绑定多个GPU卡，默认勾选设置成功后自动启动，即绑定GPU卡后自动启动虚拟机，单击 **_"确定"_** 按钮。
    - 解绑GPU卡：取消勾选是否绑定，取消后，则解绑虚拟机上的所有GPU卡，默认勾选设置成功后自动启动，即解绑GPU卡后自动启动虚拟机，单击 **_"确定"_** 按钮。

**批量为虚拟机设置GPU卡**

1. 在虚拟机列表中选择一个或多个{{<oem_name>}}平台上关机状态的虚拟机，单击列表上方 **_"批量操作"_** 按钮，选择下拉菜单 **_"设置GPU卡"_** 菜单项，弹出设置GPU卡对话框。
2. 设置GPU卡页面支持批量绑定和解绑GPU卡。
    - 绑定GPU卡：设置GPU卡选择“关联GPU卡”，选择GPU卡型号，设置每台虚拟机上绑定的GPU卡数量，默认勾选批量绑定GPU后自动启动，即绑定GPU卡后自动启动虚拟机，单击 **_"确定"_** 按钮。
    - 解绑GPU卡：设置GPU卡选择“解绑GPU卡”，默认勾选批量解绑成功后自动启动，即解绑GPU卡后自动启动虚拟机，单击 **_"确定"_** 按钮，批量解绑GPU卡。


## Climc

### 创建 GPU 云主机

- 查询 gpu 列表

```bash
$ climc isolated-device-list --gpu
+--------------------------------------+----------+---------------------+---------+------------------+--------------------------------------+
|                  ID                  | Dev_type |        Model        |  Addr   | Vendor_device_id |               Host_id                |
+--------------------------------------+----------+---------------------+---------+------------------+--------------------------------------+
| 273f4f72-06b6-49aa-8456-4beceec44997 | GPU-HPC  | GeForce GTX 1050 Ti | 41:00.0 | 10de:1c82        | 3bce9607-2597-469f-8d9b-977345456739 |
| a77333e9-08d9-45c6-87eb-a7d8d902c5f5 | GPU-HPC  | Quadro FX 580       | 05:00.0 | 10de:0659        | 3bce9607-2597-469f-8d9b-977345456739 |
+--------------------------------------+----------+---------------------+---------+------------------+--------------------------------------+
```

- 创建 server

server-create 中的 `--isolated-device` 参数指定透传的设备到云主机，可以重复使用多次，透传多个 gpu 到云主机，但要求透传到同一云主机的 gpu 必须在同一宿主机。其余创建参数和创建普通云主机是一样的。

```bash
$ climc server-create --hypervisor kvm --isolated-device 273f4f72-06b6-49aa-8456-4beceec44997 ...
```

### 查询 GPU 云主机

```bash
$ climc server-list --gpu
```

### 关联 GPU

如果云主机所在的宿主机有可用的 gpu，在主机关机的情况下，可以通过 `server-attach-isolated-device` 命令将 gpu 和云主机关联起来，下次主机启动后就可以使用该 gpu 。

```bash
$ climc server-attach-isolated-device <server_id> <device_id>
```

### 卸载 GPU

如果云主机关联了 gpu，可以通过 `server-detach-isolated-device` 卸载主机的某一 gpu。

```bash
$ climc server-detach-isolated-device <server_id> <device_id>
```