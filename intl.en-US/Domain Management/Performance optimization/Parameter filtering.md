---
keyword: [ignore parameters, parameter filtering, retain parameters]
---

# Parameter filtering

A Content Delivery Network \(CDN\) node may receive a request whose URL contains a question mark `(?)` followed by parameters. You can enable the parameter filtering feature to ignore parameters and increase the cache hit ratio and content delivery efficiency. This topic describes how to configure parameter filtering in the Alibaba Cloud CDN console.

The parameter filtering feature can retain or ignore parameters.

-   Retain parameters

    Most HTTP requests contain parameters. Content can still be retrieved from the origin server when parameters with low priorities are ignored. After you enable parameter filtering, the cache hit ratio and delivery efficiency are improved.

    If a parameter contains important information such as the file version, we recommend that you specify the parameter as a retained parameter. You can specify at most 10 parameters to be retained. If a request URL contains a retained parameter, the CDN node retrieves content from the origin server based on the URL with the specified parameter retained.

    Configure the parameter filtering feature to ignore parameters that follow the question mark \(`?`\) in request URLs. This increases the cache hit ratio. For example, the first time that `http://www. ****.com/1.jpg` is visited, the resource is not cached on CDN nodes. Therefore, the CDN nodes must retrieve the requested resource from the origin server. When `http://www. ****.com/1.jpg? test1` is visited, the parameters that follow the question mark \(`?`\) are ignored because parameter filtering is enabled. The resource of `http://www. ****.com/1.jpg` has already been cached on CDN nodes. The client directly retrieves the resource from the nearest CDN node.

-   Ignore parameters

    A CDN node caches a unique version of a requested resource for each URL that includes different parameters.

    After the parameter filtering feature is disabled, the requested resource can be retrieved from the cache only if the parameters that follow the question mark \(`?`\) in the URL are an exact match of the previously cached one. Exact matches can increase request accuracy. For example, the first time that `http://www. ****.com/1.jpg` is visited, the resource is not cached on CDN nodes. Therefore, the CDN nodes must retrieve the requested resource from the origin server. When `http://www. ****.com/1.jpg? test1` is visited, the parameters following the question mark \(`?`\) in the URL are not ignored because parameter filtering is disabled, and the URL is not an exact match. The CDN nodes cannot return the resource of `http://www. ****.com/1.jpg` to the client. Instead, the CDN nodes must retrieve the requested resource of `http://www. ****.com/1.jpg?test1` from the origin server.


The parameter filtering feature allows you to configure parameters to be retained or ignored.

-   Retain parameters: You can specify one or more parameters to be retained. Separate multiple parameters with commas \(,\). Unspecified parameters are not retained.
-   Ignore parameters: You can specify one or more parameters to be ignored. Separate multiple parameters with space characters. Unspecified parameters are not ignored.

**Note:** The URL authentication feature takes priority over the parameter filtering feature. The signature information of [authentication type A](/intl.en-US/Domain Management/Access control/Business type/Authentication type A.md) contains the parameters of an HTTP request. Therefore, CDN nodes must verify the signature of the request URL before the CDN nodes cache a version of the requested resource. For more information about how to configure URL authentication, see [Configure URL authentication](/intl.en-US/Domain Management/Access control/Business type/Configure URL signing.md).

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
            |**Parameter Filtering**|Enables or disables the parameter filtering feature. After this feature is enabled, the parameters following the question mark \(`?`\) in a request URL are ignored by CDN nodes. This increases the cache hit ratio.|
            |**Retain Parameters**|Specifies the parameters to be retained. You can specify at most 10 parameters. Separate multiple parameters with commas \(,\). For example, for the URL `http://www.abc.com/a.jpg?x`, you can set **Retain Parameters** to `x`.|
            |**Retain Origin Parameters**|Specifies whether to retain all parameters in a URL. If you enable **Retain Origin Parameters**, all parameters in a request URL are retained during the back-to-origin process.|

            Note:

            When a CDN node retrieves the resource of `http://www.abc.com/a.jpg? x` from the origin server, x=1 is retained. When CDN nodes receive request URLs that contain the x parameter and are destined for `http://www.abc.com/a.jpg`, the CDN nodes always return the version of the resource that was previously cached for `http://www.abc.com/a.jpg?x=1` to the clients.

        4.  Click **OK**.
    -   Ignore parameters
        1.  In the **Parameter Filtering** section, click **Modify**.
        2.  Turn on the **Parameter Filtering** switch.
        3.  Enter parameters to be ignored in the **Ignore Parameters** field.

            ![Ignore parameters](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/5161/15686049487304_en-US.png)

            |Parameter|Description|
            |---------|-----------|
            |**Parameter Filtering**|Enables or disables the parameter filtering feature. After parameter filtering is enabled, the specified parameters in request URLs are ignored by CDN nodes. Unspecified parameters are retained.|
            |**Ignore Parameters**|Specifies the parameters to be ignored. You can specify at most 10 parameters. Separate multiple parameters with space characters. For example, for the URL `http://www.abc.com/a.jpg?x`, you can set **Ignore Parameters** to `x`.|
            |**Retain Origin Parameters**|Specifies whether to retain all parameters in a URL. If you enable **Retain Origin Parameters**, all parameters in a request URL are retained during the back-to-origin process.|

            Note:

            When a CDN node retrieves the resource of `http://www.abc.com/a.jpg? x`, x is ignored by the CDN node. The CDN node retrieves the resource of `http://www.abc.com/a.jpg?x` from the origin server and then returns the resource to the client.

        4.  Click **OK**.

