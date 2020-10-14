---
keyword: [Alibaba Cloud CDN library, CDN console navigation, CDN console pages]
---

# Features

In the Alibaba Cloud Content Delivery Network \(CDN\) console, you can configure domain names and perform other basic operations. You can also view resource monitoring data and analyze data in real time. The Alibaba Cloud CDN console provides you with your billing information and allows you to change the billing method based on your business requirements. This topic describes the layout of the Alibaba Cloud CDN console and the domain management features of Alibaba Cloud CDN.

**Note:** To help you understand and obtain up-to-date information about Alibaba Cloud CDN, operations that you can perform in the console are classified into domain management features and service management features.

## Console layout

The following figure shows the layout of the Alibaba Cloud CDN console.

![Alibaba Cloud CDN console](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/2950462061/p54228.png)

The following figure shows the layout of the Alibaba Cloud CDN console.

|NO.|Section|Description|
|---|-------|-----------|
|1|Left-side navigation pane|The navigation pane of the Alibaba Cloud CDN console. For more information, see [Domain management features](#section_2le_by2_8r4).|
|2|Basic information|Displays the usage of each billing item based on the billing method of your CDN service. For more information, see [Pricing of basic services](/intl.en-US/Pricing/Billing method/Pricing of basic services.md).|
|3|Popular services|Displays popular features of Alibaba Cloud CDN.|
|4|User guide|Displays the links of Alibaba Cloud CDN documents. For more information, see [CDN Learning Path](https://www.alibabacloud.com/zh/getting-started/learningpath/cdn?spm=a2796.7980202.1167821.2.44fb5f45Bo5QjO).|
|5|Billing method|Displays the billing method of your CDN service. You can also change the billing method as needed. For more information, see [Pricing of basic services](/intl.en-US/Pricing/Billing method/Pricing of basic services.md) and [Billing of value-added services](/intl.en-US/Pricing/Billing method/Billing of value-added services.md).|
|6|Resource plans|Displays the resource plans that you have purchased. For more information, see [Resource plans](/intl.en-US/Service Management/Monitoring and Usage Analytics/Usage Query/Resource plans.md).|
|7|Total domain names|Allows you to manage accelerated domain names, add domain names, and perform the refresh or prefetch operation.|
|8|Related products|Displays related products and other relevant information.|
|9|Domain names ranked by network traffic|Displays the top five accelerated domain names ranked by network traffic.|

## Domain management features

The following table lists the domain management features.

|Feature|Reference|Description|Default value|
|-------|---------|-----------|-------------|
|Batch copying|[Copy configurations](/intl.en-US/Domain Management/Copy configurations.md)|Copies one or more specific configurations of an accelerated domain name to another one or more accelerated domain names.|None|
|Alert settings|[Set an alert rule](/intl.en-US/Domain Management/Set an alert rule.md)|Monitors accelerated domains based on metrics, such as peak bandwidth, proportions of HTTP status codes, hit ratios, outbound Internet traffic, and queries per second. When an alert rule is triggered, Cloud Monitor sends notifications to you through SMS messages or emails.|None|
|Tag management|[Attach tags to a domain name](/intl.en-US/Domain Management/Tags/Attach tags to a domain name.md)|Attaches tags to a domain name or group domain names by tag.|None|
|[Use tags to manage domain names](/intl.en-US/Domain Management/Tags/Use tags to manage domain names.md)|Filters or groups domain names based on specific tags.|None|
|[Query domain names by tag](/intl.en-US/Domain Management/Tags/Query domain names by tag.md)|Filters domain names and queries data based on specific tags.|None|
|Basic settings|[Modify basic information](/intl.en-US/Domain Management/Basic settings/Modify basic information.md)|Modifies the accelerated region.|None|
|[Configure an origin server](/intl.en-US/Domain Management/Basic settings/Configure an origin.md)|Modifies the origin information.|None|
|Back-to-origin settings|[Configure an origin host](/intl.en-US/Domain Management/Back-to-origin settings/Configure an origin host.md)|Modifies the domain name of the origin host.|Enable|
|[Configure the origin protocol policy](/intl.en-US/Domain Management/Back-to-origin settings/Configure the origin protocol policy.md)|Alibaba Cloud CDN communicates with origin servers based on the specified origin protocol policy. If you specify the Follow policy, Alibaba Cloud CDN communicates with origin servers based on the protocol of the request sent from the client.|Disable|
|[Enable private bucket back-to-origin authorization](/intl.en-US/Domain Management/Back-to-origin settings/Enable private bucket back-to-origin authorization.md)|Grants Alibaba Cloud CDN permissions to access the private Object Storage Service \(OSS\) bucket that is used as the origin server.|Disable|
|[Configure an origin SNI](/intl.en-US/Domain Management/Back-to-origin settings/Configure an origin SNI.md)|Sets a Server Name Indication \(SNI\) value to specify the requested domain name in an HTTPS back-to-origin request. You must enable this feature when the IP address of the origin server is mapped to multiple domain names.|Disable|
|[Customize an HTTP header](/intl.en-US/Domain Management/Back-to-origin settings/Customize an HTTP header.md)|Adds or removes HTTP headers when HTTP requests are redirected to origin servers.|Disable|
|[Set the origin request timeout period](/intl.en-US/Domain Management/Back-to-origin settings/Set the origin request timeout.md)|Sets the maximum amount of time that Alibaba Cloud CDN waits for a response after it redirects a request to the origin server. If Alibaba Cloud CDN does not receive a response before the timeout period ends, the connection between the CDN node and the origin server is closed.|30 seconds|
|Cache settings|[Create a cache expiration rule](/intl.en-US/Domain Management/Cache settings/Create a cache expiration rule.md)|Customizes cache expiration rules for specific resources.|None|
|[Create a status code expiration rule](/intl.en-US/Domain Management/Cache settings/Create a status code expiration rule.md)|Customizes expiration rules for the status codes of the resources in the specified directories or with the specified file extensions.|None|
|[Create an HTTP header](/intl.en-US/Domain Management/Cache settings/Customize an HTTP response header.md)|Customizes HTTP request headers. Alibaba Cloud CDN provides 10 types of HTTP request header.|None|
|[Customize an error page](/intl.en-US/Domain Management/Cache settings/Customize an error page.md)|Customizes complete URLs to which requests are redirected based on the HTTP or HTTPS status code.|404|
|[Configure a rewrite rule](/intl.en-US/Domain Management/Cache settings/Configure a rewrite rule.md)|Modifies request URIs and redirects them to the specified URIs based on the 302 status code.|None|
|HTTPS secure acceleration|[Configure an SSL certificate](/intl.en-US/Domain Management/HTTPS/Configure an SSL certificate.md)|Provides an end-to-end HTTPS secure acceleration solution. You can enable the secure acceleration mode and upload an SSL certificate and the private key for an accelerated domain name. This feature also allows you to view, disable, enable, or modify the certificate.|Disable|
|[Enable HTTP/2](/intl.en-US/Domain Management/HTTPS/Enable HTTP/2.md)|Enables the binary protocol HTTP/2 to provide multiple benefits including scalability, security, multiplexing, and header compression.|Disable|
|[Enable force redirect](/intl.en-US/Domain Management/HTTPS/Enable force redirect.md)|Redirects requests from clients to L1 nodes as HTTP or HTTPS requests.|Disable|
|[Configure TLS](/intl.en-US/Domain Management/HTTPS/Configure TLS.md)|Enables a TLS protocol version for an accelerated domain name to enable TLS handshakes. TLS 1.0, TLS 1.1, TLS 1.2, and TLS 1.3 are supported.|Disable|
|[Configure HSTS](/intl.en-US/Domain Management/HTTPS/Configure HSTS.md)|Configures HTTP Strict Transport Security \(HSTS\) to allow clients such as browsers to use only HTTPS to connect to the server.|Disable|
|Access control|[Configure hotlink protection](/intl.en-US/Domain Management/Access control/Configure hotlink protection.md)|Configures a referer blacklist or whitelist to identify and filter visitors. Only authorized users have access to resources on CDN nodes.|Disable|
|[Configure URL signing](/intl.en-US/Domain Management/Access control/Business type/Configure URL signing.md)|Configures URL authentication to prevent unauthorized downloads of resources on the origin server.|Disable|
|[Configure an IP address blacklist or whitelist](/intl.en-US/Domain Management/Access control/Configure an IP address blacklist or whitelist.md)|Configures an IP address blacklist or whitelist to identify and filter visitors. Only authorized users have access to resources on CDN nodes.|Disable|
|[Configure a User-Agent blacklist or whitelist](/intl.en-US/Domain Management/Access control/Configure a User-Agent blacklist or whitelist.md)|Configures a User-Agent blacklist or whitelist to identify and filter visitors. Only authorized users have access to resources on CDN nodes.|Disable|
|Performance optimization|[Configure HTML optimization](/intl.en-US/Domain Management/Performance optimization/Configure HTML optimization.md)|Compresses and removes HTML redundant content, such as space characters and carriage return characters, to reduce the file size.|Disable|
|[Configure intelligent compression](/intl.en-US/Domain Management/Performance optimization/Configure intelligent compression.md)|Intelligently compresses multiple formats of content to reduce the size of transmitted content.|Disable|
|[Configure Brotli compression](/intl.en-US/Domain Management/Performance optimization/Configure Brotli compression.md)|Compresses static text files to reduce the size of transmitted content and accelerate content delivery.|Disable|
|[Configure parameter filtering](/intl.en-US/Domain Management/Performance optimization/Configure parameter filtering.md)|Specifies whether Alibaba Cloud CDN retains parameters that follow a question mark \(`?`\) in the URL of a back-to-origin request. You can enable this feature when the URL includes a question mark and parameters.|Disable|
|Advanced settings|[Configure bandwidth cap](/intl.en-US/Domain Management/Advanced settings/Configure bandwidth cap.md)|Specifies a maximum bandwidth value. If the average bandwidth measured at five-minute intervals exceeds the maximum bandwidth, the accelerated domain name is disabled automatically. This can protect the accelerated domain name. In this case, all requests are redirected to the origin server.|Disable|
|Video-related settings|[Configure object chunking](/intl.en-US/Domain Management/Video Service Configuration/Configure object chunking.md)|Enables Alibaba Cloud CDN to retrieve content from origin servers based on HTTP range requests. This reduces the back-to-origin data usage and response time.|Disable|
|[Video seeking](/intl.en-US/Domain Management/Video Service Configuration/Video seeking.md)|Allows you to seek through video or audio without affecting the playback quality.|Disable|
|[Configure audio or video preview](/intl.en-US/Domain Management/Video Service Configuration/Configure audio or video preview.md)|Allows you to preview audio and video content.|Disable|
|[Audio extraction](/intl.en-US/Domain Management/Video Service Configuration/Audio extraction.md)|Extracts audio data from a video file and returns the audio data to the client. This reduces data usage.|Disable|
|IPv6|[Configure IPv6 settings](/intl.en-US/Domain Management/Configure IPv6 settings.md)|Allows IPv6 clients to send requests to Alibaba Cloud CDN over IPv6. Alibaba Cloud CDN can also bring the IPv6 information of the clients in back-to-origin requests.|Disable|

