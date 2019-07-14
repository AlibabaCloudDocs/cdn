# Rewrite {#task_371777 .task}

This topic describes the rewrite function and how to enable it in the CDN console.

With the rewrite function, you can configure multiple rewrite rules. With each rewrite rule, you can specify the requested Uniform Resource Identifier \(URI\) and the destination URI to which a request is redirected. For example, if a client requests to visit `http://example.com` through HTTP, you can configure a rewrite rule to redirect the request to `https://example.com`.

A CDN node uses one of the following two methods to run rewrite rules:

-   **Redirect**: If the requested URI matches the current rule, the CDN node returns a 302 status code and redirects the request to the destination URI.
-   **Break**: If the requested URI matches the current rule, the CDN node returns the content of the requested URI, but does not check whether the requested URI matches the remaining rules.

1.  Log on to the [CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  Find the domain name you want to set, and click **Manage** in the **Actions** column.
4.  In the left-side navigation pane, click **Cache**.
5.  On the Rewrite tab, click **add**.
6.  Set the parameters as needed and click **OK**. You can select **Redirect** or **Break** for the **Flag** parameter. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/301874/156310385648038_en-US.png)


|Example No.|Requested URI|Destination URI|Rewrite rule flag|Description|
|-----------|-------------|---------------|-----------------|-----------|
|1|/hello|/index.html|Redirect|When a client requests the content of `http://domain.com/hello`, the CDN node returns a 302 status code, asking the client to request the content of `http://domain.com/index.html`|
|2|^/hello$|/index.html|Break|When a client requests the content of `http://domain.com/hello`, the CDN node returns the content of `http://domain.com/index.html`, but does not check whether the requested URI matches the remaining rewrite rules.|
|3|^/$|/index.html|Redirect|When a client requests the content of `http://domain.com`, the CDN node returns a 302 status code, asking the client to request the content of `http://domain.com/index.html`.|

