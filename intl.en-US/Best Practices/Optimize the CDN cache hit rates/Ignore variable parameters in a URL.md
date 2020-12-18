---
keyword: [cache hit ratio, ignore parameter]
---

# Ignore variable parameters in a URL

If a request URL contains the queryString parameter or other variable parameters, Alibaba Cloud Content Delivery Network \(CDN\) may need to retrieve the requested resource from the origin server. In this case, the cache hit ratio is reduced. To improve the cache hit ratio, you can enable parameter filtering to ignore variable parameters in URLs.

Before you perform the tasks described in this document, make sure that you have completed [account registration](https://account.alibabacloud.com/register/intl_register.htm) and [real-name authentication](https://account-intl.console.aliyun.com/#/intlAuth) with Alibaba Cloud.

If a request URL contains the queryString parameter, or you specify a private Object Storage Service \(OSS\)bucket as the origin server, the required OSSAccessKeyId, Expires, and Signature parameters are automatically added to the request URL. In this case, Alibaba Cloud CDN processes request URLs based on the queryString parameter, and these requests may also hit different cache entries. If changes are made to the queryString parameter, Alibaba Cloud CDN must retrieve the requested resources from the origin server. This reduces the CDN cache hit ratio. To improve the cache hit ratio, you can enable parameter filtering.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the Domain Names page, find the target domain name and click **Manage**.

4.  In the left-side navigation pane of the specified domain, click **Optimization**.

5.  Specify parameters to be retained and ignored.

    -   Retain parameters
        1.  In the **Retain Parameters** section, click **Modify**.
        2.  Turn on the **Parameter Filtering** switch.
        3.  **Retain Parameters** based on your business requirements.

            ![Retain parameters](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9025924061/p57056.png)

            |Parameter|Description|
            |---------|-----------|
            |**Parameter Filtering**|Enables or disables the parameter filtering feature. After this feature is enabled, the parameters that follow the question mark \(`?`\) in the URL of a request are ignored by CDN nodes. This increases the cache hit ratio.|
            |**Retain Parameters**|Specifies the parameters to be retained. You can specify at most 10 parameters. Separate multiple parameters with commas \(,\). For example, for the URL `http://www.abc.com/a.jpg?x`, you can set **Retain Parameters** to `x`.|
            |**Retain Origin Parameters**|Specifies whether to retain all parameters in a URL. If you enable **Retain Origin Parameters**, all parameters in the URL of a request are retained during the back-to-origin process.|

            Example:

            When a CDN node retrieves the resource of `http://www.abc.com/a.jpg? x` from the origin server, x=1 is retained. When CDN nodes receive requests that are destined for `http://www.abc.com/a.jpg? x`, the CDN nodes always return the version of the resource that was previously cached for `http://www.abc.com/a.jpg?x` to the clients.

        4.  Click **OK**.
    -   Ignore parameters
        1.  In the **Parameter Filtering** section, click **Modify**.
        2.  Turn on the **Parameter Filtering** switch.
        3.  Enter parameters to be ignored in the **Ignore Parameters** field.

            ![Ignore parameters](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/5161/15686049487304_en-US.png)

            |Parameter|Description|
            |---------|-----------|
            |**Parameter Filtering**|Enables or disables the parameter filtering feature. After parameter filtering is enabled, the specified parameters in the URLs of requests are ignored by CDN nodes. Unspecified parameters are retained.|
            |**Ignore Parameters**|Specifies the parameters to be ignored. You can specify at most 10 parameters. Separate multiple parameters with space characters. For example, for the URL `http://www.abc.com/a.jpg?x`, you can set **Ignore Parameters** to `x`.|
            |**Retain Origin Parameters**|Specifies whether to retain all parameters in a URL. If you enable **Retain Origin Parameters**, all parameters in the URL of a request are retained during the back-to-origin process.|

            Note:

            When a CDN node retrieves the resource of `http://www.abc.com/a.jpg? x`, x is ignored by the CDN node. The CDN node retrieves the resource of `http://www.abc.com/a.jpg?x` from the origin server and then returns the resource to the client.

        4.  Click **OK**.
6.  To check whether the cached resource can be hit, perform the following steps:

    1.  Open the browser Google Chrome and press F12.
    2.  In the panel that appears, click the **Network** tab.
    3.  Check the value of the `X-Cache` field in the response header of the specified URL.
        -   A value of `HIT` indicates that the resource that is cached on the CDN node is hit.
        -   A value of `MISS` indicates that the requested resource has not been cached on the CDN node and is retrieved from the origin server.

