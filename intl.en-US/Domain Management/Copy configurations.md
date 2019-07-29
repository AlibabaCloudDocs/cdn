# Copy configurations {#task_228186 .task}

This topic describes how to copy and move the configurations of a domain to other domains.

-   The new configurations are suitable to the target domains.
-   The domain from which you copy configurations is enabled and appropriately configured.
-   The domain from which you copy configurations is active.
-   The domain from which you copy configurations provides a high operational bandwidth.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com/overview).
2.  In the left-side navigation pane, choose **Domain Names**, find the domain from which you want to copy configurations, and in the **Actions** column click **Copy Configurations**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17043/15644085758715_en-US.png)

3.  Select the configuration items you want to copy, and click **Next**. 

    **Note:** 

    -   The origin information cannot be copied at the same time as the other information.
    -   An HTTPS certificate cannot be copied.
    -   Custom HTTP origin headers are copied incrementally. For example, if Domain A has two custom HTTP origin headers and you copy another five HTTP origin headers from Domain B to Domain A, then Domain A has seven custom HTTP origin headers.
    -   If you copy HTTP headers, switch-related configurations, or Refer or IP address blacklists or whitelists, the new configurations overwrite the original configurations of the target domains. For example, the **cache\_control** HTTP header is set to **private** for Domain A and to **public** for Domain B and you copy the HTTP header configuration of Domain B to Domain A, then the **cache\_control** HTTP header of Domain A is set to **public**.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17043/15644085758716_en-US.png)

4.  Select the domains to which you want to copy the configurations, and click **Next**. You can enter a keyword in the search bar to search for a domain.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17043/15644085758717_en-US.png)

5.  In the **Copy Configurations** dialog box, click **OK**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17043/15644085758719_en-US.png)


