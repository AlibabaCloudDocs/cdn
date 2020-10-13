# 配置CDN联动DDoS高防

阿里云CDN推出联动DDoS高防功能，帮助您的加速域名更好地防御DDoS攻击。本文为您介绍在控制台配置CDN联动DDoS高防功能的具体操作。

在进行配置DDoS高防前，您需要购买DDoS高防实例，详情请参见[DDoS高防控制台](https://yundun.console.aliyun.com/?p=ddosbgp#/ddosbasic/cn-hangzhou)。

如果您的业务使用CDN加速，并且需要防御DDoS攻击。当攻击发生时，需要从CDN切换至DDoS高防，您可以使用该功能进行自动化调度。当DDoS攻击结束后，可以自动将流量切换回CDN进行正常业务分发。

CDN联动功能正在邀测中，主要针对金融、零售、交通、传媒及政府等企业级用户开放，您可以加入钉钉群（32615821）进行咨询和开通该功能。

使用场景包括但不限于以下：

-   金融行业

    保障业务分发高可用，提升跨国访问体验，同时关注信息、交易、数据资产的安全防护，避免网络攻击给企业造成重大风险。

-   零售行业

    保障企业官网，电商平台，订票平台，内部办公协同软件的网络分发质量，同时防护网络安全攻击，保证业务的持续可用性。

-   传媒行业

    保障公共媒体内容高效传播，同时通过网络安全防护保障，避免业务突增和网络攻击对业务稳定性的影响。


1.  登录[CDN控制台](https://cdn.console.aliyun.com)。

2.  在左侧导航栏，单击**域名管理**。

3.  在**域名管理**页面，单击目标域名对应的**管理**。

4.  选择**安全配置** \> **CDN联动DDoS**。

    如果还未开通该功能，请单击**申请开通**跳转到钉钉群进行咨询和开通。

5.  打开**联动DDoS防护**开关。

6.  配置**DDoS联动产品**、**联动目标类型**及**联动目标**。

    ![ddos高防](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/1009068951/p113561.png)

    **说明：** 当前域名没有查询到DDoS高防配置。

    -   未购买DDoS高防：您需要前往[DDoS高防控制台](https://yundun.console.aliyun.com/?p=ddosbgp#/ddosbasic/cn-hangzhou)购买高防实例。
    -   已购买DDoS高防：您需要在[DDoS高防控制台](https://yundun.console.aliyun.com/?p=ddosbgp#/ddosbasic/cn-hangzhou)进行域名配置。
7.  单击**确定**完成配置。


返回**CDN联动DDoS**功能页面，可查看是否配置成功。

![ddos-2](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/1009068951/p113576.png)

您使用联动DDoS功能，CDN将自动为您创建AliyunCDNAccessingDDoSRole角色，并授权CDN使用该角色授权CDN访问DDoS高防产品中的资源。AliyunCDNAccessingDDoSRole角色中包含的权限包括如下接口：

-   DescribeDomainAttackEvents：查询针对网站业务的攻击事件。
-   DescribeDomainDDoSAttackEvents：查询DDoS的攻击事件。
-   DescribeDDoSEvents：查询针对DDoS高防实例的攻击事件。
-   DescribeWebRules：查询网站业务转发规则。
-   DescribeDomainQPSList：查询网站业务的QPS统计信息。
-   DescribeCdnLinkageRules：查询联动配置。

如果您希望删除该AliyunCDNAccessingDDoSRole角色，您需要关闭所有域名的DDoS联动功能，然后才能在RAM中删除该SLR。详情请参见[SLR详细介绍](/cn.zh-CN/角色管理/服务关联角色.md)。

