# Configure the parameter rewrite feature

If you want to modify the parameters in URLs of back-to-origin requests, you can create rules to rewrite the parameters. This topic describes how to configure the parameter rewrite feature in the Alibaba Cloud Content Delivery Network \(CDN\) console.

If the parameters in a request URL are different from the parameters that are required in the back-to-origin request, you can create parameter rewrite rules. These rules allow you to ignore, add, delete, retain, or modify the parameters.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Back-to-origin**.

5.  Click the **Parameter Rewrite** tab.

6.  On the **Parameter Rewrite** tab, turn on **Rewrite Parameters**.

    ![Rewrite parameters](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2326297061/p83519.jpg)

7.  In the Rewrite Parameters dialog box, set the required parameters.

    You can configure different types of rewrite rules or specify multiple parameters for a rewrite rule based on your business requirements.

    ![Rewrite parameters](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2326297061/p85278.png)

8.  Click **OK** to apply and run the rewrite rules.

    To modify a rewrite rule, find the rule on the **Parameter Rewrite** tab, and click **Modify** in the Actions column of the rule.

    ![Rewrite parameters](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2326297061/p85281.png)

    When you configure the parameter rewrite feature, take note of the following rules:

    -   The following rewrite rules take effect in descending order of priority: the **Add** rule, the **Delete** rule, the **Reserve Only** rule, and the **Modify** rule.
    -   The **Ignore Parameters** feature and the **Reserve Only** rule are mutually exclusive. Do not configure them for the same domain name to avoid feature conflicts.
    -   If you turn on **Ignore Parameters** and do not set the **Reserve Only** rule, all parameters that are included in the original request URLs will be ignored. However, the Add rule and the Delete rule still take effect because they have higher priorities.
    -   If you enter parameters in the **Reserve Only** field and turn off **Ignore Parameters**, only the specified parameters are retained in the original request URLs. However, the Add rule and the Delete rule still take effect because they have higher priorities.
    **Note:**

    The parameter rewrite feature may have the following conflicts with other features:

    -   The parameter rewrite feature is used to rewrite the parameters in request URLs. This feature may conflict with a URI rewrite rule whose flag is set to enhance\_break. If you configure both features, make sure that no conflicts exist.********
    -   The parameter rewrite feature is used to rewrite the parameters in request URLs. This feature may conflict with the settings of the **Retain Parameters** or **Ignore Parameters** parameter. To retain or ignore parameters, in the left-side navigation pane of the Alibaba Cloud CDN console, choose **Domain Names** \> **Optimization**. If you configure these three features for the same domain name, make sure that no conflicts exist.****
    -   The parameter rewrite feature functions on the CDN nodes that communicate with origin servers. This feature does not affect the internal links of Alibaba Cloud CDN or rewrite the cache keys. The settings of **Retain Parameters** or **Ignore Parameters** function on the edge nodes. These settings affect the internal links of Alibaba Cloud CDN and rewrite cache keys.****

Example 1

|Ignore Parameters|Enabled|
|Add|None|
|Delete|None|
|Reserve Only|None|
|Modify|None|
|Description|Original request: `http://domain.com/index.html?code1=1&code2=2&code3=3` Rewritten request: `http://domain.com/index.html` |

Example 2

|Ignore Parameters|Disabled|
|Add|None|
|Delete|None|
|Reserve Only|code2|
|Modify|None|
|Description|Original request: `http://domain.com/index.html?code1=1&code2=2&code3=3` Rewritten request: `http://domain.com/index.html?code2=2` |

Example 3

|Ignore Parameters|Disabled|
|Add|code4=4|
|Delete|code2|
|Reserve Only|None|
|Modify|code3=0|
|Description|Original request: `http://domain.com/index.html?code1=1&code2=2&code3=3` Rewritten request: `http://domain.com/index.html?code1=1&code3=0&code4=4` |

