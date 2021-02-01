---
keyword: [authentication, RAM]
---

# RAM authentication

Before you call the Alibaba Cloud Content Delivery Network \(CDN\) API as a Resource Access Management \(RAM\) user, make sure that you are granted the required permissions by the Alibaba Cloud account. In the permission policy, use an Alibaba Cloud Resource Name \(ARN\) to specify the resource that you are allowed to access. This topic describes how to define a resource or an API operation in a permission policy.

By default, you can use your Alibaba Cloud account or a RAM user to manage your CDN resources in the CDN console or by calling API operations. Specific permissions are required when:

-   A newly created RAM user does not have permissions to manage the CDN resources that belong to your Alibaba Cloud account.
-   Before you can manage a resource, you must be granted the required permissions on the resource and the relevant API operations by the resource owner.

When another Alibaba Cloud account attempts to access CDN resources that belong to your Alibaba Cloud account by calling API operations, Alibaba Cloud CDN instructs RAM to check whether the Alibaba Cloud account has the required permissions. Required permissions vary based on the requested CDN resources and API operations. For more information about how to grant permissions, see the [RAM documents](/intl.en-US/Product Introduction/What is RAM?.md) and [API reference](/intl.en-US/API Reference/API Reference (RAM)/List of operations by function.md).

For more information about how to manage Alibaba Cloud CDN as a RAM user, see [Create a RAM user](/intl.en-US/Service Management/Other features/Create a RAM user.md).

For more information about how to use RAM to create custom permission policies for Alibaba Cloud CDN, see [Use RAM to manage Alibaba Cloud CDN permissions](/intl.en-US/Tutorials/Use RAM to manage Alibaba Cloud CDN permissions.md).

## Supported resources

The following table describes the CDN resources that can be defined in permission policies.

**Note:** $accountid represents the ID of the Alibaba Cloud account. You can use an asterisk \(\*\) to specify all account IDs.

|Resource type|Syntax|Description|
|:------------|:-----|:----------|
|service|acs:cdn:\*:$accountid:\*|Authorizes RAM users to manage the CDN service, for example, to change the specifications and query account information.|
|domain|acs:cdn:\*:$accountid:domain/$domainName|Authorizes RAM users to manage accelerated domain names, for example, to add, configure, and query domain names. $domainName specifies a specific domain name. You can use an asterisk \(\*\) in the expression to specify a wildcard domain name, such as \*.aliyun.com.

You can use an asterisk \(\*\) at the end of the expression acs:cdn:\*:$accountid:domain/\* to specify all domain names. |
|acs:cdn:\*:$accountid:domain/\*|

## Supported CDN API operations

The following table describes the API operations of Alibaba Cloud CDN that can be defined in permission policies.

|API|Syntax|
|:--|:-----|
|OpenCdnService|acs:cdn:\*:$accountid:\*|
|DescribeCdnService|acs:cdn:\*:$accountid:\*|
|ModifyCdnService|acs:cdn:\*:$accountid:\*|
|DescribeUserDomains|acs:cdn:\*:$accountid:domain/\*|
|DescribeCdnDomainDetail|acs:cdn:\*:$accountid:domain/$domainName|
|AddCdnDomain|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|StartCdnDomain|acs:cdn:\*:$accountid:domain/$domainName|
|StopCdnDomain|acs:cdn:\*:$accountid:domain/$domainName|
|DeleteCdnDomain|acs:cdn:\*:$accountid:domain/$domainName|
|RefreshObjectCaches|acs:cdn:\*:$accountid:domain/$domainName|
|PushObjectCache|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeRefreshTasks|acs:cdn:\*:$accountid:domain/\*|
|DescribeRefreshQuota|acs:cdn:\*:$accountid:domain/\*|
|ForbidLiveStream|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainBpsData|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainSrcBpsData|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainHitRateData|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainQpsData|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainHttpCodeData|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainsUsageByDay|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeTopDomainsByFlow|acs:cdn:\*:$accountid:domain/\*|
|DescribeDomainPvData|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainUvData|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainRegionData|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainISPData|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainTopUrlVisit|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeDomainFileSizeProportionData|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeCdnDomainLogs|acs:cdn:\*:$accountid:domain/\*|
|acs:cdn:\*:$accountid:domain/$domainName|
|DescribeIpInfo|acs:cdn:\*:$accountid:domain/\*|

