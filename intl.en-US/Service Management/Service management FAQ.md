# Service management FAQ {#concept_371744 .concept}

-   Statistical analysis
    -   [Why does CDN access log statistics differ from CNZZ statistics?](#section_9cx_x6p_0wk)
    -   [\[DO NOT TRANSLATE\]](#section_m27_vev_xyz)
-   Log management
    -   [Why is there an entry with status code 408 in the CDN log?](#section_4ut_ssu_g6r)
    -   [What is the meaning of status code 304 in the CDN log?](#section_ohl_cql_ilp)
    -   [How can I analyze CDN access logs?](#section_fpd_8ri_7k7)
-   Diagnostic tool
    -   [How can I query the IP address of a CDN node?](#section_9p1_r9f_r2g)

## Why does CDN access log statistics differ from CNZZ statistics? {#section_9cx_x6p_0wk .section}

-   CNZZ collects statistics by embedding a piece of JavaScript code in each Web page of a website. After a user visits a Web page, statistics can be collected only if the Web page is loaded successfully. If the Web page fails to be loaded or the Web page does not contain the JavaScript code, statistics cannot be collected. In addition, if a file or image on this website is referenced by another website, CNZZ cannot collect the corresponding statistics.
-   CDN collects statistics based on every access request in the logs. Therefore, the statistics are more comprehensive. In addition, when CDN calculates page views \(PVs\), multiple PVs are counted if the same page contains multiple iframe tags.

If the issue still persists, [submit a ticket](https://selfservice.console.aliyun.com/ticket/createIndex).

## \[DO NOT TRANSLATE\] {#section_m27_vev_xyz .section}

\[DO NOT TRANSLATE\]

![](../DNCDN11855815/images/47323_en-US.png)

\[DO NOT TRANSLATE\]

\[DO NOT TRANSLATE\]

-   \[DO NOT TRANSLATE\]
-   \[DO NOT TRANSLATE\]

**\[DO NOT TRANSLATE\]**

[\[DO NOT TRANSLATE\]](https://selfservice.console.aliyun.com/ticket/createIndex)

## Why is there an entry with status code 408 in the CDN log? {#section_4ut_ssu_g6r .section}

This log entry is resulted from the CDN health check on the origin site. The CDN upper-layer node sends a TCP request \(similar to Telnet\) to the origin site. This health check does not affect the origin site.

If the issue still persists, [submit a ticket](https://selfservice.console.aliyun.com/ticket/createIndex).

## What is the meaning of status code 304 in the CDN log? {#section_ohl_cql_ilp .section}

When a client successfully sends a request to the server for the first time, the server returns the correct content to the client with status code 200. The response also includes the last modification time of the content and an entity tag \(ETag\) to examine whether the content has been modified. When the server receives the next request sent by the same client, the server checks whether the content has been modified since the last request based on the last modification time and ETag specified in the request. If no modification is made, the server returns status code 304 to the client, and the client directly loads the cached content. If the content has been modified, the server returns the client the latest content with the latest modification time and ETag.

Example:

As shown in the following figure, when the client requests an image for the first time, the server returns a response with status code 200. The response includes the Last-Modified and ETag fields.

![](../DNCDN11855815/images/48445_en-US.png)

When the client requests the image again, the last modification time and ETag are added to the request header. As shown in the following figure, the server checks whether the content has been modified based on the ETag and Last-Modified fields. If no modification is made, status code 304 is returned. If the content has been modified, the latest content is returned to the client with status code 200.

![](../DNCDN11855815/images/48446_en-US.png)

Therefore, it is normal that status code 304 is included in the server log information, CDN log information, or OSS log information. This indicates that the Web cache already contains the content and has not been modified since the last request. To update the local Web cache, press Ctrl + F5. As a result, the client clears the local Web cache and sends a request to the server. The server returns the requested content with status code 200.

If the issue still persists, [submit a ticket](https://selfservice.console.aliyun.com/ticket/createIndex).

## How can I analyze CDN access logs? {#section_fpd_8ri_7k7 .section}

In Linux, you can use the following commands to analyze CDN access logs:

-   Query all entries with status code 200 in a log file.

     `grep -w "200" log_file |awk '{if($9=="206") print $0}' >200log.txt`

-   Print a specific column in a log file.

     `cat log_file |awk '{print $12}'`

-   Calculate the response size of a log file.

     `cat log_file |awk 'BEGIN {size=0} {size=size+$11} END{print "endsizeis",size/1024/1024,"M"} '`

-   Query the top 10 IP addresses by visits.

     `cat log_file | awk '{print $3}' |sort|uniq -c|sort -nr |head -10`


For more information about CDN log fields, see [EN-US\_TP\_5171.md\#](intl.en-US/Service Management/Log Management/Log Downloading.md#).

If the issue still persists, [submit a ticket](https://selfservice.console.aliyun.com/ticket/createIndex).

## How can I query the IP address of a CDN node? {#section_9p1_r9f_r2g .section}

You can use the diagnostic tool in the CDN console to check whether an IP address is the IP address of a CDN node. For more information, see [EN-US\_TP\_5172.md\#](intl.en-US/Service Management/Diagnostic Tools.md#).

If the issue still persists, [submit a ticket](https://selfservice.console.aliyun.com/ticket/createIndex).

