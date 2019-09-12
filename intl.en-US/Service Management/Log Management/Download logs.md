# Download logs {#task_187634 .task}

This topic describes the instructions for using the log download function, log fields, and download procedures. You can use this function to check logs corresponding to the domains.

Instructions for using the log download function:

-   The typical latency to ingest log data is within 24 hours. However, it may also exceed 24 hours. You can query the generated log files in the Log Management module.
-   Log files are generated once every hour. The log files are segmented based on the number of logs generated during the hour they were generated.
-   You can download all logs generated in the last month.
-   Naming convention: CDNDomain\_Year\_Month\_Date\_StartTime\_EndTime Example: www.test.com\_2018\_10\_30\_000000\_010000.gz

Log field description:

-   Sample log

    ``` {#codeblock_ove_wbh_dm1 .language-java}
    [9/Jun/2015:01:58:09 +0800] 192.168.15.75 - 1542 "-" "GET http://www.aliyun.com/index.html" 200 191 2830 MISS "Mozilla/5.0 (compatible; AhrefsBot/5.0; +http://ahrefs.com/robot/)" "text/html"
    ```

-   Log field description

    |Field|Description|
    |-----|:----------|
    |\[9/Jun/2015:01:58:09 +0800\]|Time|
    |192.168.15.75|Access IP|
    |-|Proxy IP|
    |1542|Response time \(unit: ms\)|
    |"-"|Referer|
    |GET|Method|
    |http://www.aliyun.com/index.html|Accessed URL|
    |200|HTTP status code|
    |191|Request size \(unit: Byte\)|
    |2830|Response size \(unit: Byte\)|
    |MISS|Cache hit status|
    |Mozilla/5.0 \(compatible; AhrefsBot/5.0; +http://ahrefs.com/robot/\)|UserAgent header|
    |text/html|File type|


1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).
2.  In the left-side navigation pane, click **Logs**.
3.  On the Log Download page, select a domain from the drop-down list and select a time range from the calendar, and then click Search.
4.  Click **Download** in the Actions column corresponding to a log file to download the file. 

    ![Log download](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5171/156826643121219_en-US.png)


## API {#example_q59_7yh_4dh .example}

You can call API operations to implement the log download function. For more information, see [DescribeCdnDomainLogs](../intl.en-US/New API Reference/Log operations/DescribeCdnDomainLogs.md#).

