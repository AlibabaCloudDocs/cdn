---
keyword: [CDN服务, 云产品开通]
---

# 开通CDN服务

在使用CDN之前，您需要先开通CDN服务。本文为您详细介绍了快速开通CDN服务的方法。

执行本文操作之前，请确保您已完成阿里云[账号注册](https://account.aliyun.com/register/register.htm)和[实名认证](https://account.console.aliyun.com/#/auth/home)。

**说明：** 国际站用户在以下情况下需要进行账号实名认证。

-   根据中国内地（大陆）相关法规要求，购买和使用中国内地（大陆）节点云产品服务的用户（包括存量、新购、续费用户）需要进行实名认证。
-   购买云产品服务时，如果您选择的是中国内地（大陆）区域，系统将检查您的实名认证信息。如果您的账号未完成实名认证，您需要先完成账号的实名认证。

1.  登录[阿里云CDN平台](https://www.aliyun.com/product/cdn)。

2.  单击**立即开通**。

3.  选择适合您的**计费类型**，并选中**服务协议**。

    CDN的计费方式，请参见[CDN详细价格信息](https://www.aliyun.com/price/product?spm=a2c4g.11186623.2.10.1b444ee22Dxy8y#/cdn/detail)。

    ![云产品开通页](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4078749951/p66557.png)

4.  单击**立即开通**。

    成功开通CDN服务后，您可以单击**管理控制台**，进入CDN控制台。


## 相关API

您可以调用API接口，实现CDN服务管理，详情如下表所示。

|API|描述|
|---|--|
|[OpenCdnService](/cn.zh-CN/新版API参考/服务类接口/开通CDN服务.md)|调用OpenCdnService开通CDN服务。只有开通服务后，才能进行域名操作。|
|[ModifyCdnService](/cn.zh-CN/新版API参考/服务类接口/修改CDN服务的计费类型.md)|调用ModifyCdnService变更CDN服务的计费类型。|
|[DescribeCdnService](/cn.zh-CN/新版API参考/服务类接口/获取CDN服务状态.md)|调用DescribeCdnService查询CDN服务状态。包括：当前计费类型、服务开通时间、下次生效的计费类型、当前业务状态等。|
|[DescribeCdnUserResourcePackage](/cn.zh-CN/新版API参考/服务类接口/获取CDN用户流量包信息.md)|调用DescribeCdnUserResourcePackage查询CDN用户当前流量包。|
|[DescribeCdnUserQuota](/cn.zh-CN/新版API参考/服务类接口/获取用户资源使用信息.md)|调用DescribeCdnUserQuota查询用户资源上限及已使用情况。|

