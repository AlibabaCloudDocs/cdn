# HTTPDNS {#concept_nj3_qmx_wdb .concept}

The HTTPDNS server of Alibaba Cloud CDN hosts DNS records that point to L2 CDN nodes in the world. When you want to access a resource in the CDN network, the client sends a DNS resolution request to the HTTPDNS server. After the HTTPDNS server receives the resolution request, it resolves the requested domain name and then returns IP addresses of the corresponding L2 nodes to the client. This topic describes HTTPDNS features and service endpoint.

## Features {#section_o2w_smx_wdb .section}

HTTPDNS is a DNS service that uses HTTP to access Alibaba Cloud CDN servers. It is designed to replace the current UDP-based DNS resolution service. DNS resolution requests are sent to the Alibaba Cloud HTTPDNS server, bypassing the local DNS server of the DNS service provider. This can prevent domain hijacking attacks and improve the accuracy of domain resolution.

The traditional DNS service uses the local DNS server of the DNS provider to resolve domain names. During this process, the domain may be hijacked, domain name resolution errors may occur, or the resolution request may be forwarded across networks. As a result, it may be time-consuming to connect to the requested website or you may fail to access the website. HTTPDNS is a new DNS service. It allows you to bypass the DNS provider's local DNS server and directly access Alibaba Cloud CDN servers. With HTTPDNS, you are able to get precise DNS resolution results in real time, without the need to worry about domain hijacking.

## HTTPDNS service endpoint {#section_w70_fzi_4hr .section}

You can send requests to the endpoint of the HTTPDNS service over HTTP to call the service.

-   Endpoint: `http://umc.danuoyialicdn.com/multi_dns_resolve`.
-   Method: `POST`.
-   Parameter: `client_ip=x.x.x.x`.

    If you use the same client to send HTTPDNS requests and receive responses, then you can ignore this parameter.


## Examples {#section_vm2_zmx_wdb .section}

The following examples show how to send HTTPDNS requests to call the DNS resolution service.

-   Single domain name
    -   Sample request

        ``` {#codeblock_nre_faq_4kl}
        #curl 'http://umc.danuoyi.alicdn.com/multi_dns_resolve?client_ip=192.168.253.16
        ' -d 'd.tv.taobao.com'
        ```

    -   Sample response

        ``` {#codeblock_rzf_b2e_2km}
        {"dns":[{"host":"d.tv.taobao.com","ips":[{"ip":"192.168.23.240","spdy":0},{"ip":"192.168.23.250","spdy":0}],"ttl":300,"port":80}],"port":80}
        ```

-   Multiple domain names
    -   Sample request

        Specify the domain names that you want to resolve in the `body` of the POST request. Separate the domain names with spaces, tab stops, or line breaks.

        ``` {#codeblock_e0l_ez3_5bh}
        #curl 'http://umc.danuoyi.alicdn.com/multi_dns_resolve?client_ip=192.168.253.16
        ' -d 'd.tv.taobao.com vmtstvcdn.alicdn.com'
        ```

    -   Sample response

        The returned data is in JSON format. Create records on the client to cache the returned IP addresses, assign a time to live \(TTL\) value to each record, and then use round-robin to address client queries to the returned IP addresses.

        ``` {#codeblock_5ha_35l_qgf}
        {"dns":[{"host":"vmtstvcdn.alicdn.com","ips":[{"ip":"192.168.23.250","spdy":0},{"ip":"192.168.23.240","spdy":0}],"ttl":300,"port":80},{"host":"d.tv.taobao.com","ips":[{"ip":"192.168.23.240","spdy":0},{"ip":"192.168.23.250","spdy":0}],"ttl":300,"port":80}],"port":80}
        ```


