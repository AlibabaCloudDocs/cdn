# Configure CNAME by Alibaba Cloud DNS {#concept_uwr_kbw_tdb .concept}

To enable your CDN acceleration service, you need to point your acceleration domain name to the CNAME address allocated by Alibaba Cloud CDN first. As a result, all requests to access to these acceleration domain names can be forwarded to CDN nodes, and acceleration eventually takes active. In this document, we introduce configuration of CNAME by using Alibaba Cloud DNS as an example.

## 1. Obtain the CNAME address of the CDN domain {#section_ey5_p4c_5db .section}

**a.**Log on to the [Alibaba Cloud CDN Console](https://partners-intl.console.aliyun.com/#/cdn), and click **Domain Names**.

**b.**Copy the CNAME you wish.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/15641312666056_en-US.png)

## 2. Add the CNAME record {#section_gy5_p4c_5db .section}

**a.**Log on to the [Alibaba Cloud DNS console](https://partners-intl.console.aliyun.com/#/dns).

**b.**Choose the main domain name that you want to accelerate, then click **Configure**.

**c.**Click **Add Record**.

-   Choose **Type** as `CNAME`.
-   Add the prefix for acceleration domain names with the rules below:

    |If your acceleration domain name is ...|Your host record is ...|
    |:--------------------------------------|:----------------------|
    |`testcdn.aliyun.com`|`testcdn`|
    |`www.aliyun.com`|`www`|
    |`aliyun.com`|`@`|
    |`*.aliyun.com`|`*`|

-   Paste the CNAME you copied in the CDN console.
-   Keep the default value for other boxes.

**d.**Click **Confirm**. CNAME is configured, then CDN service is also activated.

**Note:** 

-   Added CNAME record take effect immediately. However, modification of CNAME record takes up to 72 hours to take effect.
-   When adding a conflict, consider an accelerated domain name, or refer to parsing records mutex rules for Self-tuning conflicting records.
-   After the cname is configured, the status update is delayed for about 10 minutes, the domain name list page of the Ali cloud CDN console may still prompt that cname is not configured, just ignore it.

## 3. Verify CDN activation {#section_ny5_p4c_5db .section}

After you configure the CNAME record, the CNAME record may take some time to take effect, depending on your DNS provider. You can use a ping or dig command to access your CDN domain name.

When the request is redirected to`*.*kunlun*.com`, both the CNAME configuration and the CDN service are effective.

