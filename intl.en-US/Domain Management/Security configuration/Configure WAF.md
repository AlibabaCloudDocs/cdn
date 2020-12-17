# Configure WAF

Alibaba Cloud Content Delivery Network \(CDN\) integrates with Web Application Firewall \(WAF\) to filter out malicious requests and redirect secure requests to origin servers. WAF can protect web servers against intrusions, secure core data, and prevent server anomalies caused by attacks. This topic describes the features, scenarios, and billing methods of WAF and how to configure WAF.

## Prerequisites

-   WAF is activated in the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com). To activate WAF in the Alibaba Cloud CDN console, choose **Security & Protection** \> **WAF** in the left-side navigation pane and click **Activate**.
-   WAF can be used to protect only CDN nodes in mainland China. Before you activate WAF, confirm the accelerated region of your domain name. For more information about how to change the accelerated region, see [Modify basic information](/intl.en-US/Domain Management/Basic settings/Modify basic information.md).

## Background information

Alibaba Cloud CDN is integrated with WAF. After WAF is activated, it can protect CDN nodes. For more information about features of WAF, see [What is WAF?](/intl.en-US/Product Introduction/What is WAF?.md)

WAF is applicable to industries such as finance, e-commerce, O2O, Internet Plus, gaming, government, and insurance. WAF protects websites against unexpected losses caused by attacks while Alibaba Cloud CDN accelerates the websites.

WAF can address the following issues:

-   Prevents website data leaks caused by SQL injections.
-   Protects your website against Trojans that may compromise public trust of your website.
-   Provides virtual patches that enable quick fixes of newly discovered vulnerabilities.

After you activate WAF for a domain name, WAF detects all requests sent to the domain name, counts the number of requests by account, and then charges fees accordingly. For more information about the pricing of WAF, see [Pricing of value-added services - WAF](https://www.aliyun.com/price/product?spm=a2c4g.11186623.2.10.1b444ee22Dxy8y#/cdn/detail).

## Procedure

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the left-side domain name management pane, click **Security Settings**.

5.  Click the **CDN WAF** tab and turn on the CDN WAF switch.

6.  Click **Modify**.

7.  Follow the instructions on the page to configure the **Web Security** and **Access Control/Throttling** features.

    |Feature|Parameter|Description|
    |-------|---------|-----------|
    |**Web Security**|**Status**|Enable or disable the web intrusion prevention feature.|
    |**Mode**|Web intrusion prevention supports the following modes:    -   **Block**: directly blocks attacks.
    -   **Warn**: sends alerts but does not block attacks. |
    |**Protection Rule Group**|Web intrusion prevention supports the following protection rules:    -   **Loose rule group**: If the **Medium rule group** causes a high rate of false positives, we recommend that you select the **Loose rule group**. The loose rule group has the lowest false positive rate but the highest false negative rate.
    -   **Medium rule group**: The default protection rule.
    -   **Strict rule group**: If you require stronger protection against path traversal, SQL injections, and command execution attacks, we recommend that you select the **Strict rule group**. |
    |**Decoding Settings**|Specify the data formats that need to be decoded and analyzed by the RegEx protection engine.    1.  Click ![jiema](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0200918061/p178440.png) to select data formats from the drop-down list.
    2.  Select or clear the formats that you want to decode.
        -   You cannot clear the following formats: **URL Decoding**, **JavaScript Unicode Decoding**, **Hex Decoding**, **Comment Processing**, and **Space Compression**.
        -   You can clear the following formats: **Multipart Data Parsing**, **JSON Data Parsing**, **XML Data Parsing**, **Serialized PHP Data Decoding**, **HTML Entity Decoding**, **UTF-7 decoding**, **Base64 Decoding**, and **Form Data Parsing**.
    3.  Click **OK**.
**Note:** To ensure higher performance, the RegEx protection engine decodes and analyzes the request content of all formats by default. If the RegEx protection engine blocks normal requests that contain content of specified formats, you can clear the formats to reduce the false positive rate. |
    |**Access control/throttling**|**IP Blacklist**|**Status**|Enable or disable the IP address blacklist.**Note:** An IP address blacklist blocks requests from the specified IP addresses and CIDR blocks. It limits requests from specified regions. You can click **Settings** to add IP addresses or regions to the blacklist based on your business requirements. |
    |**Custom Protection Policy**|**Status**|Enable or disable custom protection policies.**Note:** A custom protection policy supports custom access control list \(ACL\) rules that are based on specified conditions or rate limiting rules. You can click **Settings** to create custom protection policies based on your business requirements. |


## Assign a service linked role

After WAF is activated, the service linked role AliyunServiceRoleForCDNAccessingWAF is automatically created and assigned to Alibaba Cloud CDN. Alibaba Cloud CDN can assume this role to access resources in WAF.

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

If you need to delete the AliyunServiceRoleForCDNAccessingWAF role, [submit ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex) to delete the WAF instance and disable WAF features for all accelerated domain names. Then, delete this role in the Resource Access Management \(RAM\) console.

