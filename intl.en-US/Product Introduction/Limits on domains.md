# Limits on domains {#concept_um5_wdx_wdb .concept}

This topic describes the limits that Alibaba Cloud CDN imposes on domains.

## Domain filing {#section_r1h_lgx_wdb .section}

We recommend that you use Alibaba Cloud ICP Filing to file domains.

## Content moderation {#section_8ow_zg9_l29 .section}

All domains connected to CDN must go through content moderation. The unauthorized content that CDN does not allow includes but is not limited to the following:

-   Content that is inaccessible or does not have any substantial information
-   Unauthorized games
-   Legendary and card games
-   Unauthorized applications
-   P2P financial websites
-   Lottery websites
-   Illegal hospital and pharmaceutical websites
-   Explicit content

**Note:** 

-   If any of the preceding unauthorized content is detected in a domain, CDN immediately stops and forbids the domain. In certain circumstances, CDN even may forbid all domains under your Alibaba Cloud account forever. In such case, you shall bear any possible risks that may arise.
-   If you connect a wildcard domain \(for example, `*.example.com`\) to Alibaba Cloud CDN and a specific domain \(for example, `a.example.com`\) contains unauthorized content, Alibaba Cloud CDN stops and forbids the wildcard domain.

## Limits on domains {#section_dop_a6z_3lb .section}

|Item|Limit|
|:---|:----|
|Domains|Each Alibaba Cloud account supports up to 50 domains. If the average daily bandwidth required in your domains during peak hours exceeds 50 MB and adding domains to your Alibaba Cloud account does not incur business risks, you can [open a ticket](https://workorder.console.aliyun.com/console.htm?lang=&accounttraceid=3c62958a-b7f1-4439-b87b-5f59ed3e9704#/ticket/add?productCode=cdn) to apply for an increase in the number of domains that are allowed.|
|IP origins|By default, each domain supports up to 10 origins that use IP addresses.|
|Cache and refresh operations| -   URL refresh: 2000/day/account
-   Directory refresh: 100/day/account

 |

## Domain recycling rules {#section_6dr_hsy_1f5 .section}

|Scenario|Action|Solution|
|:-------|:-----|:-------|
|If your domain has not been visited for over 90 days \(including the situation where the domain runs properly\)|CDN automatically stops the domain but retains the records related to the domain.|Enable the domain.|
|If your domain has been stopped for more than 120 days \(including the situation where the domain fails the content moderation\)|CDN automatically deletes the records related to the domain.|Re-add the domain.|

