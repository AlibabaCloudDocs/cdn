---
keyword: [rewrite, cache]
---

# Configure URI rewrite rules

If the requested URI does not match the URI of an origin server, the requested URI can be rewritten into the URI of the origin server. You can configure the rewrite rules in the Alibaba Cloud Content Delivery Network \(CDN\) console. Alibaba Cloud CDN matches a request from a client against the rewrite rules. If a match occurs, Alibaba Cloud CDN performs a 302 redirect to redirect the request to the specified destination URI. You can create multiple rewrite rules based on your business requirements. This topic describes how to create URI rewrite rules in the Alibaba Cloud CDN console.

If you want to modify the requested URI, create a rewrite rule. For example, if a client sends a request to access `http://example.com/hello` over HTTP, you can create a rewrite rule to redirect all requests for `http://example.com/hello` to `http://example.com/index.html`.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Cache**.

5.  Click the **Rewrite** tab.

6.  On the **Rewrite** tab, click **Create**.

7.  In the dialog box that appears, specify the original URI to be rewritten, the destination URI, and the rewrite flag.

    ![Rewrite](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9413247061/p64171.png)

    |Parameter|Description|
    |---------|-----------|
    |**Redirect**|When the requested URI matches the current rule, Alibaba Cloud CDN returns an HTTP status code 302 and redirects the request to the destination URI.|
    |**Break**|When the requested URI matches the current rule, Alibaba Cloud CDN returns the content of the destination URI, and stops matching the requested URI against the remaining rules.|

8.  Click **OK**.

    The newly configured rewrite rule appears on the **Rewrite** tab. You can click **Modify** or **Delete** in the Actions column of the rewrite rule to modify or delete the rewrite rule.

    **Note:** A domain name supports up to 50 rewrite rules.


|Example No.|Requested URI|Destination URI|Redirect flag|Description|
|-----------|-------------|---------------|-------------|-----------|
|Example 1|/hello|/index.html|Redirect|When a client requests the content of `http://domain.com/hello`, the available CDN node that is closest to the client returns the HTTP status code 302 and redirects the request to `http://domain.com/index.html`.|
|Example 2|^/hello$|/index.html|Break|When a client requests the content of `http://domain.com/hello`, the available CDN node that is closest to the client returns the content of `http://domain.com/index.html`. The CDN node does not check whether the requested URI matches the remaining rewrite rules.|
|Example 3|^/$|/index.html|Redirect|When a client requests the content of `http://domain.com`, the available CDN node that is closest to the client returns the HTTP status code 302 and redirects the request to `http://domain.com/index.html`.|
|Example 4|/hello|/hello/index.html|Redirect|When a client requests the content of `http://domain.com/hello`, the available CDN node that is closest to the client returns the HTTP status code 302 and redirects the request to `http://domain.com/hello/index.html`.|

