---
title: "删除"
date: 2021-06-11T08:22:33+08:00
weight: 50
---

该功能用于删除云用户组，删除用户组时将同步删除缓存到公有云平台的用户组。

**单个删除**

1. 在左侧导航栏，选择 **_"多云管理/云账号/云用户组"_** 菜单项，进入云用户组页面。
2. 单击云用户组右侧操作列 **_"更多"_** 按钮，选择下拉菜单 **_"删除"_** 菜单项，弹出操作确认对话框。
2. 单击 **_"确定"_** 按钮，完成操作。

**批量删除**

1. 在云用户组列表中选择一个或多个云用户组，单击列表上方 **_"删除"_** 按钮，弹出操作确认对话框。
2. 单击 **_"确定"_** 按钮，完成操作。


```bash 
# 命令行删除云用户组
$ climc cloud-group-delete <云用户组名称或ID>
```


{{% alert title="注意" %}}
- 删除云用户组会真实删除云上相应的资源
- 可查看云用户组权限组缓存列表查看当前云用户组和各个云账号上面的资源映射
{{% /alert %}}

