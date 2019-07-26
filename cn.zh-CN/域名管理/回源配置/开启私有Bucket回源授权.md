# 开启私有Bucket回源授权 {#task_187634 .task}

当您的源站为OSS时，可以开通加速域名访问私有OSS Bucket资源的权限，有效防止资源盗链。通过本文档，您可以了解开启私有Bucket回源授权的操作方法。

您可以配合使用阿里云CDN提供的Refer防盗链功能、鉴权功能，有效保护您的资源安全。详细说明，请参见[配置防盗链](cn.zh-CN/域名管理/配置访问控制/配置Refer防盗链.md#)和[配置URL鉴权](cn.zh-CN/域名管理/配置访问控制/配置URL鉴权/配置URL鉴权.md#)。

**说明：** 

-   仅支持源站类型为OSS域名的加速域名开启私有Bucket回源功能。
-   进行一次回源授权，即授权CDN对您所有Bucket的只读权限，不只是对当前Bucket授权。
-   授权成功并开启了对应域名的私有Bucket回源授权功能，该加速域名可以访问您的私有bucket内的资源内容。开启该功能前，请根据实际的业务情况，谨慎决策。如果您授权的私有Bucket内容并不适合作为CDN加速域名的回源内容，请勿授权或者开启此功能。
-   如果您的网站有被攻击风险：
    -   请购买高防服务。
    -   请勿授权或开启私有Bucket回源授权功能。

1.  登录[CDN控制台](https://cdn.console.aliyun.com)。
2.  在左侧导航栏，单击**域名管理**。
3.  在域名管理页面，单击目标域名对应的**管理**。
4.  在指定域名的左侧导航栏，单击**回源配置**。
5.  在私有Bucket回源区域，单击**点击授权**。 

    ![点击授权](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5143/156413523052546_zh-CN.png)

6.  单击**同意授权**。 

    ![同意授权](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5143/156413523045826_zh-CN.png)

7.  在私有Bucket回源区域，打开私有Bucket回源开关。 了解如何关闭私有Bucket，请参见[关闭私有Bucket回源](cn.zh-CN/域名管理/回源配置/关闭私有Bucket回源授权.md#)。

