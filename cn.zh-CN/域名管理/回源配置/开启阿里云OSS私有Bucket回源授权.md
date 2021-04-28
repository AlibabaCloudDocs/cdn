---
keyword: [OSS域名, 私有Bucket, CDN回源]
---

# 开启阿里云OSS私有Bucket回源授权

当您的源站为OSS时，可以开通加速域名访问私有OSS Bucket资源的权限，有效防止资源盗链。通过本文您可以了解开启私有Bucket回源授权的操作方法。

您可以配合使用阿里云CDN提供的Referer防盗链功能、鉴权功能，有效保护您的资源安全，更多信息，请参见[配置Referer防盗链](/cn.zh-CN/域名管理/访问控制/配置Referer防盗链.md)和[URL鉴权](/cn.zh-CN/域名管理/访问控制/URL鉴权配置/URL鉴权.md)。

**说明：**

-   开启私有OSS Bucket回源授权后，即授权CDN对您所有Bucket的只读权限，不只是对当前Bucket授权。
-   授权成功并开启了对应域名的私有Bucket回源授权功能，该加速域名可以访问您的私有Bucket内的所有资源。开启该功能前，请根据您的实际业务情况谨慎决策。如果您授权的私有Bucket内容并不适合作为CDN加速的回源内容，请勿授权或开启此功能。
-   如果您的网站有被攻击的风险，请购买高防服务，同时请勿授权或开启私有Bucket回源授权功能。

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

2.  在左侧导航栏，单击**域名管理**。

3.  在**域名管理**页面，单击目标域名对应的**管理**。

4.  在指定域名的左侧导航栏，单击**回源配置**。

5.  在**阿里云OSS私有Bucket回源**区域，单击**点击授权**。

6.  单击**同意授权**。

    **说明：** 当您的源站为OSS时，才支持开通加速域名访问私有OSS Bucket资源的权限。

    ![同意授权](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1049859161/p45826.png)

7.  在**阿里云OSS私有Bucket回源**区域，打开**阿里云OSS私有Bucket回源**开关。

    当CDN回源OSS私有Bucket访问非加密文件时，完成以上配置即可正常访问文件。如果您在OSS上对文件进行了KMS加密，此时将无法直接访问，需要为**AliyunCDNAccessingPrivateOSSRole**角色添加**AliyunKMSCryptoUserAccess**权限才能正常访问文件。

    如需关闭私有Bucket，请参见[关闭私有Bucket回源授权](/cn.zh-CN/域名管理/回源配置/关闭私有Bucket回源授权.md)。

8.  为**AliyunCDNAccessingPrivateOSSRole**角色添加**AliyunKMSCryptoUserAccess**权限。

    1.  登录[RAM控制台](https://ram.console.aliyun.com/)。

    2.  在左侧导航栏，单击**RAM角色管理**。

    3.  在**RAM角色名称**列表下，找到**AliyunCDNAccessingPrivateOSSRole**角色。

    4.  单击**添加权限**，**被授权主体**会自动填入。

    5.  在**系统策略**下搜索**AliyunKMSCryptoUserAccess**，并单击**AliyunKMSCryptoUserAccess**，会添加到**已选择**列表。

    6.  单击**确定**，显示授权成功。

    7.  单击**完成**。


**相关文档**  


[批量配置域名](/cn.zh-CN/新版API参考/域名管理类接口/批量配置域名.md)

