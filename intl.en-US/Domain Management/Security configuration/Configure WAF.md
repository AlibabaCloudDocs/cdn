# Configure WAF

Alibaba Cloud Content Delivery Network \(CDN\) integrates with Web Application Firewall \(WAF\) to filter out malicious requests and redirect secure requests to origin servers. WAF can protect web servers against intrusions, secure core data, and prevent server anomalies caused by attacks. This topic describes the features, use scenarios, and billing methods of WAF and how to configure WAF for an accelerated domain name.

## Prerequisites

-   WAF Pro Edition or WAF Business Edition is activated. If you have not activated WAF Pro Edition or WAF Business Edition, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).
-   Before you enable WAF for an accelerated domain name, make sure that the accelerated region of the domain name is set to **Global** or **Global \(Excluding Mainland China\)**. For more information about how to change the accelerated region for an accelerated domain name, see [Modify basic information](/intl.en-US/Domain Management/Basic settings/Modify basic information.md).

## Value-added services

For more information about how to configure features of WAF, see the [WAF documents](https://www.alibabacloud.com/help/zh/product/28515.htm). The following table lists the features supported by WAF Business Edition.

|Feature|WAF Business Edition|
|-------|--------------------|
|Scan protection|[Supported](https://www.alibabacloud.com/help/zh/doc-detail/147717.htm)|
|Account security|[Supported](https://www.alibabacloud.com/help/zh/doc-detail/147940.htm)|
|HTTP flood protection|[Supported](https://www.alibabacloud.com/help/zh/doc-detail/147594.htm)|
|IP blacklists|[Supported](https://www.alibabacloud.com/help/zh/doc-detail/147687.htm)|
|Rate limiting|[Supported](https://www.alibabacloud.com/help/zh/doc-detail/147937.htm)|
|Bot threat intelligence rules|[Supported](https://www.alibabacloud.com/help/zh/doc-detail/159911.htm)|
|JavaScript validation|[Supported](https://www.alibabacloud.com/help/zh/doc-detail/147937.htm)|
|Crawler whitelists|[Supported](https://www.alibabacloud.com/help/zh/doc-detail/159910.htm)|
|Web application protection|[Supported](https://www.alibabacloud.com/help/zh/doc-detail/147592.htm)|
|Zero-day attack protection|[Supported](https://www.alibabacloud.com/help/zh/doc-detail/147592.htm)|
|Block and Warn protection modes|[Supported](https://www.alibabacloud.com/help/zh/doc-detail/147592.htm)|
|Decoding and analytics of request data in specified formats|[Supported](https://www.alibabacloud.com/help/zh/doc-detail/147592.htm)|
|Custom rule groups|[Supported](https://www.alibabacloud.com/help/zh/doc-detail/99477.htm)|
|HTTP access control list \(ACL\) policies|[Supported](https://www.alibabacloud.com/help/zh/doc-detail/61993.htm)|
|Log Service|[Supported](https://www.alibabacloud.com/help/zh/doc-detail/95078.htm) with a storage capacity of 3 TB|

## Background information

Alibaba Cloud CDN can be integrated with WAF. You can use WAF to protect resources on CDN nodes. For more information about features of WAF, see [What is WAF?](/intl.en-US/Product Introduction/What is WAF?.md)

WAF is applicable to sectors and industries such as finance, e-commerce, online-to-offline \(O2O\), Internet Plus, gaming, public service, and insurance. WAF protects websites accelerated by Alibaba Cloud CDN against unexpected loss caused by attacks.

WAF provides the following protection features:

-   Prevents website data leaks caused by SQL injections.
-   Protects your website against Trojans that may compromise the public trust of your website.
-   Provides virtual patches that enable quick fixes of newly discovered vulnerabilities.

After you enable WAF for a domain name, WAF scans all requests that are sent to the domain name, counts the number of requests by account, and then charges fees based on the billing rules. For more information about the pricing of WAF, see [Value-added services - WAF](https://www.aliyun.com/price/product?spm=a2c4g.11186623.2.10.1b444ee22Dxy8y#/cdn/detail).

## Procedure

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the left-side domain name management pane, click **Security Settings**.

5.  On the **WAF** tab, turn on CDN WAF.

6.  Click **Modify**.

7.  Follow the instructions on the page to configure the protection features on the **Web Security**, **Bot Management**, and **Access Control/Throttling** tabs.

    |Feature|Parameter|Description|
    |-------|---------|-----------|
    |**Web Security**|**Status**|You can turn on or off web intrusion prevention.|
    |**Mode**|Web application protection supports the following protection modes:    -   **Block**: blocks attacks immediately after they are detected.
    -   **Alert**: sends alerts after attacks are detected but does not block the attacks. |
    |**Protection Rule Group**|Web application protection supports the following protection rules:    -   **Loose rule group**: If the **Medium rule group** causes a high rate of false positives, we recommend that you select the **Loose rule group**. The loose rule group has the lowest false positive rate but the highest false negative rate.
    -   **Medium rule group**: the default protection rule.
    -   **Strict rule group**: If you require stronger protection against path traversal, SQL injections, and command execution attacks, we recommend that you select the **Strict rule group**. |
    |**Decoding Settings**|You can specify the data formats that need to be decoded and analyzed by the RegEx protection engine.     1.  Click ![jiema](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0200918061/p178440.png) to select data formats from the drop-down list.
    2.  Select or clear data formats based on your business requirements.
        -   You cannot clear the following formats: **URL Decoding**, **JavaScript Unicode Decoding**, **Hex Decoding**, **Comment Processing**, and **Space Compression**.
        -   You can clear the following formats: **Multipart Data Parsing**, **JSON Data Parsing**, **XML Data Parsing**, **Serialized PHP Data Decoding**, **HTML Entity Decoding**, **UTF-7 decoding**, **Base64 Decoding**, and **Form Data Parsing**.
    3.  Click **OK**.
**Note:** To ensure higher performance, the RegEx protection engine decodes and analyzes the request content in all formats by default. If the RegEx protection engine blocks requests that contain content in formats that you do not want to block, you can clear the formats to reduce the false positive rate. |
    |**Bot Management** \(Business Edition only\)|**Allowed Crawlers**|**Status**|You can enable or disable this feature. **Note:** This feature allows you to use crawlers on specific search engines that are included in the whitelist, Crawlers can be used on all domain names of these websites. You can click **Settings** to enable or disable this feature based on your business requirements. |
    |**Typical Bot Behavior Identification**|**Status**|You can enable or disable this feature. **Note:** This feature provides general algorithms to identify typical crawler behaviors. You can configure relevant parameters and thresholds to prevent advanced crawlers. You can click **Settings** to add algorithm rules based on your business requirements. |
    |**Bot Threat Intelligence**|**Status**|You can enable or disable this feature. **Note:** This feature provides information about suspicious IP addresses of dialers, data centers, and malicious scanners based on the computing capabilities of Alibaba Cloud. This feature also maintains a dynamic IP library of malicious crawlers and prevents crawlers from accessing specific domain names or paths. You can click **Settings** to configure this feature based on your business requirements. |
    |**Access Control/Throttling**|**IP Blacklist**|**Status**|You can enable or disable the IP blacklist feature. **Note:** You can use the IP blacklist to block requests from specified IP addresses or CIDR blocks, or limit requests from IP addresses in specified regions. You can click **Settings** to add IP addresses or regions to the blacklist. |
    |**Custom Protection Policy**|**Status**|You can enable or disable the custom protection policy feature. **Note:** This allows you to customize an access control rule and apply the access control rule to a specific object. A default rule is provided. You can click **Settings** to add a rule. |


## Assign a service-linked role

After WAF is activated, the service-linked role AliyunServiceRoleForCDNAccessingWAF is automatically created and assigned to Alibaba Cloud CDN. Alibaba Cloud CDN can assume this role to access resources in WAF.

AliyunServiceRoleForCDNAccessingWAF has the following permissions:

-   DescribePayInfo
-   CreatePostpaidInstance
-   CreateOutputDomainConfig
-   DeleteOutputDomainConfig
-   DescribeDomainWebAttackTypePv
-   ModifyLogServiceStatus
-   DescribeProtectionModuleMode
-   DescribeDomainRuleGroup
-   DescribeRegions
-   ModifyProtectionRuleStatus
-   ModifyProtectionRuleCacheStatus
-   DescribePeakValueStatisticsInfo
-   DescribeDomainAccessStatus
-   DescribeFlowStatisticsInfo
-   DescribeDomainTotalCount
-   DescribeResponseCodeStatisticsInfo
-   DescribeDDosCreditThreshold
-   ModifyDomainClusterType
-   DescribeInstanceInfo
-   DescribeOutputDomains
-   CreateOutputDomain
-   DeleteOutputDomain
-   DeleteInstance
-   DescribeInstanceSpecInfo
-   DescribeDomainBasicConfigs

If you want to delete the AliyunServiceRoleForCDNAccessingWAF role, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex) to delete the WAF instance and disable WAF features for all accelerated domain names. Then, delete this role in the Resource Access Management \(RAM\) console.

