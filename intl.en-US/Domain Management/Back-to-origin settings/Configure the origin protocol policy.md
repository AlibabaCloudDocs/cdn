---
keyword: [CDN back-to-origin request, static origin protocol policy, dynamic origin protocol policy]
---

# Configure the origin protocol policy

If a client requests resources that are not cached on a Content Delivery Network \(CDN\) node, the node retrieves these resources from the origin server based on the origin protocol policy and caches these resources on the node. This topic describes how to configure the origin protocol policy.

If you set the origin protocol policy to Follow, Alibaba Cloud CDN communicates with the origin server over the protocol used by the client. If the client sends an HTTPS request to retrieve resources that are not cached on a CDN node, the node retrieves the requested resources from the origin server also over HTTPS. If the client sends an HTTP request, the CDN node retrieves the requested resources from the origin server over HTTP.

**Note:** The origin server must support both port 80 and port 443. Otherwise, the back-to-origin process may fail.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the Domain Names page, find the target domain name and click **Manage**.

4.  In the left-side navigation pane of the specified domain, click **Back-to-origin**.

5.  In the **Origin Protocol Policy** section, turn on the **Origin Protocol Policy** switch.

6.  Click **Modify**.

7.  In the **Static Origin Protocol Policy** dialog box, set Redirect Type to **Follow**, **HTTP**, or **HTTPS** based on your business requirements.

    |Parameter|Description|
    |---------|-----------|
    |**Follow**|Follow: When a client sends an HTTP or HTTPS request, CDN nodes communicate with the origin server over the protocol used by the client.|
    |**HTTP**|CDN nodes communicate with origin servers only over HTTP.|
    |**HTTPS**|CDN nodes communicate with origin servers only over HTTPS.|

    ![StaticOriginProtocolPolicy](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6415034061/p178536.png)

8.  Click **OK**.


