# Test whether a domain name is accessible \(optional\)

After you add a domain name to Alibaba Cloud Content Delivery Network \(CDN\), we recommend that you test whether the domain name is accessible before you update the Canonical Name \(CNAME\) record of the domain name. This ensures that DNS updates do not affect the services of the domain name. This topic describes how to test whether a domain name is accessible after it is mapped to the CNAME assigned by Alibaba Cloud CDN.

**Note:** During the test, requests are sent to CDN nodes. You are charged for the basic services and value-added services of Alibaba Cloud CDN that you have used. The billing rules of Alibaba Cloud CDN apply in the test. For more information, see [Metering methods](/intl.en-US/Pricing/Overview.md).

## Prerequisites

-   A domain name is added to Alibaba Cloud CDN. If you have not added a domain name to Alibaba Cloud CDN, add one to Alibaba Cloud CDN. For more information, see [Add a domain name to Alibaba Cloud CDN](/intl.en-US/Quick Start/Add a domain name to Alibaba Cloud CDN.md).
-   You can access services of the origin server.

## Procedure

1.  Obtain the CNAME that is assigned to the domain name.

    1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

    2.  In the left-side navigation pane, click **Domain Names**.

    3.  On the **Domain Names** page, copy the CNAME of the domain name.

        ![Domain Names](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8550435161/p66555.png)

2.  Obtain the IP address of the CNAME.

    **Note:** The following IP address is an example retuned by running the ping command and is for reference only. To obtain the actual IP address of your CNAME, run the ping command to ping your CNAME.

    -   Windows: To obtain the IP address of your CNAME, open the command-line interface and run the ping command to ping your CNAME.
    -   macOS: To obtain the IP address of your CNAME, open the command-line interface and run the dig command to dig your CNAME.

        ![MAc dig CNAME](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5331627161/p125264.png)

3.  Add the IP address and domain name to the hosts file of the on-premises machine.

    You must add the IP address obtained from Step 2 and the accelerated domain name to the hosts file of the on-premises machine. Make sure that you add the IP address before the accelerated domain name.

    In this example, the accelerated domain name is example.com, the CNAME is example.com.w.kunlunsl.com, and the IP address of the CNAME is 203.0.113.1.

    -   The path of the hosts file in Windows is C:\\Windows\\System32\\drivers\\etc\\hosts. The following figure is an example.

        ![Example](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7097648161/p254611.png)

    -   The path of the hosts file in macOS is Finder\>Go\>Go to the folder\>/etc/hosts. The following figure is an example.

        ![The hosts file](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5331627161/p125298.png)

4.  Test whether the accelerated domain name is accessible.

    After you add the IP address and accelerated domain name to the hosts file, you can open the browser and enter the accelerated domain name in the address bar to test the connectivity. You can view the test result by using the developer tool of the browser.

    -   If the IP address in the **Remote Address** field is the same as the one that you add to the hosts file, it indicates that the configuration is valid. You can configure the CNAME on the DNS service provider side.

        ![Test the connectivity of the website](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6331627161/p125301.png)

    -   If the IP address in the **Remote Address** field is different from the one that you add to the hosts file, it indicates that the configuration is invalid. Make sure that you add the IP address of the CNAME to the hosts file.
    After you access the accelerated domain name, you can also test other features by using the on-premises machine.


[Add a CNAME record for a domain name](/intl.en-US/Quick Start/Add a CNAME record for a domain name.md)

