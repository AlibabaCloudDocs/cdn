---
keyword: [CDN, basic features]
---

# Brief introduction to basic features of Alibaba Cloud CDN

After you activate the Alibaba Cloud Content Delivery Network \(CDN\) service to accelerate content delivery, you can configure Alibaba Cloud CDN based on business requirements in the console or by calling API operations. This topic describes the layout of the Alibaba Cloud CDN console, operations that you can perform in the console, and features that you can configure in the console.

## Layout of the console

The following figure shows the Alibaba Cloud CDN console.

![The Alibaba Cloud International site](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9334528951/p68637.png)

|No.|Benefit|
|---|-------|
|1|Left-side navigation pane: displays features of Alibaba Cloud CDN that can be configured in the console.|
|2|Resource usage: displays the usage of Alibaba Cloud CDN resources.|
|3|Quick start: displays popular features, user guide, and FAQ.|
|4|Resources and billing: displays the current billing method and all resources under your account.|
|5|Related products: displays related products and other relevant information.|

## Functions of the console

Alibaba Cloud CDN supports domain management and service management. You can configure domain names and query, monitor, or configure CDN resources in the console.

The following table lists the domain management features.

|Feature|Reference|
|-------|---------|
|Copy one or more specific configurations of an accelerated domain name to another one or more accelerated domain names.|[Copy configurations](/intl.en-US/Domain Management/Copy configurations.md)|
|Monitor accelerated domains based on metrics, such as peak bandwidth, proportions of HTTP status codes, and hit ratios.|[Set an alert rule](/intl.en-US/Domain Management/Set an alert rule.md)|
|Attach tags to a domain name or group domain names by tag. You can use the tags to filter domain names, manage groups, and query data.|[Attach tags to a domain name](/intl.en-US/Domain Management/Tags/Attach tags to a domain name.md), [Use tags to manage domain names](/intl.en-US/Domain Management/Tags/Use tags to manage domain names.md), and [Query data of domain names by tag](/intl.en-US/Domain Management/Tags/Query data of domain names by tag.md)|
|Modify the accelerated region or origin information.|[Modify basic information](/intl.en-US/Domain Management/Basic settings/Modify basic information.md) and [Configure an origin server](/intl.en-US/Domain Management/Basic settings/Configure an origin server.md)|
|Modify the domain name of an origin server, set the maximum amount of time that CDN waits for a response after a request is redirected to the origin server, and configure other back-to-origin features.|[Configure an origin host](/intl.en-US/Domain Management/Back-to-origin settings/Configure an origin host.md), [Configure the origin protocol policy](/intl.en-US/Domain Management/Back-to-origin settings/Configure the origin protocol policy.md), [Enable private bucket back-to-origin authorization](/intl.en-US/Domain Management/Back-to-origin settings/Enable private bucket back-to-origin authorization.md), [Configure an origin SNI](/intl.en-US/Domain Management/Back-to-origin settings/Configure an origin SNI.md), [Customize an HTTP header](/intl.en-US/Domain Management/Back-to-origin settings/Customize an HTTP header.md), and [Set the origin request timeout period](/intl.en-US/Domain Management/Back-to-origin settings/Set the origin request timeout.md)|
|Customize cache expiration rules for specific resources, customize the expiration rules for the status codes of the resources in the specified directories or with the specified file extensions, associate full URLs with error codes that are carried in HTTP or HTTPS responses, and configure other cache features.|[Create a cache expiration rule](/intl.en-US/Domain Management/Cache settings/Create a cache expiration rule.md), [Create a status code expiration rule](/intl.en-US/Domain Management/Cache settings/Create a status code expiration rule.md), [Create an HTTP header](/intl.en-US/Domain Management/Cache settings/Create an HTTP header.md), [Customize an error page](/intl.en-US/Domain Management/Cache settings/Customize an error page.md), and [Configure a rewrite rule](/intl.en-US/Domain Management/Cache settings/Configure a rewrite rule.md)|
|Require an end-to-end HTTPS secure acceleration solution.|[Configure an SSL certificate](/intl.en-US/Domain Management/HTTPS/Configure an SSL certificate.md), [Enable HTTP/2](/intl.en-US/Domain Management/HTTPS/Enable HTTP/2.md), [Enable force redirect](/intl.en-US/Domain Management/HTTPS/Enable force redirect.md), [Configure TLS](/intl.en-US/Domain Management/HTTPS/Configure TLS.md), and [Configure HSTS](/intl.en-US/Domain Management/HTTPS/Configure HSTS.md)|
|Identify and filter visitors to prevent unauthorized access to resources on an origin server.|[Configure hotlink protection](/intl.en-US/Domain Management/Access control/Configure hotlink protection.md), [Configure URL signing](/intl.en-US/Domain Management/Access control/Business type/Configure URL signing.md), [Configure an IP blacklist or whitelist](/intl.en-US/Domain Management/Access control/Configure an IP blacklist or whitelist.md), and [Configure a User-Agent blacklist or whitelist](/intl.en-US/Domain Management/Access control/Configure a User-Agent blacklist or whitelist.md)|
|Optimize service performance to accelerate content delivery.|[Configure HTML optimization](/intl.en-US/Domain Management/Performance optimization/Configure HTML optimization.md), [Configure intelligent compression](/intl.en-US/Domain Management/Performance optimization/Configure intelligent compression.md), [Configure Brotli compression](/intl.en-US/Domain Management/Performance optimization/Configure Brotli compression.md), and [Configure parameter filtering](/intl.en-US/Domain Management/Performance optimization/Configure parameter filtering.md)|
|Improve resource access efficiency, secure data transmission, and protect accelerated domains.|[Configure bandwidth cap](/intl.en-US/Domain Management/Advanced settings/Configure bandwidth cap.md)|
|Set audio and video files to improve content delivery.|[Configure object chunking](/intl.en-US/Domain Management/Video Service Configuration/Configure object chunking.md), [Configure video seeking](/intl.en-US/Domain Management/Video Service Configuration/Video seeking.md), [Configure audio or video preview](/intl.en-US/Domain Management/Video Service Configuration/Configure audio or video preview.md), and [Audio extraction](/intl.en-US/Domain Management/Video Service Configuration/Audio extraction.md)|
|Enable IPv6 communication clients and Alibaba Cloud CDN.|[Configure IPv6 settings](/intl.en-US/Domain Management/Configure IPv6 settings.md)|

The following table lists the service management features.

|Feature|Reference|
|-------|---------|
|Obtain up-to-date information about Alibaba Cloud CDN by using resource monitoring and real-time monitoring, and query and manage bills and other relevant data.|[Monitor data](/intl.en-US/Service Management/Monitoring and Usage Analytics/Monitor data.md), [View statistics](/intl.en-US/Service Management/Monitoring and Usage Analytics/Use the statistical analysis function.md), [Query resource usage information](/intl.en-US/Service Management/Monitoring and Usage Analytics/Usage Query/Query resource usage information.md), [Query bills](/intl.en-US/Service Management/Monitoring and Usage Analytics/Usage Query/Query bills.md), [Export a bill](/intl.en-US/Service Management/Monitoring and Usage Analytics/Usage Query/Export a bill.md), [Export billing details](/intl.en-US/Service Management/Monitoring and Usage Analytics/Usage Query/Export billing details.md), and [Resource plans](/intl.en-US/Service Management/Monitoring and Usage Analytics/Usage Query/Resource plans.md)|
|Retrieve the latest resources from an origin server, and prefetch frequently requested resources during off-peak hours.|[Configure the refresh and prefetch features](/intl.en-US/Service Management/Refresh and preload/Configure the refresh and prefetch features.md)|
|Manage and analyze real-time logs and locate issues at the earliest opportunity.|[Download logs](/intl.en-US/Service Management/Log Management/Download logs.md) and [Log storage](/intl.en-US/Service Management/Log Management/Log storage.md)|
|Check whether an IP address belongs to an Alibaba Cloud CDN node.|[Diagnostic tools](/intl.en-US/Service Management/Diagnostic tools.md)|

## Operations in the console

Before you perform operations described in this topic, make sure that you have [created an Alibaba Cloud account](https://account.aliyun.com/register/register.htm) and [passed real-name verification](https://account.console.aliyun.com/#/auth/home).

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).
2.  In the left-side navigation pane, you can perform the following steps to go to a specific page:
    -   Choose **Domain Names** \> **Manage** to manage a domain name and configure features.
    -   Click **Monitoring & Usage Analytics**, **Refresh & Prefetch**, **Logs**, **Tools**, or **Dynamic Route for CDN** to configure features based on your business requirements.

## Reference

You can read the following documents to learn more about the features of Alibaba Cloud CDN:

-   [Release notes for Alibaba Cloud CDN](/intl.en-US/.md)
-   [Overview](/intl.en-US/Quick Start/Overview.md)
-   [API overview](/intl.en-US/New API Reference/Introduction to the API.md)

