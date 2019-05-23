# Function overview {#concept_tvm_vhx_wdb .concept}

## HTTPS secure acceleration {#section_l1w_tlx_wdb .section}

|Function|Description|Default|
|:-------|:----------|:------|
|[HTTPS secure acceleration](intl.en-US/User Guide/Domain Names/HTTPS Acceleration/HTTPS Secure Acceleration.md#)|Provides a full link HTTPS secure acceleration scheme, just upload the CDN domain name certificate/private key after you activate secure acceleration mode, and supports viewing, disabling, enabling, editing of certificates.|Disabled|
|[Force redirect](intl.en-US/User Guide/Domain Names/HTTPS Acceleration/Force Redirect.md#)|When the "HTTPS secure acceleration" is enabled, the CDN domain name supports custom settings, and redirect the user's original request in a forcible way.|Disabled|
|[HTTP/2](https://www.alibabacloud.com/help/doc-detail/59894.htm)|HTTP/2 can be seen as an advanced edition of HTTP/1.1. It has many advantages, including binary protocol, content security, multiplexing, header compression, and so on.|Disabled|
|[TLS](https://www.alibabacloud.com/help/doc-detail/95838.htm)|TLS is a cryptographic protocol designed to ensure communication security and data integrity of a computer network.|TLS Version 1.0, TLS Version 1.1, and TLS Version 1.2 are enabled by default.|
|[HSTS](https://www.alibabacloud.com/help/doc-detail/95839.htm)|HSTS is specified in RFC 6797. HSTS instructs clients, such as a browser, that a domain can only be accessed by using HTTPS.|Disabled|

## Back-to-source settings {#section_rq4_5lx_wdb .section}

|Function|Description|Default|
|:-------|:----------|:------|
|[Back-to-origin HOST](intl.en-US/User Guide/Domain Names/Content back-to-source settings/Back-to-origin HOST.md#)|Specifies the host domain name that a CDN node accesses in the back-to-source process. Three options are available: CDN domain name, original site domain name, and custom domain name.|CDN domain name|
|[Back-to-source with the same protocol](intl.en-US/User Guide/Domain Names/Content back-to-source settings/Back-to-origin with the same protocol.md#)|Back-to-source requests for resources use exactly the same protocol as used by the client to request the resources.|Disabled|
|[Private bucket back-to-origin authentication](https://www.alibabacloud.com/help/doc-detail/57653.htm)|After authentication is successful and authentication configuration is enabled, domain names enabled with private bucket authentication have the permission to access the private bucket.|Disabled|

## Cache settings {#section_j4q_5lx_wdb .section}

|Function|Description|Default|
|:-------|:----------|:------|
|[Cache expiration time](intl.en-US/User Guide/Domain Names/Node Cache Settings/Cache configuration.md#)|Customizes cache expiration rules for specified resources.|Disabled|
|[Setting the HTTP Request Header](intl.en-US/User Guide/Domain Names/Node Cache Settings/Set the HTTP Response Header.md#)|Sets an HTTP request header. Nine parameters are currently available for HTTP request header customization.|Disabled|
|[Custom 404 page](intl.en-US/User Guide/Domain Names/Node Cache Settings/Customize the 404 page.md#)|Available in three options: default 404, public welfare 404, custom 404|Default 404 page|

## Access control {#section_vc4_cmx_wdb .section}

|Function|Description|Default|
|:-------|:----------|:------|
|[Anti-leech](intl.en-US/User Guide/Domain Names/Access Control Settings/Anti-leech.md#)|Configures a referer blacklist or whitelist to identify and filter visitors.|Disabled|
|[URL authentication](https://www.alibabacloud.com/help/doc-detail/85117.htm)|Uses URL authentication methods to protect resources on an origin site.|Disabled|
|[IP blacklist](intl.en-US/User Guide/Domain Names/Access Control Settings/IP Blacklist and Whitelist.md#)|Configures the access IP blacklist to identify and filter visitors.|Disabled|

## Performance optimization {#section_ev4_cmx_wdb .section}

|Function|Description|Default|
|:-------|:----------|:------|
|[Page optimization](intl.en-US/User Guide/Domain Names/Performance Optimization settings/Page Optimization.md#)|Compresses and removes useless blank lines and carriage return characters to effectively reduce the page size.|Disabled|
|[Smart compression](intl.en-US/User Guide/Domain Names/Performance Optimization settings/Smart Compression.md#)|Supports smart compression for content in multiple formats to effectively reduce the size of user transmitted content.|Disabled|
|[Filter parameter](intl.en-US/User Guide/Domain Names/Performance Optimization settings/Filter Parameter.md#)|Removes parameters after ? in a URL request during the back-to-source process.|Disabled|

## Video-related settings {#section_is2_hmx_wdb .section}

|Function|Description|Default|
|:-------|:----------|:------|
|[Back-to-source of range](intl.en-US/User Guide/Domain Names/Video Service Configuration/Back-to-origin of range.md#)|Allows a user to notify an origin site server to return partial content within a specified range. This function helps with accelerated delivery of large files.|Disabled|
|[Drag/drop playback](intl.en-US/User Guide/Domain Names/Video Service Configuration/Drag__Drop Playback.md#)|Enables random drag or drop playback in a video or audio on-demand scenario.|Disabled|
|[Notify\_URL](intl.en-US/User Guide/Domain Names/Video Service Configuration/Notify_URl setting.md#)|\(Applicable to Live\) Real-time information callback of stream status, promptly notifies users about the operation results of streaming or stream disconnection.|Disabled|

## Advanced settings {#section_vbh_cqm_2gb .section}

|Function|Description|Default|
|--------|-----------|-------|
|[Peak Bandwidth](https://www.alibabacloud.com/help/doc-detail/54954.htm)|If the average bandwidth exceeds the maximum, the domain name automatically goes offline to protect your domain name security|Disabled|

## Refresh and preload {#section_s3k_fxm_2gb .section}

|Function|Description|Default|
|:-------|:----------|:------|
|[URL refresh and preload](intl.en-US/User Guide/Refresh and Preload.md#)| -   Forces specified files on the CDN Cache node to expire in order to update back-to-source again.
-   Actively pushes content from the origin site to the L2 Cache node. Upon first access, you can directly hit cache to relieve pressure on the origin site.

 |Enabled|

## **Data monitoring and statistical analysis** {#section_vfc_kwm_2gb .section}

|Function|Description|Default|
|:-------|:----------|:------|
|[Data monitoring](intl.en-US/User Guide/Data monitoring.md#)|You can select Domain Name, Region, Operator, Time Granularity \(1 minute, 5 minute or 1 hour\) and Time Range \(Today, Yesterday, 7 Days, 30 Days or Custom\) to view the specific condition.|Enabled|
|[Statistical analysis](intl.en-US/User Guide/Statistical Analysis.md#)|In Statistical Analysis, you can check data of PV and UV, Area and ISP, Domain Name Rankings, Popular Referer, and Popular URLs.|Enabled|

## **Usage query** {#section_dqq_dxm_2gb .section}

|Function|Description|Default|
|:-------|:----------|:------|
|[Usage query](intl.en-US/User Guide/Usage Query/Usage Query.md#)|You can use this function to obtain the actual usage of traffic, bandwidth, or requests during a certain period.|Enabled|
|[Billing export](intl.en-US/User Guide/Usage Query/Billing export.md#)|You can export actual usage data by day or by month, so as to compare it with the report output from the billing center.|Enabled|
|[Detail data export](intl.en-US/User Guide/Usage Query/Detail Data Export.md#)|You can export detail data for traffic/bps data or request times, so that you can calculate or review the usage you actually paid for.|Enabled|

## Log management {#section_y3h_gxm_2gb .section}

|Function|Description|Default|
|:-------|:----------|:------|
|[Log Downloading](intl.en-US/User Guide/Log Management/Log Downloading.md#)|You can download the log files within 1 month.|Enabled|

## Other settings {#section_ihf_hmx_wdb .section}

|Function|Description|Default|
|:-------|:----------|:------|
|[Set httpDNS](intl.en-US/User Guide/Set httpDNS.md#)|Provides a DNS service by using the HTTP protocol to directly access the server of Alibaba Cloud CDN.|Disabled|

