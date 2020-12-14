# Configure the URI rewrite feature

If you want to rewrite the URI that is included in each back-to-origin request, you can create rules to rewrite URIs. This topic describes how to configure the URI rewrite feature in the Alibaba Cloud Content Delivery Network \(CDN\) console.

If a request URI does not match the URI of the requested resource on an origin server, you must rewrite the request URI. You can create multiple rewrite rules based on your business requirements.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Back-to-origin**.

5.  Click the **URI Rewrite** tab.

6.  On the **URI Rewrite** tab, click **Add**.

7.  In the URI Rewrite dialog box, set the Source URI and Target URI fields, and specify a flag.

    ![Configure the URI rewrite feature](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0326197061/p83537.png)

    |Parameter|Example|Description|
    |---------|-------|-----------|
    |Source URI|^/hello$|Enter a URI that starts with a forward slash \(/\). The specified URI must exclude the string http:// and domain names. Perl Compatible Regular Expressions \(PCRE\) such as ^/hello$ are supported.|
    |Target URI|/hello/test|Enter a URI that starts with a forward slash \(/\). The specified URI must exclude the string http:// and domain names.|
    |Flag|None|If multiple rules are configured, and this rule is matched, the system continues to match rules.|
    |break|If this rule is matched, only the URI is rewritten. The system stops matching rules.|
    |enhance\_break|If this rule is matched, the URI and its parameters are rewritten. The system stops matching rules.|

    **Note:**

    -   If you set the flag of a URI rewrite rule to Break, the query parameters in a request URI will not be rewritten. However, the settings of **Parameter Rewrite** feature still take effect.
    -   If you set the flag of a URI rewrite rule to enhance break, the parameter rewrite settings may conflict with the settings of **Parameter Rewrite**. If you configure both features for the same domain name, make sure that no conflicts exist.
    -   If you set the flag of a URI rewrite rule to enhance break, the parameter rewrite settings may conflict with the settings of **Retain Parameters** or **Ignore Parameters**. To retain or ignore parameters, in the left-side navigation pane of the Alibaba Cloud CDN console, choose **Domain Names** \> **Optimization**. If you configure these three features for the same domain name, make sure that no conflicts exist.
8.  Click **OK** to apply and run the rewrite rule.

    To modify or delete a rewrite rule, find the rule on the **URI Rewrite** tab, and click **Modify** or **Delete** in the Actions column of the rule.

    **Note:**

    -   A domain supports up to 50 URI rewrite rules.
    -   The system runs the listed rewrite rules on the URI Rewrite tab in order from top to bottom. A change to this order may lead to a different rewrite result.
    -   The URI rewrite feature is different from the rewrite feature on the Cache page. The rewrite feature functions on the edge nodes. This feature affects the internal links of Alibaba Cloud CDN, and rewrites cache keys. The URI rewrite feature functions on the CDN nodes that communicate with origin servers. This feature does not affect the internal links of Alibaba Cloud CDN or rewrite the cache keys.

Example 1

|Source URI|^/hello$|
|Target URI|/index.html|
|Flag|None|
|Description|Original request: `http://domain.com/hello`Rewritten request: `http://domain.com/index.html`

The system continues to match this request against the subsequent URI rewrite rules that are listed on the **URI Rewrite** tab. |

Example 2

|Source URI|^/hello.jpg$|
|Target URI|/image/hello.jpg|
|Flag|break|
|Description|Original request: `http://domain.com/hello.jpg`Rewritten request: `http://domain.com/image/hello.jpg`

The system stops matching this request against the subsequent URI rewrite rules that are listed on the **URI Rewrite** tab. |

Example 3

|Source URI|^/hello.jpg? code=123$|
|Target URI|/image/hello.jpg? code=321|
|Flag|enhance\_break|
|Description|Original request: `http://domain.com/hello.jpg?code=123`Rewritten request: `http://domain.com/image/hello.jpg?code=321`

The system stops matching this request against the subsequent URI rewrite rules that are listed on the **URI Rewrite** tab.|

