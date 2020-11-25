# Configure WAF

Alibaba Cloud Content Delivery Network \(CDN\) integrates with Web Application Firewall \(WAF\) to filter out malicious requests and redirect secure requests to origin servers. WAF can protect web servers against intrusions, secure core data, and prevent server abnormalities caused by attacks. This topic describes the features, scenarios, and billing methods of WAF and how to configure WAF.

-   WAF is activated in the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com). To activate WAF in the Alibaba Cloud CDN console, choose **Security & Protection** \> **WAF** and click **Activate**.
-   WAF can be used to protect only CDN nodes in mainland China. Before you activate WAF, confirm the accelerated region of your domain name. For more information about how to modify the accelerated region, see [Modify basic information](/intl.en-US/Domain Management/Basic settings/Modify basic information.md).

Alibaba Cloud CDN can be integrated with WAF. After WAF is activated, it can protect CDN nodes. For more information about features of WAF, see [What is WAF?](/intl.en-US/Product Introduction/What is WAF?.md).

WAF is applicable to industries such as finance, e-commerce, O2O, Internet Plus, gaming, government, and insurance. WAF protects websites against unexpected losses caused by attacks while Alibaba Cloud CDN accelerates the websites.

WAF can address the following issues:

-   Protects your website against injections that may retrieve core data of your website.
-   Protects your website against Trojans that may compromise public trust of your website.
-   Provides virtual patches that enable quick fixes of newly discovered vulnerabilities.

After you activate WAF for a domain name, WAF detects all requests sent to the domain name, counts the number of requests by account, and then charges fees accordingly. For more information about the pricing of WAF, see [Pricing of value-added services - WAF](https://www.aliyun.com/price/product?spm=a2c4g.11186623.2.10.1b444ee22Dxy8y#/cdn/detail).

## Procedure

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the Domain Names page, find the target domain name and click **Manage**.

4.  In the left-side navigation tree, click **Security Settings**.

5.  Click the WAF tab and turn on the **WAF Configuration** switch.

6.  Click **Modify**.

7.  Follow the instructions on the page to configure the Web Application Protection and HTTP ACL Policy features.

    |Feature|Parameter|Description|
    |-------|---------|-----------|
    |**Web Application Protection**|**Status**|Turn on or off web application protection.|
    |**Mode**|Web application protection supports the following protection modes:     -   **Prevention**

Directly blocks detected attacks.

    -   **Detection**

Sends alerts after attacks are detected but does not block the attacks. |
    |**Mode of protection policy**|Web application protection supports the following protection policies:     -   **Loose rule group**

If the **Medium rule group** causes a high rate of false positive, we recommend that you select the **Loose rule group**. The loose rule group has the lowest false positive rate but the highest false negative rate.

    -   **Medium rule group**

The default policy.

    -   **Strict rule group**

If you require stronger protection against path traversal, SQL injections, and command execution attacks, we recommend that you select the **Strict rule group**.

If the protection policy causes a high rate of false negative, you can change the protection policy. The loose rule group has the lowest false positive rate but the highest false negative rate. |
    |**HTTP ACL Policy**|**Status**|Turn on or off the HTTP ACL policy feature.|
    |**Rule**|A default rule is provided. You can click **Settings** to add a rule or modify the default rule. Each rule can contain up to three match conditions and the logical relationship among the conditions are AND. It indicates that a rule is hit only when all the three match conditions are met.|


## Assign a service linked role

After WAF is activated, the service linked role AliyunCDNAccessingWAFRole is automatically created and assigned to Alibaba Cloud CDN. Alibaba Cloud CDN can assume this role to access resources in WAF.

The AliyunCDNAccessingWAFRole role supports the following API operations:

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

If you need to delete the AliyunCDNAccessingWAFRole role, submit a ticket to delete the WAF instance and disable WAF features for all accelerated domain names. Then, delete this role in the Resource Access Management \(RAM\) console.

