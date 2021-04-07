---
keyword: [rewrite, cache]
---

# Create a URI rewrite rule

If the URI in a request does not match the URI of the requested resource on the origin server, you must overwrite the request URI with the resource URI. To rewrite URIs, you must create a rewrite rule. After Alibaba Cloud Content Delivery Network \(CDN\) receives a request, Alibaba Cloud CDN compares the request with the rewrite rule. If the request matches the rewrite rule, Alibaba Cloud CDN performs a 302 redirect to redirect the request to the destination URI.

## Scenarios

If you want to rewrite URIs in requests to the URIs of the requested resources, you can create a rewrite rule. If a request matches the rewrite rule, Alibaba Cloud CDN performs a 302 redirect to redirect the request to the destination URI. For example, users visit `www.example.com/hello` over HTTP. After you create a rewrite rule, requests that are sent to `www.example.com/hello` are redirected to `www.example.com/index.html`.

## Procedure

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Cache**.

5.  Click the **Rewrite** tab.

6.  Click **Create**. In the Create Rewrite Rule dialog box, set the Original URI, Rewritten URI, and Flag parameters.

    **Note:**

    -   You can create at most 50 rewrite rules for each domain name.
    -   You can use regular expressions to specify the original URI and rewritten URI. Do not use braces \(`{}`\) in the regular expressions. Regular expressions that contain braces \(`{}`\) do not take effect.
    ![Create a rewrite rule](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9413247061/p64171.png)

    |Parameter|Description|
    |---------|-----------|
    |**Original URI**|Enter a URI that starts with a forward slash \(/\). The URI cannot contain http:// or domain names. You can use a Perl-compatible regular expression \(PCRE\) to specify the URI, for example, ^/hello$.|
    |**Rewritten URI**|Enter a URI that starts with a forward slash \(/\). The URI cannot contain http:// or domain names. Example: /index.html.|
    |**Flag**|**Redirect** and **Break** are supported.     -   **Redirect**: If the URI in a request matches the current rule, Alibaba Cloud CDN performs a 302 redirect to redirect the request to the destination URI.
    -   **Break**: If the URI in a request matches the current rule, Alibaba Cloud CDN does not rewrite the URI and ignores other rewrite rules. |

7.  Click **OK**.

    After a rewrite rule is created, it is displayed on the **Rewrite** tab. You can **Modify** or **Delete** the rule.


## Examples

|Example|Original URI|Rewritten URI|Flag|Description|
|-------|------------|-------------|----|-----------|
|Example 1|/hello|/index.html|Redirect|Requests are sent to `www.domain.com/hello`. CDN nodes perform a 302 redirect to redirect the requests to `www.domain.com/index.html`.|
|Example 2|^/$|/index.html|Redirect|Requests are sent to `www.domain.com`. CDN nodes perform a 302 redirect to redirect the requests to `www.domain.com/index.html`.|
|Example 3|/hello|/hello/index.html|Redirect|Requests are sent to `www.domain.com/hello`. CDN nodes perform a 302 redirect to redirect the requests to `www.domain.com/hello/index.html`.|
|Example 4|^/hello$|/index.html|Break|Requests are sent to `www.domain.com/hello`. CDN nodes perform a 302 redirect to redirect the requests to `www.domain.com/index.html` and ignore other rewrite rules.|

## Related API operations

[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md)

