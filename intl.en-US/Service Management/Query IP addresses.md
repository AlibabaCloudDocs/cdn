---
keyword: [diagnostic tool, CDN tool, query IP address]
---

# Query IP addresses

Alibaba Cloud Content Delivery Network \(CDN\) allows you to query whether an IP address belongs to a CDN node. You can query IP addresses in the Alibaba Cloud CDN console.

## Procedure

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Tools**.

3.  In the **IP Address** filed, enter the IP address that you want to query and click **Check**.

    **Note:** You can query IPv4 addresses and IPv6 addresses. You can query only one IP address at a time.

    ![Query IP addresses](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4004419161/p51480.png)

4.  View drift detection results.

    -   If the specified IP address belongs to a CDN node, the results show the following information about the IP address: **Region**, **Provider**, and **CDN Node**.

        ![View the result.](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9518609161/p51482.png)

    -   If the specified IP address does not belong to a CDN node, the result shows the following message: **No matching records found.**.

## Related API operations

[DescribeIpInfo](/intl.en-US/New API Reference/Auxiliary tool operations/DescribeIpInfo.md)

