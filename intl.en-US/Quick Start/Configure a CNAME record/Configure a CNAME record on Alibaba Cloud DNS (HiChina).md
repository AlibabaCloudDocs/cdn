# Configure a CNAME record on Alibaba Cloud DNS \(HiChina\) {#task_187531 .task}

After you add a CDN domain, CDN will assign a CNAME to the CDN domain. To enable the CDN service, you must point a CDN domain to its CNAME. After that, requests destined for the CDN domain can be redirected to CDN nodes. This topic uses a domain that is added to Alibaba Cloud DNS \(HiChina\) as an example.

1.  Obtain the CNAME of a CDN domain. 
    1.  Log on to the [CDN console](https://partners-intl.aliyun.com/login-required#cdn).
    2.  In the left-side navigation pane, click **Domain Names**.
    3.  On the Domain Names page, copy the CNAME of a CDN domain. 

        ![Domain names](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/156715045245282_en-US.png)

2.  Add a CNAME record. 
    1.  Log on to [Alibaba Cloud DNS console](https://partners-intl.aliyun.com/login-required#/dns).
    2.  On the Manage DNS page, click the Domains tab and select a domain. Then, click **Configure** in the Actions column corresponding to the domain. 

        ![Manage DNS](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/156715045245284_en-US.png)

    3.  Click **Add Record** to add a CNAME record. 

        ![DNS Settings](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/156715045245285_en-US.png)

        -   Type: Select `CNAME`.
        -   Host: Enter the prefix of the domain.

            |Domain name|Corresponding host record|
            |:----------|:------------------------|
            |`testcdn.aliyun.com`|`testcdn`|
            |`www.aliyun.com`|`www`|
            |`aliyun.com`|`@`|
            |`*.aliyun.com`|`*`|

        -   ISP Line: Use the default value.
        -   Value: Enter the CNAME value obtained in step 1.
        -   TTL: Use the default value.
    4.  Click **OK**. 

        A CNAME record is configured. The CDN service takes effect immediately after a new CNAME record takes effect.

        **Note:** 

        -   A new CNAME record takes effect immediately. However, if you modify a CNAME record, it takes effect within 72 hours.
        -   After you configure a CNAME record, it takes about 10 minutes to update the status. The message "You must add the CNAME record" may still appear on the Domain Names page in the CDN console. Ignore this message.
3.  Verify whether a new CNAME record takes effect. 

    The time when a new CNAME record takes effect depends on the DNS provider. You can run the `ping` or `dig` command followed by a CDN domain to verify whether a new CNAME record takes effect. If the CDN domain is redirected to `*.*kunlun*.com`, both the CNAME record and CDN features have taken effect.

    ![[DO NOT TRANSLATE]](images/45287_en-US.png)


