# Set status code expiration time {#task_261642 .task}

If the specified file extension or directory rule is matched to static resources cached on CDN, you can set the expiration time of these resources based on the specified status code expiration time. This topic describes how to set the status code expiration time.

When you set the status code expiration time, note the following limits:

-   The system does not cache information about 303, 304, 401, 407, 600, and 601 status codes.
-   For 204, 305, 400, 403, 404, 405, 414, 500, 501, 502, 503, and 504 status codes, if a Cache-Control header is returned from the origin, the rule specified by the Cache-Control parameter is applied. If the status code expiration time is not specified, the default cache time specified by the negative\_ttl parameter is 1s.
-   If you set status code expiration time of both the directory and file extension types, the type you set first takes effect.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the left-side navigation pane of the specified domain, click **Cache**.
5.  Click **Status Code Expiration**.
6.  On the Status Code Expiration tab, click **Create Rule**. 

    ![Status code expiration time](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/145921/156653095141802_en-US.png)

7.  In the Create Expiration Rule dialog box that appears, set Type as prompted. 

    |Type|Consideration|
    |:---|:------------|
    |Directory|     -   Add a single directory \(full paths are supported\). The directory must start with a forward slash \(/\), such as /www/directory/aaa.
    -   Status codes of the 2xx and 3xx formats are not allowed.
 |
    |File extension|     -   Multiple file extensions are separated by commas \(,\), such as txt,jpg.
    -   Asterisks \(`*`\) cannot be used to match all types of files.
    -   Status codes of the 2xx and 3xx formats are not allowed.
 |

8.  Click **OK**. 

    You can click **Modify** or **Delete** in the Actions column corresponding to a status code expiration rule to modify or delete the rule.


