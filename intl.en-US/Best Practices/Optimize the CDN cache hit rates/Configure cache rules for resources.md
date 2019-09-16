# Configure cache rules for resources {#task_878738 .task}

When the ETag or Last-Modified response headers are not returned, the requested static resource fails to be cached. This reduces the CDN cache hit rate. To improve the CDN cache hit rate, you can configure a cache rule for this resource. As a result, the resource can be cached on CDN according to the cache rule.

When no cache rule is configured on CDN, a static file cannot be cached on the CDN node if the ETag and Last-Modified response headers are not returned. Configure a cache rule for the static file as follows.

As shown in the following figure, the x-swift-cachetime response header shows that the cache duration of the static file on CDN is zero seconds. This indicates that CDN will not cache this static file because the ETag and Last-Modified response headers are not returned.

![Response header exception](images/50553_en-US.png)

If the origin server is configured with the following response headers, CDN will not cache the resource even if you have configured a cache rule. This is because these response headers have the highest priority in terms of CDN cache rules.

-   Any one of s-maxage=0, max-age=0, no-cache, no-store, and private
-   s-maxage or s-maxage=0
-   Pragma: no-cache

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the left-side navigation pane of the specified domain, click **Cache**.
5.  On the **Cache Expiration** tab, click **Create Rule**. 

    ![Cache expiration](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5147/156860492353307_en-US.png)

6.  In the Create Expiration Rule dialog box that appears, select a rule type as prompted. 

    |Parameter|Description|
    |---------|-----------|
    |Type|     -   Directory: specifies resources cached in a specific directory.
    -   File Extension: specifies resources cached in files with specific file extensions.
 |
    |Object|     -   When Type is set to Directory, enter a directory name in the Object field. The directory name must start with a forward slash \(/\), such as /directory/aaa.
    -   When Type is set to File Extension, enter one or more file extensions in the Object field. Multiple file extensions must be separated by using commas \(,\), such as jpg,txt.
 |
    |Expire In|Specifies the expiration time of the cached resources. The resource retention duration can reach up to three years. We recommend that you set this parameter in compliance with the following rules:     -   Specify a retention duration of one month or longer for static files such as images and applications that are not frequently updated.
    -   Specify a retention duration based on actual business situations for static files such as files in JS and CSS formats that are frequently updated.
    -   Do not cache dynamic files such as files in PHP, JSP, and ASP formats.
 |
    |Weight|Specifies the priority of the rule. **Note:** 

    -   The value of this parameter ranges from 1 to 99. A greater value indicates a higher priority, which in turn means that the rule takes effect preferentially.
    -   We recommend that you do not set the same priority for different rules. If different rules have the same priority value, they take effect in a random sequence.
 For example, if you set the following rules for the `example.aliyun.com` domain, Rule 1 takes effect preferentially over the other two rules:

    -   Rule 1: Type is set to File Extension, Object is set to jpg,png, Expire In is set to 1 Months, and Weight is set to 90.
    -   Rule 2: Type is set to Directory, Object is set to /www/dir/aaa, Expire In is set to 1 Hours, and Weight is set to 70.
    -   Rule 3: Type is set to Directory, Object is set to /www/dir/aaa/example.php, Expire In is set to 0 Seconds, and Weight is set to 80.
 |

7.  Click **OK**.

