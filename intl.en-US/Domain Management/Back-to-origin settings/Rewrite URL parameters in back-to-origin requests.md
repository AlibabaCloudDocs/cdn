# Rewrite URL parameters in back-to-origin requests

Alibaba Cloud Content Delivery Network \(CDN\) allows you to rewrite URL parameters in requests before they are redirected to origin servers. This topic describes how to rewrite URL parameters in back-to-origin requests.

If the parameters in a request URL are different from those required in the request that you want to redirect to the origin server, you can create parameter rewrite rules to rewrite the URL parameters. These rules allow Alibaba Cloud CDN to ignore, add, delete, retain, and modify the parameters.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the left-side management pane of the domain name that you want to manage, click **Back-to-origin**.

5.  Click the **Parameter Rewrite** tab.

6.  Turn on **Rewrite Parameters**.

    ![Rewrite parameters](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2326297061/p83519.jpg)

7.  In the Rewrite Parameters dialog box, set the required parameters.

    You can configure different types of rewrite rule or specify multiple parameters in a rewrite rule based on your business requirements. For more information, see [Procedure](#example_cmf_gh1_big).

    ![Rewrite parameters](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5879745261/p85278.png)

8.  Click **OK** to apply the rewrite rule.

    To modify a rewrite rule, find the rule on the **Parameter Rewrite** tab, and click **Modify** in the Actions column.

    ![Rewrite parameters](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2326297061/p85281.png)

    When you create a parameter rewrite rule, take note of the following rules:

    -   The following rewrite rules take effect in descending order of priority: the **Add** rule, the **Delete** rule, the **Reserve Only** rule, and the **Modify** rule.
    -   The **Ignore Parameters** feature and the **Reserve Only** rule are mutually exclusive. To prevent errors, do not configure them for the same domain name.
    -   If you turn on **Ignore Parameters** and do not set the **Reserve Only** rule, all parameters that are included in the original request URLs will be ignored. However, the Add rule and the Delete rule still take effect because they have higher priorities.
    -   If you enter parameters in the **Reserve Only** field and turn off **Ignore Parameters**, only the specified parameters are retained in the original request URLs. However, the Add rule and the Delete rule still take effect because they have higher priorities.
    **Note:**

    The parameter rewrite feature may have the following conflicts with other features:

    -   The **parameter rewrite** feature is used to rewrite parameters in request URLs. This feature may conflict with **Uniform Resource Identifier \(URI\) rewrite rules** whose flag is set to `enhance_break`. If you configure both features, make sure that the features do not conflict with each other.
    -   The **parameter rewrite** feature is used to rewrite parameters in request URLs. This feature may conflict with the settings of the **Retain Parameters** or **Ignore Parameters** parameter. To retain or ignore parameters, choose **Domain Names** \> **Optimization** in the left-side navigation pane of the Alibaba Cloud CDN console. If you configure these three features for the same domain name, make sure that the features do not conflict with each other.
    -   The **parameter rewrite** feature takes effect on CDN nodes that communicate with origin servers. This feature does not affect the internal services of Alibaba Cloud CDN or rewrite the cache keys. The settings of **Retain Parameters** or **Ignore Parameters** take effect on the CDN nodes. These settings affect the internal services of Alibaba Cloud CDN and rewrite cache keys.

Example 1

|Ignore Parameters|Enabled|
|Add|Disabled|
|Delete|Disabled|
|Reserve Only|Disabled|
|Modify|Disabled|
|Expected result|Original request: `http://domain.com/index.html?code1=1&code2=2&code3=3`Final request: `http://domain.com/index.html` |

Example 2

|Ignore Parameters|Disabled|
|Add|Disabled|
|Delete|Disabled|
|Reserve Only|code2|
|Modify|Disabled|
|Expected result|Original request: `http://domain.com/index.html?code1=1&code2=2&code3=3`Final request: `http://domain.com/index.html?code2=2` |

Example 3

|Ignore Parameters|Disabled|
|Add|code4=4|
|Delete parameters|code2|
|Reserve Only|Disabled|
|Modify|code3=0|
|Description|Original request: `http://domain.com/index.html?code1=1&code2=2&code3=3`Final request: `http://domain.com/index.html?code1=1&code3=0&code4=4` |

**Related topics**  


[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md)

