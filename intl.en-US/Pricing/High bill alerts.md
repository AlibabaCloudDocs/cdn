# High bill alerts

This topic describes what can cause your bills to be higher than expected and the solutions to them. If your domain name is under attack or abused for data transmission, high bandwidth values or traffic spikes may occur. In this case, you may receive bills higher than expected.

## Potential risks

-   If an attack occurs, you are charged for the bandwidth resources of your Alibaba Cloud Content Delivery Network \(CDN\) service and network traffic that are consumed.
-   If your domain name is abused for data transmission, high bandwidth values or traffic spikes may occur. This is similar to an attack, and you are charged for the bandwidth resources and network traffic that are consumed.

## Solutions

To ensure that your CDN service runs as expected and prevent higher than expected bills, we recommend that you enable protection features to manage network traffic. For more information, see the [product page of Anti-DDoS](https://www.alibabacloud.com/product/ddos).

The following table lists the features that can be used to manage network traffic.

|Item|Feature|
|----|-------|
|Bandwidth cap|If you want to put a cap on the amount of bandwidth resources that a domain name can consume, you can navigate to the **Domain Names** page, find the domain name that you want to manage, and then click the **Advanced** tab. On this tab, you can configure the **Bandwidth Cap** feature. After a bandwidth value reaches the specified bandwidth cap, Alibaba Cloud CDN disables acceleration and requests are directly sent to the origin server. For more information, see [Configure a bandwidth cap](/intl.en-US/Domain Management/Advanced settings/Configure bandwidth cap.md).|
|Bandwidth throttling|If you want to throttle bandwidth for Alibaba Cloud CDN, you can [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).**Note:** After a bandwidth value reaches the specified bandwidth cap, the data transfer rate is reduced and packet loss may occur. |
|Real-time monitoring|If you want to monitor the peak bandwidth values of a domain name in real time, you can use **Cloud Monitor**. After a bandwidth value reaches the specified threshold, notifications will be sent to the administrator of your CDN service through SMS, emails, or DingTalk. This alerts you of potential risks. For more information, see the [product page of Cloud Monitor](https://www.alibabacloud.com/zh/product/cloud-monitor).|
|Financial management and alerts|You can use the following features to monitor and control the expenses of your CDN service. To configure these features, place your pointer over **Expenses** in the top navigation bar of the **console** and select **User Center**.-   Low balance alert: After this feature is enabled, notifications will be sent to you through SMS when the balance in your account drops below the specified value.
-   Credit: After this feature is disabled, Alibaba Cloud CDN stops running immediately after an overdue payment occurs.
-   High bill alert: After this feature is enabled, notifications will be sent to you through SMS if a daily bill reaches the specified amount.

**Note:** To ensure the integrity of the statistics and the accuracy of the bills, Alibaba Cloud CDN releases the bill about three days after a billing cycle ends. Therefore, the time when the relevant fees are deducted from your account balance may be later than when the resources are consumed within the billing cycle. Alibaba Cloud does not provide consumption details of CDN resources in bills because Alibaba Cloud CDN is a distributed service. Other CDN providers have adopted similar approaches. |

