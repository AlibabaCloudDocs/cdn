# Create an HTTP header {#task_261642 .task}

The HTTP header fields describe the requested resources and the client or server behavior, and also define the operating parameters of an HTTP transaction. This topic describes how to create an HTTP header.

The HTTP header refers to the header component in the request and response messages sent over Hypertext Transfer Protocol \(HTTP\).

HTTP header fields include General-header, Client Request-header, and Server Response-header fields. The following table describes the 10 HTTP header parameters provided by Alibaba Cloud CDN. You can define the value of each parameter.

|Parameter|Description|
|:--------|:----------|
|Content-Type|Specifies the content type of the objects requested by a client program.|
|Cache-Control|Specifies the caching policy that a client program follows when initiating requests and making responses.|
|Content-Disposition|Specifies the default file name provided by a client program when the requested content is saved as a file.|
|Content-Language|Specifies the language of the objects requested by a client program.|
|Expires|Specifies the expiration time of the objects requested by a client program.|
|Access-Control-Allow-Origin|Specifies the domains from which cross-domain requests are allowed.|
|Access-Control-Allow-Headers|Specifies the fields that are allowed in cross-domain requests.|
|Access-Control-Allow-Methods|Specifies the cross-domain request methods that are allowed.|
|Access-Control-Max-Age|Specifies the duration in which the response result can be retained and cached for a prefetch request initiated by a client program for a particular resource.|
|Access-Control-Expose-Headers|Specifies the custom header information that is allowed to be accessed.|

When you create an HTTP response header, note the following limits:

-   The HTTP response header configurations of a domain affect the response behavior of all client programs such as browsers in this domain. However, the configurations do not affect the behavior of the cache server.
-   Alibaba Cloud CDN supports only the 10 HTTP header parameters described in the preceding table. If you require other HTTP header parameters, .
-   The Access-Control-Allow-Origin parameter can be set as an asterisk \(`*`\) to allow cross-domain requests or a specific domain name such as `www.aliyun.com`.
-   Alibaba Cloud CDN does not support wildcard domains.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the left-side navigation pane of the specified domain, click **Cache**.
5.  Click **HTTP Header**.
6.  On the HTTP Header tab, click **Customize**. 

    ![Customize HTTP Header](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5149/15665309897278_en-US.png)

7.  In the Customize HTTP Header dialog box that appears, set the parameters.
8.  Click **OK**. 

    You can click **Modify** or **Delete** in the Actions column corresponding to an HTTP header to modify or delete the HTTP header.


