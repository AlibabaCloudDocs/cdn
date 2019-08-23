# Configure a rewrite rule {#task_371777 .task}

The rewrite function allows you to modify the requested Uniform Resource Identifier \(URI\) and configure destination URIs for 302 redirects. You can configure multiple rewrite rules as needed. This topic describes how to configure rewrite rules in the CDN console.

If you need to modify the requested URI, create a rewrite rule. For example, if a client requests to visit http://example.com through HTTP, you can create a rewrite rule to redirect the request to https://example.com.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the target domain name and click **Manage**.
4.  In the left-side navigation pane of the specified domain, click **Cache**.
5.  On the Rewrite tab, click **Create**.
6.  Click **Rewrite**.
7.  On the Rewrite tab, click **Create**. 

    ![Create Rewrite Rule](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/301874/156653117148038_en-US.png)

8.  Set the Original URI, Rewritten URI and Flag as needed. 

    A CDN node uses one of the following methods to run rewrite rules:

    -   Redirect: If the requested URI matches the current rule, the CDN node returns a 302 status code and redirects the request to the destination URI.
    -   Break: If the requested URI matches the current rule, the CDN node returns the content of the requested URI, but does not check whether the requested URI matches the remaining rules.
9.  Click **OK**. 

    After a rewrite rule is configured, you can click **Modify** or **Delete** in the Actions column to modify or delete the rewrite rule.


|Example No.|Requested URI|Destination URI|Rewrite flag|Description|
|-----------|-------------|---------------|------------|-----------|
|1|/hello|/index.html|Redirect|When a client requests the content of `http://domain.com/hello`, the CDN node returns a 302 status code and redirects the client to `http://domain.com/index.html`.|
|2|^/hello$|/index.html|Break|When a client requests the content of `http://domain.com/hello`, the CDN node returns the content of `http://domain.com/index.html`, but does not check whether the requested URI matches the remaining rewrite rules.|
|3|^/$|/index.html|Redirect|When a client requests the content of `http://domain.com`, the CDN node returns a 302 status code and redirects the client to `http://domain.com/index.html`.|

