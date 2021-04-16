# Prevent high bills

This topic describes the causes of unexpected high bills and the solutions to them. If your domain name is under attack or abused for data transmission, high bandwidth values or traffic spikes may occur. In this case, you may receive bills that are higher than expected.

## Potential risks

-   If an attack occurs, you are charged for the bandwidth resources of your Alibaba Cloud Content Delivery Network \(CDN\) service and network traffic that are consumed.
-   If your domain name is abused for data transmission, high bandwidth values or traffic spikes may occur. This is similar to an attack, and you are charged for the bandwidth resources and network traffic that are consumed.

## Solutions

To ensure that your CDN service runs as expected and prevent unexpected high bills, we recommend that you enable protection features to manage network traffic. For more information, see the [product page of Anti-DDoS](https://www.alibabacloud.com/product/ddos).

The following table lists the features that can be used to manage network traffic.

|Feature|Description|
|-------|-----------|
|Bandwidth cap|If you want to put a cap on the amount of bandwidth resources that a domain name can consume, you can navigate to the **Domain Names** page, find the domain name that you want to manage, and then click the **Advanced** tab. On this tab, you can configure the **Bandwidth Cap** feature.After a bandwidth value reaches the specified bandwidth cap, Alibaba Cloud CDN disables acceleration and requests are directly sent to the origin server. For more information, see [Configure a bandwidth cap](https://www.alibabacloud.com/help/doc-detail/54954.htm).|
|Bandwidth throttling|If you want to throttle bandwidth for Alibaba Cloud CDN, you can [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex). **Note:** After a bandwidth value reaches the specified bandwidth cap, the data transfer rate is reduced and packet loss may occur. |
|Real-time monitoring|If you want to monitor the peak bandwidth values of a domain name in real time, you can use **Cloud Monitor**. After a bandwidth value reaches the specified threshold, notifications are sent to the administrator of your CDN service through SMS messages, emails, or DingTalk messages. This alerts you of potential risks. For more information, see the [product page of Cloud Monitor](https://www.alibabacloud.com/product/cloud-monitor).|
|Spending management and alerts|You can use the following features to monitor and control the expenses of your CDN service. To configure these features, move your pointer over **Expenses** in the top navigation bar of the **console** and select **User Center**. -   Low balance alert: After this feature is enabled, notifications are sent to you through SMS messages if the balance in your Alibaba Cloud account drops below a specified value.
-   Credit: After this feature is disabled, Alibaba Cloud CDN stops running immediately after an overdue payment occurs.
-   High bill alert: After this feature is enabled, notifications are sent to you through SMS messages if a daily bill reaches a specified amount.

**Note:** To ensure the integrity of the statistics and the accuracy of the bills, Alibaba Cloud CDN issues the bill about 3 hours after a billing cycle ends. Therefore, the time when the relevant fees are deducted from your account balance may be later than when the resources are consumed within the billing cycle. Alibaba Cloud does not provide consumption details of CDN resources in bills because Alibaba Cloud CDN is a distributed service. Other CDN providers adopt similar approaches. |

