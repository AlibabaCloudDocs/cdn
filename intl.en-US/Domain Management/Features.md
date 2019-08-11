# Features {#concept_tvm_vhx_wdb .concept}

The Alibaba Cloud CDN console not only allows you to complete basic operations such as domain name configuration, but also provides resource monitoring services for real-time data analysis. You can also learn about your billing information and change the billing method at any time. This topic describes the CDN console and the domain management features.

## Console guide {#section_75m_vfk_6p8 .section}

The following figure shows the CDN console interface.

![CDN console](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5118/156552078954228_en-US.png)

The following table describes the CDN console interface.

|No.|Element|Description|
|---|-------|-----------|
|1|Left-side navigation pane|Displays the navigation pane for domain management. For more information, see [Domain management features](#section_2le_by2_8r4).|
|2|Basic data|Displays the usage status of each billing item based on the billing method of your CDN service. For more information, see [Basic Service](../../../../intl.en-US/Pricing/Billing method/Basic Service.md#).|
|3|Hot services|Shows you how to quickly access the frequently used CDN features.|
|4|CDN user guide|Displays the links of the CDN help documents to which you can refer. For more information, see [CDN Learning Path](https://www.alibabacloud.com/zh/getting-started/learningpath/cdn?spm=a2796.7980202.1167821.2.44fb5f45Bo5QjO).|
|5|Configure log storage|The log storage service uses Function Compute to store logs for a long time period. For more information, see [Configure log storage](../../../../intl.en-US/Service Management/Log Management/Configure log storage.md#).|
|6|Billing method|Displays the billing method you have selected. You can also modify the billing method as needed. For more information, see [Basic Service](../../../../intl.en-US/Pricing/Billing method/Basic Service.md#) and [Value-added service](../../../../intl.en-US/Pricing/Billing method/Value-added service.md#).|
|7|All domains|Allows you to quickly manage the existing domains, add domains, and perform the refresh or preload operation.|
|8|Other acceleration products|Displays CDN-related products.|
|9|Traffic-based domain ranking|Displays top five CDN domains by traffic.|

## Domain management features {#section_2le_by2_8r4 .section}

The following table lists the CDN domain management features.

|Feature|Reference|Description|Default value|
|-------|---------|-----------|-------------|
|Bulk copying|[Copy configurations](intl.en-US/Domain Management/Copy configurations.md#)|Allows you to copy one or more configurations of a CDN domain to another one or more CDN domains.|None|
|Alert settings|[Set an alarm rule](intl.en-US/Domain Management/Set an alarm rule.md#)|Monitors CDN domains by using the following metrics: peak bandwidth, 4xx code proportion, 5xx code proportion, hit rate, Internet downstream traffic, and QPS. When an alert rule is triggered, Alibaba Cloud CloudMonitor sends an alert message through SMS or email based on the settings.|None|
|Tag management|[Attach tags to a domain name](intl.en-US/Domain Management/Tags/Attach tags to a domain name.md#)|Allows you to add tags to a domain name or group domain names by tags.|None|
|[Manage domain names by tag](intl.en-US/Domain Management/Tags/Manage domain names by tag.md#)|Allows you to use tags to quickly filter domain names for group management.|None|
|[Query domain names by tag](intl.en-US/Domain Management/Tags/Query domain names by tag.md#)|Allows you to use tags to quickly filter domain names for data query.|None|
|Basic information settings|[Modify basic information](intl.en-US/Domain Management/Basic settings/Modify basic information.md#)|Allows you to modify the accelerated region.|None|
|[Modify origin information](intl.en-US/Domain Management/Basic settings/Modify origin information.md#)|Allows you to modify the origin information.|None|
|Back-to-origin settings|[Configure an origin host](intl.en-US/Domain Management/Content back-to-source settings/Configure an origin host.md#)|Allows you to modify the domain name of the origin host.|Enabled|
|[Configure an origin protocol](intl.en-US/Domain Management/Content back-to-source settings/Configure an origin protocol.md#)|CDN communicates with your origin according to the specified origin protocol policy. If you specify the Follow policy, CDN communicates with your origin over HTTP or HTTPS, depending on the protocol of the client request.|Disabled|
|[Configure the private bucket access control](intl.en-US/Domain Management/Content back-to-source settings/Enable private bucket back-to-origin authentication.md#)|Grants CDN permissions to access the specified private OSS bucket that serves as the origin.|Disabled|
|[Back-to-origin SNI](intl.en-US/Domain Management/Content back-to-source settings/Back-to-origin SNI.md#)|If you have bound your origin IP address to multiple domain names, you must specify the SNI of a specific domain when CDN nodes access your origin site over HTTPS.|Disabled|
|[Customize an origin HTTP header](intl.en-US/Domain Management/Content back-to-source settings/Customize an origin HTTP header.md#)|If you configure CDN to use HTTP to communicate with your origin, you can add or remove HTTP header fields.|Disabled|
|[Set the origin request timeout period](intl.en-US/Domain Management/Content back-to-source settings/Set the origin request timeout period.md#)|Allows you to set the maximum amount of time that CDN waits for a response after it forwards a request to an origin. When CDN does not receive any response before the timeout period expires, the connection between the CDN node and the origin is terminated.|30 seconds|
|Cache settings|[Configure cache expiration](intl.en-US/Domain Management/Cache settings/Create a cache expiration rule.md#)|Allows you to customize cache expiration rules for specified resources.|None|
|[Set HTTP code expiration time](intl.en-US/Domain Management/Cache settings/Set HTTP code expiration time.md#)|Allows you to customize the expiration rules for the status codes of the resources that are specified by directory or file extension.|None|
|[Set the HTTP header](intl.en-US/Domain Management/Cache settings/Create an HTTP header.md#)|Allows you to customize the HTTP request header. Currently, 10 HTTP request header fields are available for customization.|None|
|[Customize an error page](intl.en-US/Domain Management/Cache settings/Customize an error page.md#)|Allows you to customize a complete URL to redirect for an HTTP or HTTPS response code.|404|
|[Rewrite](intl.en-US/Domain Management/Cache settings/Rewrite.md#)|Allows you to modify a request URI and perform a 302 redirect to the specified target URI.|None|
|HTTPS secure acceleration|[Configure HTTPS certificates](intl.en-US/Domain Management/HTTPS Acceleration/Configure HTTPS certificates.md#)|Provides an end-to-end HTTPS secure acceleration solution. You only need to enable the secure acceleration mode and then upload the certificate and private key for a CDN domain. This feature also allows you to view, disable, enable, or modify certificates.|Disabled|
|[Enable HTTP/2](intl.en-US/Domain Management/HTTPS Acceleration/Enable HTTP__2.md#)|The HTTP/2 protocol is binary and has multiple advantages including scalability, security, multiplexing, and header compression.|Disabled|
|[Enable Force Redirect](intl.en-US/Domain Management/HTTPS Acceleration/Enable Force Redirect.md#)|If HTTP secure acceleration is enabled, you can configure CDN to forcibly redirect user requests to HTTPS or HTTP.|Disabled|
|[Configure TLS](intl.en-US/Domain Management/HTTPS Acceleration/Configure TLS.md#)|After a TLS protocol version is enabled, the TLS handshake is enabled for the CDN domain. Currently, only TLS version 1.0, TLS version 1.1, TLS version 1.2, and TLS version 1.3 are supported.|Disabled|
|[Configure HSTS](intl.en-US/Domain Management/HTTPS Acceleration/Configure HSTS.md#)|HSTS is used to force clients \(such as browsers\) to use HTTPS to create connections with the server.|Disabled|
|Access control|[Configure hotlinking protection](intl.en-US/Domain Management/Access Control Settings/Anti-leech.md#)|Allows you to configure a referer blacklist or whitelist to identify and filter visitors.|Disabled|
|[Configure URL authentication](intl.en-US/Domain Management/Access Control Settings/Business type/Authentication configuration.md#)|Allows you to configure URL authentication to prevent unauthorized downloads and theft of the resources on the site.|Disabled|
|[Configure an IP blacklist or whitelist](intl.en-US/Domain Management/Access Control Settings/IP Blacklist and Whitelist.md#)|Allows you to configure an IP blacklist or whitelist to identify and filter visitors.|Disabled|
|[UA blacklist and whitelist](intl.en-US/Domain Management/Access Control Settings/UA blacklist and whitelist.md#)|Allows you to configure a User-Agent blacklist or whitelist to identify and filter visitors.|Disabled|
|Performance optimization|[Configure HTML optimization](intl.en-US/Domain Management/Performance Optimization settings/Page Optimization.md#)|Compresses and removes HTML redundant content, such as blank lines and carriage return characters, to reduce the file size.|Disabled|
|[Configure intelligent compression](intl.en-US/Domain Management/Performance Optimization settings/Brotli Compression.md#)|Supports intelligent compression for content in multiple formats to reduce the size of user transmitted content.|Disabled|
|[Brotli compression](intl.en-US/Domain Management/Performance Optimization settings/Brotli compression.md#)|If you want to compress static text files, you can enable this feature. It can reduce the size of the transmitted content and accelerate content delivery.|Disabled|
|[Configure parameter filtering](intl.en-US/Domain Management/Performance Optimization settings/Filter Parameter.md#)|After a CDN node receives a URL request that includes the question mark \(`?`\) and Parameters, it determines whether the URL request needs to be rerouted to the origin site with the parameters.|Disabled|
|Advanced settings|[Configure a bandwidth cap](intl.en-US/Domain Management/Advanced settings/Peak Bandwidth.md#)|Allows you to set the maximum bandwidth value for average bandwidth measured during each statistical cycle \(5 minutes\). To protect the CDN domain, the domain automatically becomes disabled when the average bandwidth exceeds the maximum value. In this situation, all requests are forwarded to the origin site.|Disabled|
|Video-related settings|[Configure object chunking](intl.en-US/Domain Management/Video Service Configuration/Back-to-origin of range.md#)|Reduces back-to-origin traffic consumption and shortens resource response time.|Disabled|
|[Configure video seeking](intl.en-US/Domain Management/Video Service Configuration/Drag__Drop Playback.md#)|After this feature is enabled, you can drag and drop the playback progress of an audio or video content without affecting the playback effect.|Disabled|

