---
keyword: CDN缓存命中率
---

# 提高CDN缓存命中率

CDN缓存命中率低会导致源站压力大，静态资源访问效率低。您可以针对导致CDN缓存命中率低的具体原因，选择对应的优化策略来提高CDN的缓存命中率。

CDN通过将静态资源缓存在距离客户端最近的CDN节点上，当客户端访问该资源时，如果CDN节点上已经缓存了该资源，则用户请求会命中CDN节点上的缓存，并直接从缓存中获取资源，可避免通过较长的链路回源，提高资源的响应速度和降低源站的带宽压力。如果CDN缓存命中率低，会影响用户体验和增加源站的带宽压力。

CDN缓存命中率包括字节缓存命中率和请求缓存命中率。具体如下：

-   字节缓存命中率=CDN缓存命中响应的字节数÷CDN所有请求响应的字节数

    **说明：** 字节缓存命中率越低，回源流量越大，源站的流出流量越大，源站的带宽资源以及其他的负载越大，因此回源流量代表了源站服务器接收到的负载压力，在业务使用中主要关心字节缓存命中率。

-   请求缓存命中率=CDN缓存命中的请求数÷CDN所有的请求数

## 查看CDN缓存命中率

查看CDN缓存命中率的方式如下：

-   通过控制台查看

    CDN控制台提供的缓存命中率监控包含请求命中率和字节命中率，详细信息如下：

    -   通过资源监控功能查询

        可查询数据的时间范围较大，适合查看较长周期（例如30天）内的命中率情况。时间粒度为5分钟的情况下，数据延迟15分钟左右。详细信息，请参见[资源监控](/intl.zh-CN/服务管理/监控查询/资源监控.md)。

        ![命中率](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9731442261/p278844.png)

    -   通过实时监控功能查询

        可查询数据的时间范围较小，适合查看较短周期（例如1小时）内的实时命中率情况。时间粒度为1分钟的情况下，数据延迟3分钟左右。详细信息，请参见[实时监控](/intl.zh-CN/服务管理/监控查询/实时监控.md)。

        ![质量监控](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7671022261/p63526.png)

-   调用API查看
    -   资源监控功能对应的API

        |API|描述|
        |---|--|
        |[DescribeDomainHitRateData](/intl.zh-CN/新版API参考/数据监控类接口/获取加速域名的字节命中率.md)|调用DescribeDomainHitRateData获取加速域名的字节命中率数据，支持获取最近90天的数据。|
        |[DescribeDomainReqHitRateData](/intl.zh-CN/新版API参考/数据监控类接口/获取加速域名的请求命中率.md)|调用DescribeDomainReqHitRateData获取加速域名的请求命中率数据，支持获取最近90天的数据。|

    -   实时监控功能对应的API

        |API|描述|
        |---|--|
        |[DescribeDomainRealTimeByteHitRateData](/intl.zh-CN/新版API参考/数据监控类接口/获取字节命中率数据.md)|调用DescribeDomainRealTimeByteHitRateData获取加速域名1分钟粒度的字节命中率数据，支持查询7天内的数据。|
        |[DescribeDomainRealTimeReqHitRateData](/intl.zh-CN/新版API参考/数据监控类接口/获取请求命中率数据.md)|调用DescribeDomainRealTimeReqHitRateData获取加速域名1分钟粒度的请求命中率数据，支持查询7天内的数据。|


## 查看缓存命中状态日志

在CDN的请求日志中，记录了所有CDN请求的缓存命中状态，详细的日志格式，请参见[日志下载](/intl.zh-CN/服务管理/日志管理/日志下载.md)。其中cache命中状态字段HIT表示命中，MISS表示未命中，日志示例如下。

```
26/Jun/2019:10:38:19 +0800] 192.168.53.146 - 1542 "-" "GET http://www.aliyun.com/index.html" 200 191 2830 MISS "Mozilla/5.0 (compatible; AhrefsBot/5.0; +http://ahrefs.com/robot/)" "text/html"
```

**说明：** 命中状态仅表示CDN L1节点的命中状态。例如，CDN L1节点未命中缓存，L2节点命中缓存，日志中仍然显示MISS。

您也可以调用[DescribeCdnDomainLogs](/intl.zh-CN/新版API参考/日志信息类接口/获取加速域名的日志信息.md)接口，获取加速域名的日志信息。

## 影响CDN缓存命中率的因素及优化策略

CDN缓存命中率的影响因素和优化策略如下表所示。

|影响因素|优化策略|
|----|----|
|运营大型活动或新版本安装包发布前，没有提前将资源预热到CDN节点，大量资源需要从源站获取，导致CDN缓存命中率低。

通过预热功能，源站主动将对应的资源缓存到CDN节点，当您首次请求资源时，即可直接从CDN节点获取到最新的资源，无需再回源站获取，有效提高缓存命中率。

|[预热资源](/intl.zh-CN/服务管理/刷新和预热资源.md)|
|以下两种情况都会导致用户请求需要回源站获取最新资源并缓存到CDN节点，从而降低CDN的缓存命中率，增大源站的带宽压力。-   CDN上没有配置对源站文件的缓存策略，所有用户请求都将直接透传回源站。
-   CDN上配置了缓存策略，但是缓存时间过短，CDN上的缓存资源过期后会自动从CDN节点删除，导致用户请求仍然需要频繁回源站获取资源。

|[配置缓存过期时间](/intl.zh-CN/域名管理/缓存配置/配置缓存过期时间.md)|
|当URL请求中带有queryString或其他可变参数时，访问同一个资源的不同URL请求（URL携带的参数不同）会重新回源，导致CDN缓存命中率降低。|-   [开启过滤参数及配置保留参数](/intl.zh-CN/域名管理/性能优化/开启过滤参数及配置保留参数.md)
-   [开启过滤参数及配置删除参数](/intl.zh-CN/域名管理/性能优化/开启过滤参数及配置删除参数.md) |
|当您只需要访问资源文件指定范围内的部分内容时，因未开启Range回源，CDN上层节点会向源站请求全部文件，由于客户端收到Range定义的字节后自动断开HTTP连接，请求的文件没有缓存到CDN节点上，最终导致缓存命中率较低，且回源流量较大。|[配置Range回源](/intl.zh-CN/域名管理/视频相关/配置Range回源.md)|

