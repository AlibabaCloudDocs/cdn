# Terms {#concept_plh_jlc_5db .concept}

This topic explains the commonly used terms in Alibaba Cloud CDN products.

## Accelerating domain {#section_obn_stb_p2b .section}

An accelerating domain is a domain that uses CDN to accelerate content distribution. A domain is the server IP address of a website, email, or FTP server.

**说明：** In this document, an accelerating domain is a referred to domain in most cases.

## Origin {#section_dym_wtb_p2b .section}

An origin is the server that provides services. Specifically, an origin specifies the IP address to which CDN redirects back-to-origin requests. You can set your origin type to **OSS Domain**, **IP**, or **Origin Domain** on the Alibaba Cloud CDN console.

## CNAME record {#section_cm2_nlc_5db .section}

A Canonical Name \(CNAME\) is an alias, which is used to point a domain to another domain that provides an IP address.

For example, a large amount of information is stored on your server, and you can access the information through `docs.example.com`. If you also want to be able to access the information through `documents.example.com`, you can add a CNAME record at your DNS provider side, pointing `documents.example.com` to `docs.example.com`. Then, all requests destined for `documents.example.com` are redirected to `docs.example.com`, from which you can obtain the requested information.

## CNAME {#section_dm2_nlc_5db .section}

After you connect to Alibaba Cloud CDN and add your domain name on the Alibaba Cloud CDN console, Alibaba Cloud CDN assigns a CNAME in `*.*kunlun*.com` format to your domain. You can add a CNAME record at your DNS provider side, pointing your domain to the domain `*.*kunlun*.com`. When the CNAME record takes effect, all requests destined for your domain are redirected to your CDN node to accelerate content distribution.

## DNS {#section_em2_nlc_5db .section}

Domain Name System \(DNS\) is used to translate domain names into IP addresses that can be recognized by the Internet. A dedicated DNS server must be used to automatically translate domain names into IP addresses. For example, if you enter the domain name `www.baidu.com`, the DNS server automatically translates it into the IP address `220.181.112.143`.

## SSL/TLS {#section_ghx_z5v_m2b .section}

Secure Sockets Layer \(SSL\) is a TCP-based secure communications protocol. It helps to protect the integrity and security of data when the data is being transmitted over the Internet. After SSL is standardized, its name is changed to TLS. Therefore, SSL and TLS are collectively known as SSL/TLS.

## Edge node {#section_fm2_nlc_5db .section}

In this document, the terms edge node, CDN node, cache node, accelerating node, and Alibaba Cloud node all refer to Alibaba Cloud edge node, sometimes shortened to node. The edge node concept is proposed to simplify the complex network structure. Edge nodes are located near end users on the network, therefore they can respond and connect to the network faster than origins. CDN caches the content that is frequently accessed by end users to edge nodes, increasing user access speeds and network quality.

## Origin host {#section_gm2_nlc_5db .section}

An origin host specifies the host to which CDN redirects back-to-origin requests.

Example 1:

If your origin is the domain `www.a.com` and your origin host is `www.b.com`, then CDN redirects back-to-origin requests to the IP address that is translated from `www.a.com` and this IP address belongs to the `www.b.com` host.

Example 2:

If your origin is the IP address `1.1.1.1` and your origin host is `www.b.com`, then CDN redirects back-to-origin requests to the `www.b.com` host corresponding to the IP address `1.1.1.1`.

## Origin protocol {#section_hm2_nlc_5db .section}

An origin protocol is the protocol that CDN uses to redirect back-to-origin requests. If you set **Redirect Type** to **Follow** on the Alibaba Cloud CDN console, CDN redirects back-to-origin requests by using the same protocol as used by your client to request resources. In such case, if your client requests resources by using HTTPS \(or HTTP\), your CDN node redirects the requests to your origin also by using HTTPS \(or HTTP\) in case that the requested resources are not cached on the node.

## Filter Parameter {#section_im2_nlc_5db .section}

Filter Parameter is a function, which enables you to filter out the parameters that follow a question mark \(?\) in the URL of each request based on your business needs.

-   When you enable this function, your CDN node filters out the parameters that follow a question mark \(?\) from each URL. In addition, if multiple URLs are the same after the parameters are filtered out, your CDN node caches only one replica for these URLs.
-   When you disable this function, your CDN node caches a replica of each URL.

If the URLs of the resources that you request contain different parameters that indicate the same content, we recommend that you enable this function to increase the cache hit ratio.

