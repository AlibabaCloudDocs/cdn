---
keyword: [CDN back-to-origin, static origin protocol policy, dynamic origin protocol policy]
---

# Configure the origin protocol policy

When a client requests resources that are not cached on Alibaba Cloud Content Delivery Network \(CDN\) nodes, CDN nodes follow the origin protocol policy to redirect the request to the origin server. This topic describes how to configure the origin protocol policy.

If you set the origin protocol policy to Follow, Alibaba Cloud CDN communicates with the origin server over the protocol that is used by the client.

-   If the client sends a request over HTTPS and the requested resources are not cached on CDN nodes, CDN nodes redirect the request to port 443 on the origin server over HTTPS.
-   If the client sends a request over HTTP and the requested resources are not cached on CDN nodes, CDN nodes redirect the request to port 80 on the origin server over HTTP.

**Note:** If you set the origin protocol policy to **Follow**, client requests are redirected to the origin server over HTTP or HTTPS. Make sure that both port 443 and port 80 are open on the origin server. Otherwise, CDN nodes fail to redirect client requests to the origin server.

When the origin protocol policy is enabled, requests are redirected to port 80 or port 443 on the origin server. CDN nodes redirect requests to one of the ports on the origin server based on the origin protocol policy. If the origin server uses a custom port, it becomes invalid. If you want to enable the origin protocol policy for an origin server that uses a custom port, submit a ticket to request Alibaba Cloud to configure relevant settings.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Back-to-origin**.

5.  In the **Origin Protocol Policy** section, turn on **Origin Protocol Policy**.

6.  Click **Modify**.

7.  In the **Static Origin Protocol Policy** dialog box, set Redirect Type to **Follow**, **HTTP**, or **HTTPS** based on your business requirements.

    |Parameter|Description|
    |---------|-----------|
    |**Follow**|Follow: When a client sends an HTTP or an HTTPS request, CDN nodes redirect the request to the origin server over the protocol used by the client.|
    |**HTTP**|CDN nodes communicate with origin servers only over HTTP.|
    |**HTTPS**|CDN nodes communicate with origin servers only over HTTPS.|

    ![Static origin protocol policy](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9368355261/p64121.png)

8.  Click **OK**.


**Related topics**  


[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md)

