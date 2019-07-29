# Modify origin information {#task_270231 .task}

This topic describes how to modify the origin information of a domain on the Alibaba Cloud CDN console.

You cannot modify the origin information of a domain whose business type is undefined[undefined](../../../../intl.en-US/.md#)undefined.

Alibaba Cloud CDN supports three types of origin domains: **OSS Domain**, **IP**, and **Origin Domain**. **IP** allows for multiple IP addresses and **Origin Domain** allows for multiple domains. If you set **Type** to **IP** or **Origin Domain**, you can also set priorities for multiple origins.

**Note:** The system automatically performs a four-tier health check to test Port 80 for each origin once per 2.5 seconds. If an origin fails the check for three consecutive times, the system considers it unavailable.

CDN must allow for switchovers between primary and secondary origins.undefined

-   When you configure multiple origins and these origins have different priorities, CDN preferably directs requests to the primary origin. If the primary origin fails the health check for three consecutive times, CDN considers the primary origin faulty and then directs requests to the secondary origin. Once the faulty origin passes the health check, CDN considers it available again and restores the priority of this origin to **Primary**.
-   When you configure multiple origins but these origins have the same priority, CDN polls each origin and directs requests to them.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com/overview).
2.  In the left-side navigation pane, click **Domain Names**.
3.  On the Domain Names page, find the domain name you want to set, and in the **Actions** column click **Manage**.
4.  In the left-side navigation pane, click **Basics**.
5.  In the **Origin Information** section, click **Modify**.
6.  In the Modify Origin Information dialog box, set the origin type, IP address, and port number. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/223013/156440874947757_en-US.png)

    The following table describes the **Type** parameter.

    |Value|Description|
    |:----|:----------|
    |OSS Domain|Allows you to define an OSS origin domain, whose name must end with **aliyuncs.com** or **aliyun-inc.com**, for example, **xxx.oss-cn-hangzhou.aliyuncs.com**. The OSS origin helps you to lower the costs of back-to-origin traffic.|
    |IP|Allows you to configure multiple origin IP addresses and set their priorities.|
    |Origin Domain|Allows you to configure multiple origin domains and set their priorities.|

    The following table describes the **Port** parameter.

    |Value|Description|
    |:----|:----------|
    |Port 80|Your origin server returned the requested resources to Port 80 by using HTTP or HTTPS.|
    |Port 443|Your origin server returned the requested resources to Port 443 by using HTTP or HTTPS. If your origin server provides multiple domains for a single IP address, you need to configure Origin SNI. For more information, see [Back-to-origin SNI](intl.en-US/Domain Management/Content back-to-source settings/Back-to-origin SNI.md#).|
    |Custom Port|Your origin server returned the requested resources to a custom port only by using HTTP. Before you customize a port, you must set **Origin Protocol Policy** to **HTTP**. For more information, see [Configure an origin protocol](intl.en-US/Domain Management/Content back-to-source settings/Configure an origin protocol.md#).     -   If you set **Origin Protocol Policy** to **Follow**, you cannot customize a port.
    -   If you set **Origin Protocol Policy** to **Follow** through OpenAPI, make sure that your origin protocol and custom port work properly.
    -   If you enable the **HTTP** or **HTTPS** origin protocol and customize a port through the **Port** parameter, your origin server returns the requested resources according to the port settings regardless of the other relevant settings you specify on the Alibaba Cloud CDN console.
 |

7.  Click **OK**.

