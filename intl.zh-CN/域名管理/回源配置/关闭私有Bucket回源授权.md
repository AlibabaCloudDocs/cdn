---
keyword: [回源授权, 私有Bucket]
---

# 关闭私有Bucket回源授权

本文为您介绍如何移除加速域名能够访问您私有Bucket内资源的权限。您可以通过访问控制RAM（Resource Access Management）控制台，取消对应角色名称的授权，关闭私有Bucket回源功能。

如果您的加速域名正在使用私有Bucket作为源站进行回源，请不要关闭或删除私有Bucket授权。

1.  登录[RAM控制台](https://ram.console.aliyun.com/overview)。

2.  在左侧导航栏，单击**RAM角色管理**。

3.  在**RAM角色名称**列表下，单击**AliyunCDNAccessingPrivateOSSRole**角色。

    ![RAM角色管理](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8881959161/p45856.png)

4.  移除角色**AliyunCDNAccessingPrivateOSSRole**中的所有权限。

    1.  单击权限对应的**移除权限**。

    2.  在移除权限的确认对话框中，单击**确定**。

5.  返回**RAM角色管理**页面，删除**AliyunCDNAccessingPrivateOSSRole**角色。

    1.  单击**AliyunCDNAccessingPrivateOSSRole**角色对应的**删除**。

    2.  在**删除RAM角色**的确认对话框中，单击**确定**。


**相关文档**  


[批量配置域名](/intl.zh-CN/新版API参考/域名管理类接口/批量配置域名.md)

