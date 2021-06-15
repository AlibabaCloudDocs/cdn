# Enable log storage

Alibaba Cloud Content Delivery Network \(CDN\) supports the log storage feature, which is integrated with Object Storage Service \(OSS\) and Data Lake Analytics \(DLA\). After the log storage feature is enabled, Alibaba Cloud CDN automatically stores logs in a specified OSS bucket. Logs can be stored in OSS buckets for an extended period of time. You can use DLA to analyze the logs. This topic describes how to enable log storage.

You must activate OSS and DLA before you can enable log storage. You can use the following methods to activate these services:

-   To activate OSS, go to the [product page of OSS](https://www.alibabacloud.com/product/oss).
-   To activate DLA, go to the [product page of DLA](https://www.alibabacloud.com/product/data-lake-analytics).

When you enable log storage, the system automatically creates the service-link role \(SLR\) AliyunServiceRoleForCDNLogDelivery. The SLR is granted permissions to access OSS and DLA. This allows Alibaba Cloud CDN to automatically store logs in OSS buckets. For more information about the SLR, see [Manage the SLR for log storage]().

## Billing rules

After log storage is enabled, you are charged for both OSS and DLA.

-   For more information about the billing rules of OSS, see [OSS Pricing](https://www.alibabacloud.com/product/oss/pricing).
-   For more information about the billing rules of DLA, see [Billing methods]().

    **Note:** After log storage is enabled, logs are delivered by DLA. You are charged for DLA no matter whether you use DLA to analyze data.


## Procedure

**Note:**

-   Logs are collected from DCDN nodes and then directly delivered to the OSS bucket. The integrity of logs is not guaranteed. If you want to acquire complete log data, we recommend that you download logs on the **Log Download** tab. Make sure that the fields you specified are the same as those in the logs.
-   If you want to grant a Resource Access Management \(RAM\) user permissions on log storage, make sure that the authorized scope is **Alibaba Cloud Account**. For more information, see [Step 2: Grant permissions to the RAM user]().
-   If you want to manage log storage as a RAM user, make sure that the authorized scope of the RAM user is **Alibaba Cloud Account**. Otherwise, log storage may be disabled for some domain names.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, choose **Logs** \> **Offline Logs**.

3.  Click the **Log Storage** tab.

4.  Click **Activate Now**.

5.  Set **Storage Location**.

    1.  In the **Activate Log Storage** dialog box, set **Storage Location**.

        **Note:**

        -   An OSS bucket is created in the specified region. Logs of Alibaba Cloud CDN are stored in this OSS bucket.
        -   The region cannot be changed.
        -   If log storage is already enabled in Dynamic Route for CDN \(DCDN\) with a region specified, you cannot specify a region when you enable log storage in Alibaba Cloud CDN. By default, the region for the log storage feature in Alibaba Cloud CDN and DCDN is the same.
        |Service country and region|Storage country and region|Description|
        |--------------------------|--------------------------|-----------|
        |Mainland China|        -   China \(Shanghai\)
        -   China \(Beijing\)
        -   China \(Hangzhou\)
|The China \(Shanghai\), China \(Beijing\), and China \(Hangzhou\) regions are supported. Select a region based on your business requirements.|
        |Other countries and regions|Singapore \(Singapore\)|Only this region is supported.|
        |India|India \(Mumbai\)|Only this region is supported.|
        |Europe|Germany \(Frankfurt\)|Only this region is supported.|
        |US|US \(Silicon Valley\)|Only this region is supported.|

    2.  Click **Activate Data Lake Analytics and go to the next step**.

6.  Set **Delivery Rule**.

    1.  In the **Activate Log Storage** dialog box, set **Log Fields**, and select the accelerated domain names for which you want to enable log storage.

        **Note:** The console displays at most 500 domain names. You can select at most 500 domain names. If you want to enable log storage for more domain names, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).

        You can specify one or more log fields. The log fields cannot be modified after they are specified. The following table describes the supported fields.

        |Field|Description|Example|
        |-----|-----------|-------|
        |contentType|Indicates file types.|`text/html`|
        |domain|Indicates accelerated domain names.|`www.aliyun.com`|
        |hitInfo|Indicates cache hit ratios.|`hit`|
        |http2|Indicates the HTTP/2 protocol.|`HTTP2`|
        |httpCode|Indicates HTTP status codes.|`504`,`404`,`302`,`200`|
        |method|Indicates request methods. Valid values: GET and POST.|`GET` or `POST`|
        |refer|Indicates the referer header in HTTP requests.|`"-"`|
        |remoteIP|Indicates the IP address of the client that initiated the request.|`192.168.15.75`|
        |reqSize|Indicates the size of the request. Unit: bytes.|`129`|
        |respSize|Indicates the size of the response. Unit: bytes.|`129`|
        |rt|Indicates the response time. Unit: milliseconds.|`1542`|
        |schema|Indicates the protocol over which the request was transmitted. HTTP and HTTPS are supported.|`HTTP` or `HTTPS`|
        |traceID|Indicates the unique ID of the request.|`d35ba34115550716522547264e`|
        |ua|Indicates the information about the proxy of the client.|`Mozilla/5.0(compatible; AhrefsBot/5.0; +http://ahrefs.com/robot/)`|
        |unixtime|Indicates the start time of the log entry. Unit: seconds.|`[9/Jun/2019:01:58:09 +0800]`|
        |urlPath|Indicates the Uniform Resource Identifier \(URI\) of the request. No domain name information is included.|`/index.html`|
        |urlRawQuery|Indicates the query parameters that follow the question mark \(?\)in a URL.|`x=1&y=1`|
        |userlnfo|Indicates custom fields.|N/A|

    2.  Click **Activate**.

        If you want to modify log delivery rules or disable log storage after log storage is enabled, you can perform relevant operation on the **Log Storage** tab.

        After log storage is disabled, you can delete the SLR AliyunServiceRoleForCDNLogDelivery based on business requirements. For more information, see [Delete AliyunServiceRoleForCDNLogDelivery](section_bge_8p4_c15).


