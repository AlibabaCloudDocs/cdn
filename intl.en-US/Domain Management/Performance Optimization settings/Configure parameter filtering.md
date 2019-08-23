# Configure parameter filtering {#task_187634 .task}

If a request URL contains a question mark `(?)` and parameters, such as `http://alibaba.com/content?a=10`, CDN nodes will determine whether to retrieve content from the origin server based on the entire request URL. This topic describes how to configure parameter filtering.

-   Enable parameter filtering

    When a request is sent to a CDN node, the CDN node removes the parameters after the question mark \(?\) in the URL when retrieving content from the origin server. The CDN node caches only one copy of the requested content.

    -   Most HTTP requests contain parameters. However, parameters can be ignored when they have low priorities. After you enable parameter filtering, the file cache hit rate and delivery efficiency are improved.
    -   If a parameter contains important information such as the file version, we recommend you set Retain Parameters to retain this parameter. You can retain up to 10 parameters. If the request URL contains a retained parameter, the CDN node will retrieve content from the origin server based on the URL with the retained parameter.
-   Disable parameter filtering

    Different copies of the requested content corresponding to different parameters in URLs will be cached.


Parameter filtering consists of Retain Parameters feature and Ignore Parameters feature.

-   Retain Parameters: You can specify one or more parameters to be retained. You must separate multiple parameters with commas \(,\). Unspecified parameters are not retained.
-   Ignore Parameters: You can specify one or more parameters to be ignored. You must separate multiple parameters with spaces. Unspecified parameters are not ignored.

**Note:** The URL authentication feature takes priority over parameter filtering. The authentication information in authentication type A contains parameters of an HTTP request. Therefore, CDN nodes perform URL authentication first. The CDN node caches a copy of the requested content after the URL authentication succeeds. For more information about how to configure URL authentication, see [Configure URL authentication](EN-US_TP_15390.dita#concept_rtr_qsm_j2b).

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the left-side navigation pane of the specified domain, click **Optimization**.
5.  In the Parameter Filtering section, click **Modify** below **Retain Parameters** or **Ignore Parameters**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5161/156653379057058_en-US.png)

    ![Parameter filtering](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5161/15665337907304_en-US.png)

6.  You can configure **Retain Parameters** or **Ignore Parameters** as needed. 

    -   Retain Parameters

        |Parameter|Description|
        |---------|-----------|
        |Parameter Filtering|The switch used to retain parameters. After the Parameter Filtering switch is turned on, the parameters that follow question marks \(?\) in the URL are filtered out during the back-to-origin process. This helps increase the file cache hit rate.|
        |Retain Parameters|The parameters to be retained. Up to 10 parameters can be configured. Separate multiple parameters with commas \(,\).|
        |Retain Origin Parameters|The switch used to retain origin parameters. After the Retain Origin Parameters switch is turned on, all parameters are retained during the back-to-origin process.|

    -   Ignore Parameters

        |Parameter|Description|
        |---------|-----------|
        |Parameter Filtering|The switch used to ignore parameters. After the Parameter Filtering switch is turned on, the specified parameters are ignored during the back-to-origin process. Unspecified parameters are not ignored.|
        |Ignore Parameters|The parameters to be ignored. Up to 10 parameters can be configured. Separate multiple parameters with spaces.|
        |Retain Origin Parameters|The switch used to retain origin parameters. After the Retain Origin Parameters switch is turned on, all parameters are retained during the back-to-origin process.|

    Example:

    The `http://www.abc.com/a.jpg?x=1` URL request is sent to a CDN node.

    -   If the Retain Parameters feature is enabled:
        1.  The CDN node initiates the `http://www.abc.com/a.jpg` request to the origin server. The parameter x=1 is ignored.
        2.  The origin server returns a response to the CDN node.
        3.  The CDN node caches a copy of the content requested by the `http://www.abc.com/a.jpg` request and then returns the content to the client.
        4.  The CDN node caches a copy of the requested content for the `http://www.abc.com/a.jpg` request, and returns the requested content to all requests similar to `http://www.abc.com/a.jpg?parameters`.
    -   If the Retain Parameters feature is disabled: `http://www.abc.com/a.jpg? x=1` and `http://www.abc.com/a.jpg?x=2` contain different parameters. Therefore, requested contents are returned based on the parameters following the question mark \(?\) in the URL.
7.  Click **OK**.

