# High bill alerts

This topic describes what can cause your bills to be higher than expected and the solutions to them. If your domain name is under attack or abused for data transmission, high bandwidth values or traffic spikes may occur. In this case, you may receive bills higher than expected.

## Potential risks

-   If an attack occurs, you are charged for the bandwidth resources of your Alibaba Cloud Content Delivery Network \(CDN\) service and network traffic that are consumed.
-   If your domain name is abused for data transmission, high bandwidth values or traffic spikes may occur. This is similar to an attack, and you are charged for the bandwidth resources and network traffic that are consumed.

## Solutions

为保障服务的正常运行和避免高额账单的出现，建议开启防护功能或者对流量进行相应的管理。

如果您的业务有潜在的被攻击风险，建议开通SCDN产品，SCDN产品有更强大的整体安全防护能力。详细请参见[安全加速SCDN](https://www.aliyun.com/product/scdn)。

开启防护功能

|攻击类型|防护措施|
|----|----|
|CC攻击|建议您可以选择申请开启**频次控制**功能。详细请参见[频次控制](https://help.aliyun.com/document_detail/146280.html)。|
|DDoS攻击|建议您可以选择申请开启**CDN联动DDoS高防**功能。详细请参见[Configure Anti-DDoS](/intl.en-US/Domain Management/Security configuration/Integrate Alibaba Cloud CDN with Anti-DDoS.md)。|
|流量盗刷|建议您给域名配置**访问控制**功能（包括**Referer防盗链**、**IP黑白名单**、**URL鉴权**等），以避免产生不必要的流量带宽消耗。详细请参见[访问控制功能](https://help.aliyun.com/document_detail/127783.html)。|

**Note:** 如果需要开通**频次控制**和**CDN联动DDoS高防**功能，请submit a ticket[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)[submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex)。目前需要阿里云后台人员审核确认之后才能开通。

To ensure that your CDN service runs as expected and prevent higher than expected bills, we recommend that you enable protection features to manage network traffic. For more information, see the [product page of Anti-DDoS](https://www.alibabacloud.com/product/ddos).

开启流量管理The following table lists the features that can be used to manage network traffic.

|Item|Feature|
|----|-------|
|Bandwidth cap|If you want to put a cap on the amount of bandwidth resources that a domain name can consume, you can navigate to the **Domain Names** page, find the domain name that you want to manage, and then click the **Advanced** tab. On this tab, you can configure the **Bandwidth Cap** feature. After a bandwidth value reaches the specified bandwidth cap, Alibaba Cloud CDN disables acceleration and requests are directly sent to the origin server. For more information, see [Configure a bandwidth cap](/intl.en-US/Domain Management/Advanced settings/Set a bandwidth cap.md).|
|Bandwidth throttling|If you want to throttle bandwidth for Alibaba Cloud CDN, you can submit a ticket[submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).**Note:** After a bandwidth value reaches the specified bandwidth cap, the data transfer rate is reduced and packet loss may occur. |
|Real-time monitoring|If you want to monitor the peak bandwidth values of a domain name in real time, you can use **Cloud Monitor**. After a bandwidth value reaches the specified threshold, notifications will be sent to the administrator of your CDN service through SMS, emails, or DingTalk. This alerts you of potential risks. For more information, see the [云监控产品详情页](https://www.aliyun.com/product/jiankong)[product page of Cloud Monitor](https://www.alibabacloud.com/product/cloud-monitor).|
|Financial management and alerts|You can use the following features to monitor and control the expenses of your CDN service. To configure these features, place your pointer over **Expenses** in the top navigation bar of the **console** and select **User Center**.-   Low balance alert: After this feature is enabled, notifications will be sent to you through SMS when the balance in your account drops below the specified value.
-   Credit: After this feature is disabled, Alibaba Cloud CDN stops running immediately after an overdue payment occurs.
-   High bill alert: After this feature is enabled, notifications will be sent to you through SMS if a daily bill reaches the specified amount.

**Note:** To ensure the integrity of the statistics and the accuracy of the bills, Alibaba Cloud CDN releases the bill about three hours after a billing cycle ends. Therefore, the time when the relevant fees are deducted from your account balance may be later than when the resources are consumed within the billing cycle. Alibaba Cloud does not provide consumption details of CDN resources in bills because Alibaba Cloud CDN is a distributed service. Other CDN providers have adopted similar approaches. |

