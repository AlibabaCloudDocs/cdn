# HTTPDNS {#concept_nj3_qmx_wdb .concept}

当您发起资源访问请求时，通过HTTP协议访问阿里云CDN指定的HTTPDNS服务端，该服务端依托遍布各地的二级DNS节点解析域名，获得域名解析结果并返回给您。通过本文档，您可以了解HTTPDNS功能简介和接口。

## 功能简介 {#section_o2w_smx_wdb .section}

HTTPDNS使用HTTP协议进行域名解析，代替现有基于UDP的DNS协议，域名解析请求直接发送到阿里云的HTTPDNS服务器，从而绕过运营商的Local DNS，能够避免Local DNS造成的域名劫持问题和调度不精准问题。

传统的DNS解析是通过访问运营商Local DNS获得解析结果，这种方式容易引发域名劫持、域名解析错误、流量跨网等问题， 从而导致网站无法访问或访问缓慢。httpDNS是域名解析服务，通过HTTP协议直接访问阿里云CDN的服务器，由于绕过了运营商的Local DNS，因此可以避免DNS劫持并获得实时精确的DNS解析结果。

如果您想了解更多信息，请参见[HTTPDNS](https://help.aliyun.com/product/30100.html)。

## HTTPDNS接口说明 {#section_w70_fzi_4hr .section}

CDN支持通过HTTP接口直接访问，接口说明如下：

-   URL：`http://umc.danuoyialicdn.com/multi_dns_resolve`。
-   请求方法：`POST`。
-   支持参数：`client_ip=x.x.x.x`。

    如果使用发起HTTPDNS请求的客户端IP地址，则该参数可以忽略。


## HTTPDNS接口示例 {#section_vm2_zmx_wdb .section}

HTTPDNS接口示例如下所示：

-   单个域名
    -   请求示例

        ``` {#codeblock_nre_faq_4kl}
        #curl 'http://umc.danuoyi.alicdn.com/multi_dns_resolve?client_ip=192.168.253.16
        ' -d 'd.tv.taobao.com'
        ```

    -   返回示例

        ``` {#codeblock_rzf_b2e_2km}
        {"dns":[{"host":"d.tv.taobao.com","ips":[{"ip":"192.168.23.240","spdy":0},{"ip":"192.168.23.250","spdy":0}],"ttl":300,"port":80}],"port":80}
        ```

-   多个域名
    -   请求示例

        待解析的多个域名放到POST的`body`中，域名之间以空白分隔，空白可以是空格、TAB和换行符。

        ``` {#codeblock_e0l_ez3_5bh}
        #curl 'http://umc.danuoyi.alicdn.com/multi_dns_resolve?client_ip=192.168.253.16
        ' -d 'd.tv.taobao.com vmtstvcdn.alicdn.com'
        ```

    -   返回示例

        json数据。解析后提取域名对应的IP地址，多个IP地址之间可以做轮询，需要遵循ttl进行缓存和过期。

        ``` {#codeblock_5ha_35l_qgf}
        {"dns":[{"host":"vmtstvcdn.alicdn.com","ips":[{"ip":"192.168.23.250","spdy":0},{"ip":"192.168.23.240","spdy":0}],"ttl":300,"port":80},{"host":"d.tv.taobao.com","ips":[{"ip":"192.168.23.240","spdy":0},{"ip":"192.168.23.250","spdy":0}],"ttl":300,"port":80}],"port":80}
        ```


