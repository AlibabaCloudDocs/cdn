# Remove an accelerated domain name

If a domain name no longer needs to be accelerated by Alibaba Cloud Content Delivery Network \(CDN\), you can remove it in the Alibaba Cloud CDN console. You are no longer charged for the domain name after it is removed. This topic describes how to remove an accelerated domain name.

A domain name is added to Alibaba Cloud CDN.

After you activate Alibaba Cloud CDN and enable it to accelerate content delivery for a domain name, you cannot disable Alibaba Cloud CDN for the domain name by closing your Alibaba Cloud account. You must remove the accelerated domain name from Alibaba Cloud CDN. If you want to enable Alibaba Cloud CDN for a domain name after it is removed, you must add the domain name to Alibaba Cloud CDN again. The following table describes the differences between disabling an accelerated domain name and removing an accelerated domain name.

|Parameter|Description|
|---------|-----------|
|**Disable**|Disables acceleration for the domain name. The domain name is not removed from Alibaba Cloud CDN. After an accelerated domain name is disabled, it is not mapped to the CNAME assigned by Alibaba Cloud CDN. Requests that are destined for the domain name are sent to the origin server. However, the configuration of the domain name is retained on CDN nodes. If the settings on your local DNS server are not cleared, or you use the hosts file to resolve the accelerated domain name to a CDN node, data transfer is still generated.|
|**Delete**|After you remove an accelerated domain name from Alibaba Cloud CDN, data transfer is no longer generated by the domain name. Therefore, no fee is charged. In this case, Alibaba Cloud CDN is disabled for the domain name.|

## Procedure

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to remove and choose **![The More icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7823827161/p242681.png)** \> **Delete** in the **Actions** column.

4.  In the message that appears, click **OK**.


## Related API operations

[DeleteCdnDomain](/intl.en-US/New API Reference/Domain name management/DeleteCdnDomain.md)

