# 设置httpDNS {#concept_nj3_qmx_wdb .concept}

## 功能简介 {#section_o2w_smx_wdb .section}

-   传统的DNS解析是通过访问运营商Local DNS获得解析结果，这种方式容易引发域名劫持、域名解析错误、流量跨网等问题， 从而导致网站无法访问或访问缓慢。
-   httpDNS是域名解析服务，通过HTTP协议直接访问阿里云CDN的服务器，由于绕过了运营商的Local DNS，因此可以避免DNS劫持并获得实时精确的DNS解析结果。
-   原理： 客户端发起请求，通过HTTP协议访问阿里云CDN指定httpDNS服务端，该服务端依托遍布各地的二级DNS节点解析域名，获得域名解析结果并最终返回给客户端。

## httpDNS 接口 {#section_vm2_zmx_wdb .section}

支持通过HTTP接口直接访问，访问方式如下：

1.  服务URL：

    ```
    http://umc.danuoyi.alicdn.com/multi_dns_resolve
    ```

2.  请求方法：`POST`
3.  支持参数： `client_ip=x.x.x.x` 如果使用发起httpDNS请求的客户端IP，该参数可以忽略。
4.  请求示例： 待解析的多个域名放到POST的body中，域名之间以空白分隔，空白可以是空格、TAB和换行符。

    ```
    #curl 'http://umc.danuoyi.alicdn.com/multi_dns_resolve?client_ip=182.92.253.16
    ' -d 'd.tv.taobao.com'
    ```

5.  返回格式： json 数据，解析后提取域名对应的ip，多个ip之间可以做轮询，需要遵循ttl进行缓存和过期。

    ```
    {"dns":[{"host":"d.tv.taobao.com","ips":[{"ip":"115.238.23.240","spdy":0},{"ip":"115.238.23.250","spdy":0}],"ttl":300,"port":80}],"port":80}
    ```

6.  多个域名请求事例：
    -   请求示例

        ```
        #curl 'http://umc.danuoyi.alicdn.com/multi_dns_resolve?client_ip=182.92.253.16
        ' -d 'd.tv.taobao.com vmtstvcdn.alicdn.com'
        ```

    -   返回示例

        ```
        {"dns":[{"host":"vmtstvcdn.alicdn.com","ips":[{"ip":"115.238.23.250","spdy":0},{"ip":"115.238.23.240","spdy":0}],"ttl":300,"port":80},{"host":"d.tv.taobao.com","ips":[{"ip":"115.238.23.240","spdy":0},{"ip":"115.238.23.250","spdy":0}],"ttl":300,"port":80}],"port":80}
        ```


