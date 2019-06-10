# 关闭私有Bucket回源 {#task_187634 .task}

本文档介绍了如何移除加速域名能够访问您私有bucket内资源内容的权限。您可以通过RAM（Resource Access Management）控制台，取消对应角色名称的授权，关闭私有Bucket回源功能。

**说明：** 若您的加速域名正在使用私有bucket作为源站进行回源，请不要关闭或删除私有bucket授权。

1.  登录[RAM控制台](https://ram.console.aliyun.com/overview)。
2.  在左侧导航栏，单击**RAM角色管理**。
3.  在RAM角色管理页面，单击RAM角色名称**AliyunCDNAccessingPrivateOSSRole**。 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5143/156015101445856_zh-CN.png)

4.  单击**移除权限**。
5.  返回RAM角色管理页面，单击**删除**，单击**确认**。 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5143/156015101545859_zh-CN.png)

    了解如何开启私有Bucket回源，请参见[开启私有Bucket回源](cn.zh-CN/用户指南/域名管理/内容回源设置/开启私有Bucket回源.md#)。


