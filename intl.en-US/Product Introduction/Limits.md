---
keyword: [ICP filing, Add domain names to Alibaba Cloud CDN, Alibaba Cloud CDN]
---

# Limits

This topic describes the limits that Alibaba Cloud CDN imposes on domain names. Before you add a domain name for CDN to the Alibaba Cloud CDN console, make sure that the domain name for CDN meets all the requirements. This helps you prevent losses that are caused by violations.

## ICP filing

You can determine whether to file a domain name for CDN based on the region you select for the domain name. If you select **Global** or **Mainland China Only**, you must file the domain name. We recommend that you use [Alibaba Cloud ICP Filing](https://beian.aliyun.com/?spm=5176.8142029.388261.3.a0SCC3) to file domain names.

**Note:** To use Alibaba Cloud CDN to provide content delivery services in Mainland China, you must file the domain names that are connected to the applications on origins.

## Content moderation

All domain names connected to Alibaba Cloud CDN must go through content moderation. You cannot add the domain names that contain unauthorized content to the Alibaba Cloud CDN console. The unauthorized content includes but is not limited to the following items:

-   Content that is inaccessible or does not include substantial information
-   Unauthorized games
-   Role-playing and card games
-   Unauthorized software applications
-   Peer-to-peer \(P2P\) lending websites
-   Lottery websites
-   Illegal hospital and pharmaceutical websites
-   Pornography, drugs, and gambling content

**Note:**

-   If the preceding unauthorized content is detected, you shall bear possible risks that may arise. Alibaba Cloud CDN regularly reviews content that is contained in domain names. If unauthorized content is detected in a domain name, Alibaba Cloud CDN immediately disables and forbids the domain name. In certain circumstances, Alibaba Cloud CDN may even permanently forbid all domain names under the Alibaba Cloud account.
-   If you add a wildcard domain name \(for example, `*.example.com`\) to the Alibaba Cloud CDN console and a specific domain name \(for example, `a.example.com`\) contains unauthorized content, Alibaba Cloud CDN disables the wildcard domain name \(`*.example.com`\).
-   If a domain name is rejected due to content moderation, you can view the rejection reason on the Domain Names page in the Alibaba Cloud CDN console. You can modify the content based on the rejection details, and re-submit the domain name for content moderation.

## Limits on domain names

|Item|Limit|
|:---|:----|
|Domain names|You can add a maximum of 50 domain names for each Alibaba Cloud account. If the average daily peak bandwidth required by your domain names exceeds 50 MB, you can [submit a ticket](https://workorder.console.aliyun.com/console.htm?lang=&accounttraceid=3c62958a-b7f1-4439-b87b-5f59ed3e9704#/ticket/add?productCode=cdn) to increase domain names. However, you must make sure that adding domain names does not incur business risks.|
|IP origins|If you select IP for the Origin Info field, you can add a maximum of 10 IP addresses for each domain name for CDN by default.|
|Cache and refresh operations|-   URL refresh: 2,000 URLs per day for each Alibaba Cloud account.
-   Directory refresh: 100 directories per day for each Alibaba Cloud account. |

## Domain name reclaim rules

|Scenario|Action|Solution|
|:-------|:-----|:-------|
|Your domain name for CDN has not been visited for more than 90 days. Your domain name may run properly during this period.|Alibaba Cloud CDN automatically disables the domain name for CDN but retains the records that are related to the domain name for CDN.|Enable the domain name for CDN.|
|Your domain name for CDN has been disabled for more than 120 days, including the days during which the domain name fails content moderation.|Alibaba Cloud CDN automatically deletes the records that are related to the domain name.|Add the domain name for CDN to the Alibaba Cloud CDN console again.|

