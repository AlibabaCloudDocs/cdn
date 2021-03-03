---
keyword: [ignore parameters, parameter filtering, retain parameters]
---

# Parameter filtering

A Content Delivery Network \(CDN\) node may receive a request whose URL contains a question mark `(?)` followed by parameters. You can enable the parameter filtering feature to ignore parameters and increase the cache hit ratio and content delivery efficiency. This topic describes how to configure parameter filtering in the Alibaba Cloud CDN console.

The parameter filtering feature can retain or ignore parameters.

-   Retain parameters

    Most HTTP requests contain parameters. Content can still be retrieved from the origin server when parameters with low priorities are ignored. After you enable parameter filtering, the cache hit ratio and delivery efficiency are improved.

    If a parameter contains important information such as the file version, we recommend that you retain the parameter. You can specify at most 10 parameters to be retained. If the URL of a request contains a retained parameter, the CDN node retrieves content from the origin server based on the URL with the specified parameter retained.

    Configure the parameter filtering feature to ignore parameters that follow the question mark \(`?`\) in the URLs of requests. This increases the cache hit ratio. For example, the first time that `http://www. ****.com/1.jpg` is visited, the resource is not cached on CDN nodes. Therefore, the CDN nodes must retrieve the requested resource from the origin server. When `http://www. ****.com/1.jpg? test1` is visited, the parameters that follow the question mark \(`?`\) are ignored because parameter filtering is enabled. The resource of `http://www. ****.com/1.jpg` has already been cached on CDN nodes. The client directly retrieves the resource from the nearest CDN node.

-   Ignore parameters

    A CDN node caches a unique version of a requested resource for each URL that includes different parameters.

    After the parameter filtering feature is disabled, the requested resource can be retrieved from the cache only if the parameters that follow the question mark \(`?`\) in the URL are an exact match of the previously cached one. Exact matches can increase request accuracy. For example, the first time that `http://www. ****.com/1.jpg` is visited, the resource is not cached on CDN nodes. Therefore, the CDN nodes must retrieve the requested resource from the origin server. When `http://www. ****.com/1.jpg? test1` is visited, the parameters that follow the question mark \(`?`\) in the URL are not ignored because parameter filtering is disabled, and the URL is not an exact match. The CDN nodes cannot directly return the resource of `http://www. ****.com/1.jpg` to the client. Instead, the CDN nodes must retrieve the requested resource of `http://www. ****.com/1.jpg?test1` from the origin server.


The parameter filtering feature allows you to specify parameters to be retained and ignored.

-   Retain parameters: You can specify one or more parameters to be retained. Separate multiple parameters with commas \(,\). Unspecified parameters are not retained.
-   Ignore parameters: You can specify one or more parameters to be ignored. Separate multiple parameters with space characters. Unspecified parameters are not ignored.

**Note:** The URL authentication feature takes priority over the parameter filtering feature. The signature information of [type A signing](/intl.en-US/Domain Management/Access control/URL signing/Type A signing.md) contains the parameters of an HTTP request. Therefore, CDN nodes must verify the signature of the request URL before the CDN nodes cache a version of the requested resource. For more information about how to configure URL signing, see [URL signing](/intl.en-US/Domain Management/Access control/URL signing/URL signing.md).

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Optimization**.

5.  Specify parameters to be retained and ignored.

    -   Retain parameters
        1.  In the **Retain Parameters \(Retain Specified Parameters\)** section, click **Modify**.
        2.  Turn on **Parameter Filtering**.
        3.  **Retain Parameters \(Retain Specified Parameters\)** based on your business requirements.

            ![Retain parameters](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9025924061/p57056.png)

            |Parameter|Description|
            |---------|-----------|
            |**Parameter Filtering**|Enables or disables the parameter filtering feature. After parameter filtering is enabled, the parameters that follow the question mark \(`?`\) in the URL of a request are ignored by CDN nodes. This increases the cache hit ratio.**Note:** If you enable parameter filtering but do not specify the parameters to be ignored or retained, all parameters that follow the question mark \(`?`\) are ignored. |
            |**Retain Specified Parameters**|Specifies the parameters to be retained. You can specify at most 10 parameters. Separate multiple parameters with commas \(,\). For example, for the URL `http://www.abc.com/a.jpg?x`, you can set **Retain Specified Parameters** to `x`.|
            |**Retain Origin Parameters**|Specifies whether to retain all parameters in a URL. If you enable **Retain Origin Parameters**, all parameters in the URL of a request are retained during the back-to-origin process.|

            Note:

            When a CDN node retrieves the resource of `http://www.abc.com/a.jpg? x` from the origin server, x=1 is retained. When CDN nodes receive requests that are destined for `http://www.abc.com/a.jpg? x`, the CDN nodes always return the version of the resource that was previously cached for `http://www.abc.com/a.jpg?x` to the clients.

        4.  Click **OK**.
    -   Ignore parameters
        1.  In the **Ignore Parameters \(Deletes Specified Parameters\)** section, click **Modify**.
        2.  Turn on **Parameter Filtering**.
        3.  Enter parameters to be ignored in the **Ignore Parameters** field.

            ![Filter Parameters dialog box](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/5161/15686049487304_en-US.png)

            |Parameter|Description|
            |---------|-----------|
            |**Parameter Filtering**|Enables or disables the parameter filtering feature. After parameter filtering is enabled, the specified parameters in the URLs of requests are ignored by CDN nodes. Unspecified parameters are retained.|
            |**Ignore Parameters**|Specifies the parameters to be ignored. You can specify at most 10 parameters. Separate multiple parameters with space characters. For example, for the URL `http://www.abc.com/a.jpg?x`, you can set **Ignore Parameters** to `x`.|
            |**Retain Origin Parameters**|Specifies whether to retain all parameters in a URL. If you enable **Retain Origin Parameters**, all parameters in the URL of a request are retained during the back-to-origin process.|

            Note:

            When a CDN node retrieves the resource of `http://www.abc.com/a.jpg? x`, x is ignored by the CDN node. The CDN node retrieves the resource of `http://www.abc.com/a.jpg?x` from the origin server and then returns the resource to the client.

        4.  Click **OK**.

