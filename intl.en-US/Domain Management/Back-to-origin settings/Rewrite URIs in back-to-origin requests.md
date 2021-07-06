# Rewrite URIs in back-to-origin requests

If you want to rewrite the Uniform Resource Identifiers \(URIs\) that are included in back-to-origin requests, you can create rewrite rules to rewrite URIs. This topic describes how to set a URI rewrite rule in the Alibaba Cloud Content Delivery Network \(CDN\) console.

If a request URI does not match the URI of the requested resource on an origin server, you must rewrite the request URI. You can create multiple rewrite rules based on your business requirements.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the left-side management pane of the domain name, click **Back-to-origin**.

5.  Click the **URI Rewrite** tab.

6.  Click **Add**.

7.  In the URI Rewrite dialog box, set the Original URI and Final URI fields, and specify a flag.

    ![Rewrite URIs](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0326197061/p83537.png)

    |Parameter|Example|Description|
    |---------|-------|-----------|
    |Original URI|^/hello$|Enter a URI that starts with a forward slash \(/\). The URI cannot contain the string http:// or domain names. Perl Compatible Regular Expressions \(PCRE\) such as ^/hello$ are supported.|
    |Final URI|/hello/test|Enter a URI that starts with a forward slash \(/\). The URI cannot contain the string http:// or domain names.|
    |Flag|None|If multiple rules are configured, and the current rule is matched, the system continues to match the request against the subsequent rules.|
    |break|If the current rule is matched, only the URI is rewritten. In this case, the system stops matching the request against the subsequent rules.|
    |enhance break|If the current rule is matched, the URI and its parameters are rewritten. In this case, the system stops matching the request against the subsequent rules.|

    **Note:**

    -   If you set the flag of a **URI rewrite rule** to `Break`, the query parameters in a request URI will not be rewritten. However, the **Parameter Rewrite** feature still takes effect.
    -   If you set the flag of a **URI rewrite rule** to `enhance break`, the parameter rewrite settings may conflict with the settings of the **Parameter Rewrite** feature. If you configure both features for the same domain name, make sure that the features do not conflict with each other.
    -   If you set the flag of a **URI rewrite rule** to enhance break, the parameter rewrite settings may conflict with the settings of the **Retain Parameters** or **Ignore Parameters** feature. To retain or ignore parameters, choose **Domain Names** \> **Optimization** in the left-side navigation pane of the Alibaba Cloud CDN console. If you configure these three features for the same domain name, make sure that the features do not conflict with each other.
8.  Click **OK** to apply the rewrite rule.

    To modify or delete a rewrite rule, find the rule on the **URI Rewrite** tab and click **Modify** or **Delete** in the Actions column.

    **Note:**

    -   Each domain name supports up to 50 **URI rewrite rules**.
    -   The system runs the rewrite rules that are listed on the URI Rewrite tab in order from top to bottom. A change to this order may lead to a different rewrite result.
    -   The **URI rewrite** feature is different from the **rewrite** feature on the Cache page. The **rewrite** feature functions on CDN nodes. It affects the internal services of Alibaba Cloud CDN, and rewrites cache keys. The **URI rewrite** feature functions on the CDN nodes that communicate with origin servers. It does not affect the internal services of Alibaba Cloud CDN or rewrite cache keys.

Example 1

|Original URI|^/hello$|
|Final URI|/index.html|
|Flag|None|
|Description|Original request: `http://domain.com/hello`Final request: `http://domain.com/index.html`

The system continues to match this request against the subsequent URI rewrite rules that are listed on the **URI Rewrite** tab. |

Example 2

|Original URI|^/hello.jpg$|
|Final URI|/image/hello.jpg|
|Flag|break|
|Description|Original request: `http://domain.com/hello.jpg`Final request: `http://domain.com/image/hello.jpg`

The system stops matching this request against the subsequent URI rewrite rules that are listed on the **URI Rewrite** tab. |

Example 3

|Original URI|^/hello.jpg?code=123$|
|Final URI|/image/hello.jpg?code=321|
|Flag|enhance break|
|Description|Original request: `http://domain.com/hello.jpg?code=123`Final request: `http://domain.com/image/hello.jpg?code=321`

The system stops matching this request against the subsequent URI rewrite rules that are listed on the **URI Rewrite** tab.|

Example 4

Scenario: Add a URI when the file name is a variable.

Example: Add the /image path to the URI of all files in the root directory. For example, you can rewrite /xxx that is included in URIs to /image/xxx. xxx is a file name, such as /hello.jpg and /hello.html.

|Original URI|^\(.\*\)$**Note:** ^\(.\*\)$ matches any characters, and a pair of parentheses \(\) represents a group. You can use $1 in the final URI to call variables in the group. |
|Final URI|/image$1**Note:** $1, the first special replacement pattern, represents the content that matches the expression in the first pair of parentheses \(\) in a regular expression. $2, the second special replacement pattern, represents the content that matches the expression in the second pair of parentheses \(\). $n represents the nth special replacement pattern. |
|Flag|break|
|Description|-   Original request: `http://domain.com/hello.jpg`

Final request: `http://domain.com/image/hello.jpg`

-   Original request: `http://domain.com/hello.html`

Final request: `http://domain.com/image/hello.html`


The system stops matching this request against the subsequent URI rewrite rules that are listed on the **URI Rewrite** tab.|

Example 5

Scenario: Add a URI when the file name is a variable.

Example: Add the /image path to the URI of all files in the /live directory. For example, you can rewrite /live/xxx that is included in URIs to /image/live/xxx. xxx is a file name, such as /live/hello.jpg and /live/hello.html.

|Original URI|^/live/\(.\*\)$|
|Final URI|/image/live/$1|
|Flag|break|
|Description|-   Original request: `http://domain.com/live/hello.jpg`

Final request: `http://domain.com/image/live/hello.jpg`

-   Original request: `http://domain.com/live/hello.html`

Final request: `http://domain.com/image/live/hello.html`


The system stops matching this request against the subsequent URI rewrite rules that are listed on the **URI Rewrite** tab.|

**Related topics**  


[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md)

