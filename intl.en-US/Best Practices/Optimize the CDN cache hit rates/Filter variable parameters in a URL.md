# Filter variable parameters in a URL {#task_878912 .task}

If the URL of your request includes a query string or other variable parameters, CDN may need to retrieve the requested resource from the origin server. In this case, the CDN cache hit rate is reduced. To improve the cache hit rate, you can enable parameter filtering to filter variable parameters in URLs.

-   If you specify an OSS private bucket as the origin, the required OSSAccessKeyId, Expires, and Signature parameters are automatically added to the URL of the origin request. In such a case, how CDN processes requests to the URL depends on the query string, and these requests may also hit different cache entries. The same is also true when the URL of your request includes the query string. If any change occurs to the query string, CDN needs to retrieve the requested resource from the origin server. This reduces the CDN cache hit rate. To improve the cache hit rate, you can enable parameter filtering.
-   For CDN-based OSS access acceleration, we recommend that you enable the private bucket back-to-origin authorization feature. For more information, see [Enable private bucket back-to-origin authorization](../reseller.en-US/Domain Management/Content back-to-source settings/Enable private bucket back-to-origin authorization.md#).

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the left-side navigation pane of the specified domain, click **Optimization**.
5.  In the Parameter Filtering section, click **Modify** below **Retain Parameters** or **Ignore Parameters**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5161/156860494757058_en-US.png)

    ![Parameter filtering](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5161/15686049487304_en-US.png)

6.  Turn on **Parameter Filtering** and set **Retain Parameters** or Ignore Parameters. You can also choose to turn on **Retain Origin Parameters** based on your business requirements. 
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

7.  Click **OK**.

