# Create a cache expiration rule {#task_261642 .task}

In each cache expiration rule, you can set the expiration time of static resources, which are cached in a specified directory or in files with specified file extensions. In addition, you can set the priority of each rule. This topic describes the cache policy of resources on CDN and how to create a cache expiration rule.

If the following requirement is met, you can follow the steps described in this topic: The same file name is not used to update content on your origin. If you need to update content on your origin, we recommend that you name the content files by version, such as img-v1.0.jpg and img-v2.1.jpg.

The following figure shows the cache policy of resources on CDN nodes.

![Cache policy](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5147/15670453053383_en-US.png)

**Note:** 

-   The default cache policy on edge nodes is used to set the file expiration time. This cache policy has a higher priority than that configured in the origin. If no cache policy is configured on the origin site, you can set a cache policy based on directory or file extension. Full paths are supported.
-   The resources cached on CDN nodes can be removed from the nodes ahead of time in case of low popularity.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the left-side navigation pane of the specified domain, click **Cache**.
5.  On the **Cache Expiration** tab, click **Create Rule**. 

    ![Cache Expiration](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5147/156704530553307_en-US.png)

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

    You can click **Modify** or **Delete** in the Actions column corresponding to a cache expiration rule to modify or delete the rule.


