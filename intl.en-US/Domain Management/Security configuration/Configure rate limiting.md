---
keyword: [security, rate limiting]
---

# Configure rate limiting

If the response time of your website is increased due to HTTP flood attacks, you can use the rate limiting feature to block specific requests that are sent to your website. This feature can be used to block requests within seconds and improve website security. This topic describes how to configure rate limiting.

You must apply for the rate limiting feature of Alibaba Cloud Content Delivery Network \(CDN\) before you can use this feature. To apply for this feature, you can join one of the following DingTalk groups:

-   Group 1: 23184221. No more members can be added to the group.
-   Group 2: 33298914.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the left-side domain name management pane, click **Security Settings**.

5.  On the **Rate Limiting** page, turn on **Set Rate Limiting**.

6.  Click **Modify**.

7.  In the **Rate Limiting** dialog box, enable **Parameter Check** and select an option of **Control Mode**.

    |Parameter|Description|
    |---------|-----------|
    |**Parameter Check**|After the parameter check feature is enabled, the rate limiting feature uses the specified URIs with all parameters to compare requests. The parameter check feature is used to check only URIs. Custom match rules that are set for the custom rate limiting mode do not apply to the parameter check feature.|
    |**Control Mode**|You can select one of the following modes:     -   **Normal**

The default rate limiting mode. Select this mode to prevent false positives if the network traffic of your website is within the expected range.

    -   **Emergency**

Select this mode if your website responds slowly and exceptions are detected in network traffic, CPU usage, memory usage, and other performance indicators.

    -   **Custom**

Select this mode if you want to customize rate limiting rules based on your business requirements. This mode does not provide default rules. You must set custom rules based on your business requirements. For more information about how to set a custom rule, see [Step 8](#step_9k3_pp6_0y2). |

    ![Configure rate limiting](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4013286061/p71196.png)

8.  If you set **Control Mode** to **Custom**, you must set a custom rate limiting rule.

    1.  Click **Create Rule** on the right side of **Custom Rules**.

        **Note:** You can create up to five custom rules in the Alibaba Cloud CDN console.

    2.  Follow the instructions to create a custom rule. The following table describes the parameters.

        ![Parameters used to create a custom rule](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4013286061/p75891.png)

        |Parameter|Description|
        |---------|-----------|
        |**Rule Name**|The name must be 4 to 30 characters in length and can contain letters and digits. The names of rules that are set for the same accelerated domain name must be unique.|
        |**URI**|Enter the URI that you want to protect, for example, `/register`. You can include parameters in the URI. You must also enable the parameter check feature if you want to apply the rule to the entire URI, including the parameters. Example: `/user? action=login`.|
        |**Matching Mode**|You can select one of the following match rules. The rate limiting rule applies the match rules in the following order: exact match, prefix match, and fuzzy match. You can adjust the priorities of the match rules in a rate limiting rule. The match rules are listed and executed based on their priorities.         -   **Exact Match**

In this mode, requests are counted only if the request URI exactly matches the specified URI.

        -   **Prefix Match**

In this mode, requests are counted if the request URI starts with the specified URI. For example, if the URI is set to `/register`, requests that are sent to `/register.html` are counted.

        -   **Fuzzy Match**

In this mode, requests are counted if the request URI matches the specified regular expression. Regular expressions support only periods \(.\) and asterisks \(\*\). A period \(.\) specifies that the rate limiting rule compares each individual character. An asterisk \(\*\) specifies that the rate limiting rule considers the request a match if any character matches the specified regular expression. |
        |**Interval**|Set a time period during which request statistics are collected. This parameter takes effect only if you specify a check object. The time period must be from 10 seconds to 600 seconds.|
        |**Check and Block Object**|You can select one of the following types of objects:         -   **Source IP**
        -   **Header**
        -   **Domain**
        -   **URL Parameter** |
        |**Matching Rule**|Click **Add Rule** and set the following parameters: **Type**, **Option**, **Operator**, and **Value**.|
        |**Action**|Specify an action to be performed after a request matches the specified match rule, and the period of time that the source IP address remains blocked if the Action parameter is set to Block.         -   **Block**

If this action is triggered, a 403 HTTP status code is returned to the request.

        -   **Bot Detection**

If this action is triggered, a 200 HTTP status code is returned to the request and the request is redirected for verification. If the request passes the verification, it is allowed to access the requested resources. For example, if an IP address initiates requests more than five times within 20 seconds, human-machine identification is triggered. All requests from the IP address within the following 10 minutes are verified. Requests from this IP address are allowed to access resources only if the IP address passes human-machine identification. |
        |**TTL**|Specify how long IP addresses remain blocked. The time period must be at least 60 seconds.|

        The following table lists some sample custom rules.

        |Scenario|Check object|Interval|Matching rule|Action|TTL|
        |--------|------------|--------|-------------|------|---|
        |4xx or 5xx errors|IP|10 seconds|`"status_ratio|404">60%`&&`"count">50`|Block|10 minutes|
        |Queries per second \(QPS\) anomalies|Domain name|10 seconds|`"count">N`|Human-machine identification|10 minutes|

        **Note:** Specify a value for N based on your business requirements.

    3.  Click **OK**.


