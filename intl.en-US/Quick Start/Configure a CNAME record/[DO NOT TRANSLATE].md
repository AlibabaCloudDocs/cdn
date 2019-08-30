# Configure a CNAME on Xinnet {#task_187634 .task}

This topic describes how to configure a CNAME on Xinnet. After you add a domain, Alibaba Cloud CDN assigns a CNAME address to the domain. You must point the domain to its CNAME address so that CDN can direct the requests destined for the domain to CDN nodes.

1.  Obtain the CNAME of the target domain name. To obtain the CNAME, complete these steps: 
    1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#/cdn).
    2.  In the left-side navigation pane, choose **Domain Names**, find the target domain name and in the **CNAME** column copy the CNAME. 

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/156715059345282_en-US.png)

2.  Add a CNAME record to Xinnet. To add a CNAME record to Xinnet, complete these steps: 
    1.  Log on to the DNS console of Xinnet.
    2.  On the DNS page for the target domain name, click the button for adding a CNAME record.
    3.  Set the following parameters: 
        -   Type: Select CNAME.
        -   Host: Enter the prefix of the domain name.
        -   ISP Line: Retain the default value.
        -   Value: Enter the CNAME obtained in Step 1.
        -   TTL: Retain the default value.
    4.  Submit the settings. The CDN service takes effect immediately after the new CNAME record takes effect.

        **Note:** 

        -   A new CNAME record takes effect immediately, but a modified CNAME record takes effect within 72 hours.
        -   After you add a CNAME record, it takes about 10 minutes to update the status of the corresponding domain name.
3.  Verify that the new CNAME record takes effect. 

    **Note:** The time when a new CNAME record takes effect varies depending on the DNS provider.

    You can run the ping or dig command to check whether the target domain is accessible. If the access request is directed to `*.*kunlun*.com`, the CNAME record and CDN service both take effect.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/15671505936060_en-US.png)


