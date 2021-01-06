---
keyword: [ICP filing for domain names, add domain names to Alibaba Cloud CDN, Alibaba Cloud CDN]
---

# Limits

This topic describes the limits that Alibaba Cloud Content Delivery Network \(CDN\) imposes on domain names. Before you add a domain name to Alibaba Cloud CDN, make sure that the domain name meets the requirements. This helps you prevent losses that can be caused by violations.

## Apply for an Internet Content Provider \(ICP\) number for an accelerated domain name

Whether you need to apply for an ICP number for an accelerated domain name is based on the accelerated region of the domain name. If you select **Global** or **Mainland China Only**, you must apply for an ICP number for the domain name. We recommend that you apply for ICP numbers through [Alibaba Cloud ICP Filing System](https://beian.aliyun.com/?spm=5176.8142029.388261.3.a0SCC3).

**Note:** To use Alibaba Cloud CDN to accelerate content delivery in mainland China, you must apply for an ICP number for the accelerated domain name.

## Content moderation

All content of domain names added to Alibaba Cloud must be reviewed. Domain names that cannot be added to Alibaba Cloud CDN include but are not limited to:

-   The content is inaccessible or does not contain substantial information
-   Servers that host pirated games
-   Websites that provide multiplayer games and card games
-   Websites that provide downloads of pirated software
-   Websites that run peer-to-peer \(P2P\) lending
-   Lottery websites
-   Websites of unlicensed hospital and pharmaceuticals
-   Websites that contain pornography, drugs, and gambling content

**Note:**

-   If the preceding content is detected from your accelerated domain name, you must bear the possible risks that may arise. Alibaba Cloud CDN regularly reviews the content of accelerated domain names. If illicit content is detected from a domain name, Alibaba Cloud CDN immediately disables or blocks the domain name. If the violation is severe, Alibaba Cloud CDN may even permanently block all domain names under the Alibaba Cloud account.
-   If you add a wildcard domain name, for example, `*.example.com`, to Alibaba Cloud CDN and a specific domain name, for example, `a.example.com`, that matches the wildcard domain name contains illicit content, Alibaba Cloud CDN disables the wildcard domain name \(`*.example.com`\).
-   If a domain name fails the review, you can check the reason for rejection on the Domain Names page in the Alibaba Cloud CDN console. You can modify the content based on the rejection details, and submit the domain name for review again.

## Limits

-   Limits on domain names

    |Item|Limit|
    |:---|:----|
    |Domain names|You can add a maximum of 50 domain names to Alibaba Cloud CDN with each Alibaba Cloud account. If the average daily peak bandwidth of your domain names exceeds 50 Mbit/s, you can [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex) to increase the upper limit of domain names. Make sure that the increase of domain names does not incur business risks.|
    |IP addresses of origin servers|If the origin server of an accelerated domain name uses IP addresses, you can add a maximum of 10 IP addresses for each accelerated domain name.|
    |Cache and refresh operations|    -   URL refresh: 2,000 URLs per day for each Alibaba Cloud account.
    -   Directory refresh: 100 directories per day for each Alibaba Cloud account. |

-   Limits on feature configurations

    **Note:** Some features of Alibaba Cloud CDN support multiple configuration records. However, these features support a limited number of configuration records, as described in the following table.

    |Feature|Limit|
    |:------|:----|
    |**Custom Request Header**|Supports a maximum number of 50 configuration records.|
    |**Custom Response Headers**|
    |**URI Rewrite**|
    |**Parameter Rewrite**|
    |**Cache Expiration**|


## Domain name reclaim rules

|Scenario|Action|Solution|
|:-------|:-----|:-------|
|An accelerated domain name has not been visited for more than 90 days. The domain name may run as expected during this period.|Alibaba Cloud CDN automatically disables the domain name but retains the records that are related to the domain name.|Enable the domain name.|
|An accelerated domain name remains disabled for more than 120 days, including the days during which the domain name fails the review on content.|Alibaba Cloud CDN automatically deletes the records that are related to the domain name.|Add the domain name to Alibaba Cloud CDN again.|

