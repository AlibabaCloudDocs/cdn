# 关闭私有Bucket回源授权 {#task_187634 .task}

本文档介绍了如何移除加速域名能够访问您私有bucket内资源的权限。您可以通过RAM（Resource Access Management）控制台，取消对应角色名称的授权，关闭私有Bucket回源功能。

**说明：** 若您的加速域名正在使用私有bucket作为源站进行回源，请不要关闭或删除私有bucket授权。

1.  登录[RAM控制台](https://ram.console.aliyun.com/overview)。
2.  在左侧导航栏，单击**RAM角色管理**。
3.  在RAM角色管理页面，单击RAM角色名称**AliyunCDNAccessingPrivateOSSRole**。 

    ![RAM角色管理](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5143/156653071745856_zh-CN.png)

4.  单击待删除权限对应的**移除权限**。 在移除权限确认对话框中，单击**确认**。
5.  返回RAM角色管理页面，单击待删除角色对应的**删除**。 

    在删除RAM角色确认对话框中，单击**确认**。


