# Set HTTP code expiration time {#concept_wx3_2pq_dhb .concept}

This topic describes how to set the HTTP code expiration time.

## Background {#section_xrd_jsb_fhb .section}

If the specified file extension or directory rule is matched to resources cached on CDN, you can set the expiration time of these resources based on the specified HTTP code expiration time.

**Note:** 

-   The system does not cache information about 303, 304, 401, 407, 600, and 601 status codes.
-   For 204, 305, 400, 403, 404, 405, 414, 500, 501, 502, 503, and 504 status codes, if a Cache-Control header is returned from the origin, the rule specified by the Cache-Control parameter is applied. If the HTTP code expiration time is not specified, the default cache time specified by the negative\_ttl parameter is 1s.

## Procedure {#section_gky_rgp_fhb .section}

1.  Log on to the [CDN console](https://cdnnext.console.aliyun.com).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, select a domain name, and in the **Actions** column click **Manage**.
4.  On the page that is displayed, choose **Cache** from the left pane, and click the **HTTP Code Expire Time** tab in the right pane.
5.  On the HTTP Code Expire Time tab page, click **Add**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/145921/156163097541801_en-US.png)

6.  In the Http code expire time dialog box, set **Type** and other required parameters.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/145921/156163097541802_en-US.png)

    |Type|Remarks|
    |:---|:------|
    |Directory|     -   Add a single directory \(full paths are supported\). The directory must start with a forward slash \(/\) \( for example, /directory/aaa\).
    -   Status codes of the 2xx and 3xx formats are not allowed.
 |
    |File extension|     -   Multiple file extensions are separated by commas \(,\) \(for example, txt,jpg\).
    -   Asterisks \(\*\) cannot be used to match all types of files.
    -   Status codes of the 2xx and 3xx formats are not allowed.
 |

7.  Click **Confirm**.

    **Note:** If you set two types of HTTP code expiration times, for the Directory and File extension, then the type you set earlier takes effect.


