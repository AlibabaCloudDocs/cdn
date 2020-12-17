---
keyword: [rewrite, cache]
---

# Create a rewrite rule

If the requested URI does not match the URI of the requested resource on the origin server, the requested URI must be rewritten to match the destination URI. To rewrite URIs, you must create rewrite rules. After Alibaba Cloud Content Delivery Network \(CDN\) receives a request, Alibaba Cloud CDN compares the request with the rewrite rules. If the request matches the rules, Alibaba Cloud CDN performs a 302 redirect to redirect the request to the destination URI. You can create one or more rewrite rules based on your business requirements. This topic describes how to create a rewrite rule.

To enable Alibaba Cloud CDN to rewrite requested URIs, you must create rewrite rules. For example, if a client requests the content of `http://example.com/hello` over HTTP, you can create a rewrite rule to redirect all the requests destined for `http://example.com/hello` to `http://example.com/index.html`.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Cache**.

5.  Click the **Rewrite** tab.

6.  On the **Rewrite** tab, click **Create**.

7.  In the Create Rewrite Rule dialog box, specify the original URI to be rewritten, the destination URI, and the rewrite flag.

    **Note:** You can configure a maximum of 50 rewrite rules for each domain name.

    ![Create a rewrite rule](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9413247061/p64171.png)

    |Parameter|Description|
    |---------|-----------|
    |**Redirect**|When the requested URI matches the current rule, Alibaba Cloud CDN returns a 302 status code and redirects the request to the destination URI.|
    |**Break**|When the requested URI matches the current rule, Alibaba Cloud CDN returns the content of the destination URI, and stops comparing the requested URI with the remaining rules.|

8.  Click **OK**.

    On the **Rewrite** tab, you can click **Modify** or **Delete** in the Actions column to modify or delete a rewrite rule.


**Note:** You can use regular expressions to specify the original URI and the destination URI. Do not include braces \(`{ }`\) in the regular expressions. Rewrite rules that contain braces \(`{ }`\) cannot take effect.

|Example|Original URI|Destination URI|Rewrite flag|Description|
|-------|------------|---------------|------------|-----------|
|Example 1|/hello|/index.html|Redirect|When a client requests the content of `http://domain.com/hello`, the CDN node returns a 302 status code and redirects the request to `http://domain.com/index.html`.|
|Example 2|^/hello$|/index.html|Break|When a client requests the content of `http://domain.com/hello`, the CDN node returns the content of `http://domain.com/index.html`, but stop comparing the requested URI with the remaining rewrite rules.|
|Example 3|^/$|/index.html|Redirect|When a client requests the content of `http://domain.com`, the CDN node returns a 302 status code and redirects the request to `http://domain.com/index.html`.|
|Example 4|/hello|/hello/index.html|Redirect|When a client requests the content of `http://domain.com/hello`, the CDN node returns a 302 status code and redirects the request to `http://domain.com/hello/index.html`.|

