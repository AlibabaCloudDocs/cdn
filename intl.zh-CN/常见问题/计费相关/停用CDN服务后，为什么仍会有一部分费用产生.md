# 停用CDN服务后，为什么仍会有一部分费用产生 {#concept_o5p_xts_xdb .concept}

造成这种情况主要有以下两个原因：

-   由于一些用户的LocalDNS服务器有缓存，在停用CDN服务后，若客户LocalDNS服务器中缓存未过期，LocalDNS还会把访问已停用CDN域名的请求解析到CDN节点，造成少量CDN流量计费。
-   一些下载类软件也存在LocalDNS缓存，在这部分缓存过期前，下载类软件也会把访问已停用CDN域名的请求解析到CDN节点上，造成少量CDN流量计费。

