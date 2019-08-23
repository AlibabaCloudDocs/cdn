# Copy configurations {#task_228186 .task}

This topic describes how to copy and move the configurations of a domain to other domains.

Ensure that the domain from which you copy configurations has been enabled and appropriately configured.

Note the following points when you copy configurations of a domain:

-   The coped configurations will overwrite the existing configurations of the domain. Therefore, exercise cautions when performing the operation.
-   The copy operation cannot be undone. The domain from which you copy configurations is enabled and provides a high operational bandwidth. The domain from which you copy configurations is active.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the domain from which you want to copy configurations, and click **Copy Configurations**. 

    ![Copy configurations](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17043/15665280948715_en-US.png)

4.  Select the configuration items you want to copy, and click **Next**. 

    **Note:** 

    -   The origin information cannot be copied at the same time as the other information.
    -   An HTTPS certificate cannot be copied.
    -   Custom HTTP origin headers are copied incrementally. For example, if Domain A has two custom HTTP origin headers and you copy another five HTTP origin headers from Domain B to Domain A, Domain A has seven custom HTTP origin headers.
    -   The HTTP headers are not incrementally copied. For example, if the cache\_control HTTP header is set to private for Domain A and to public for Domain B and you copy the HTTP header configuration of Domain B to Domain A, the cache\_control HTTP header of Domain A is set to public.
    -   If you copy switch-related configurations or Refer or IP address blacklists or whitelists, the new configurations overwrite the original configurations of the target domains.
    -   The new configurations overwrite the original configurations of the target domains.
    ![Select configuration items](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17043/15665280948716_en-US.png)

5.  Select the domains to which you want to copy the configurations, and click **Next**. You can enter a keyword in the search bar to search for a domain.

    ![Select domain](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17043/15665280948717_en-US.png)

6.  In the **Copy Configurations** dialog box, click **OK**.

