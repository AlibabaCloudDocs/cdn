---
keyword: [download log, download CDN log]
---

# Download log data

This topic describes the usage notes and procedure for downloading log data, and the definitions of fields in a log entry. This feature allows you to check the log data of a domain name.

Usage notes:

-   Log update delay: Typically, log data is generated within 24 hours after an event occurs. However, in some cases, the log data may be generated after 24 hours.
-   You can download log data generated within the last 30 days. If you need to retain log data for a longer period of time, you can use the log storage feature to deliver log data to an Object Storage Service \(OSS\) bucket.
-   Naming rule for log entries: Accelerated domain name\_year\_month\_day\_start time\_end time\[extension field\].gz. The extension field must start with an underscore \(\_\). Example: `example.com_2018_10_30_000000_010000_xx.gz`.

    **Note:** Some log entries may not contain an extension field. Example: `example.com_2018_10_30_000000_010000.gz`.


The following table describes the fields in a log entry.

-   Sample log entry

    ```
    [9/Jun/2015:01:58:09 +0800] 192.168.15.75 - 1542 "-" "GET http://www.aliyun.com/index.html" 200 191 2830 MISS "Mozilla/5.0 (compatible; AhrefsBot/5.0; +http://ahrefs.com/robot/)" "text/html"
    ```

-   Descriptions of log fields

    |Field|Description|
    |-----|:----------|
    |`[9/Jun/2015:01:58:09 +0800]`|The start time of the log entry.|
    |`192.168.15.75`|The IP address of the client that initiated the request.|
    |`-`|The proxy IP address of the client.|
    |`1542`|The response time.Unit: milliseconds. |
    |`"-"`|The referer header field in the HTTP request.|
    |`GET`|The request method.|
    |`http://www.aliyun.com/index.html`|The URI in the request.|
    |`200`|The HTTP status code.|
    |`191`|The size of the request.Unit: bytes. |
    |`2830`|The size of the response.Unit: bytes. |
    |`MISS`|The cache hit status.|
    |`Mozilla/5.0(compatible; AhrefsBot/5.0; +http://ahrefs.com/robot/)`|The information about the proxy of the client.|
    |`text/html`|The type of the requested file.|
    |`quic/https/http`|The protocol over which the request was transmitted.**Note:** This field is available beginning November 12, 2020. |


1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Logs**.

3.  On the **Log Download** page, select a **domain name** and a **date** and click **Search**.

4.  Find the log file that you want to download and click **Download** in the **Actions** column.


## API operations

You can call an API operation to download log data. For more information, see [DescribeCdnDomainLogs](/intl.en-US/New API Reference/Log operations/DescribeCdnDomainLogs.md).

