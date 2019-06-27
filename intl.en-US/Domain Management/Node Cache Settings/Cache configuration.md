# Cache configuration {#concept_f24_32d_xdb .concept}

## Introduction {#section_dks_yhd_xdb .section}

-   This function can be used to **set the actions of a cache server against resources in different directory paths**, or **resources with different file name suffixes**. You can customize cache expiration rules for specified resources.
-   You can customize a cache policy priority.
-   The following figure shows the default cache policies.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5147/15616309993383_en-US.png)

    **Note:** 

    -   This function is used to set file expiration time. The priority specified here is higher than that configured on the origin site. If no cache policy is configured on the origin site, you can set a cache policy by directory and file name suffix \(the full path mode is supported\).
    -   CDN cached files can be removed from the CDN node if the cached files are not updated frequently.

## Notes {#section_tts_q3d_xdb .section}

-   For infrequently updated static files \(for example, image files or application download files\), we suggest you set a cache time of 1 month or more;
-   For static files that must be updated or are updated frequently \(for example js and css files\), you can set a shorter cache time based on the actual situation;
-   For dynamic files \(for example, PHP files, JSP files, and ASP files\), we recommend that you set the cache duration as 0s, indicating that the files are not cached. If dynamic files such as PHP files are not updated frequently, we recommend that you set the cache duration to a small value.
-   We recommend that the content on an origin site is updated with the same file name, but tagged with different version numbers; for example, img-v1.0.jpg and img-v2.1.jpg.

## Configuration guide {#section_n4v_t3d_xdb .section}

1.  Log on to the [CDN console](https://cdnnext.console.aliyun.com/domain/list).
2.  In the left-side navigation pane, choose **Domain Names**. In the main workspace, select a domain, and in the **Actions** column click **Manage**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5147/156163099945766_en-US.png)

3.  In the left-side navigation pane, choose **Cache**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5147/15616309993384_en-US.png)

4.  Click **Modify**. You can manage cache policies by perform adding, modifying, and deletion operations.
5.  Click **Add** to add cache policies by directory paths or file name suffixes.

For example, set three cache policies for the CDN domain name `example.aliyun.com`:

-   Cache policy 1: the cache duration for all files suffixed with .jpg and .png is one month, and the weight is 90.
-   Cache policy 2: the cache duration for files in the /www/dir/aaa directory is one hour, and the weight is 70.
-   Cache policy 3: the cache duration for the full path /www/dir/aaa/example.php is 0 s \(No cache action will be performed\), and the weight is 80.

The priority is Policy 1 \> Policy 3 \> Policy 2.

**Note:** 

-   The range of weight is from 1 to 99. The larger the number, the higher the priority.
-   We recommended that you do not set the same weights for different cache policies. Cache policies with the same weight will be assigned a random weight value.

