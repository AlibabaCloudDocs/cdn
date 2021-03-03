# API概览

CDN提供以下相关API接口。

## 服务操作接口

|API|描述|
|---|--|
|[OpenCdnService](/cn.zh-CN/旧版API参考/服务操作接口/开通CDN服务.md)|调用OpenCdnService开通CDN服务。只有开通后，才能进行域名操作。|
|[DescribeCdnService](/cn.zh-CN/旧版API参考/服务操作接口/获取CDN服务状态.md)|调用DescribeCdnService查询CDN服务状态。包括当前计费类型、服务开通时间、下次生效的计费类型、当前业务状态等。|
|[ModifyCdnService](/cn.zh-CN/旧版API参考/服务操作接口/修改CDN服务的计费类型.md)|调用ModifyCdnService变更CDN服务的计费类型。|

## 域名操作接口

|API|描述|
|---|--|
|[AddCdnDomain](/cn.zh-CN/旧版API参考/域名操作接口/添加加速域名.md)|调用AddCdnDomain添加加速域名。|
|[DescribeUserDomains](/cn.zh-CN/旧版API参考/域名操作接口/获取用户的加速域名信息.md)|调用DescribeUserDomains查询用户名下所有的域名与状态。|
|[DescribeCdnDomainDetail](/cn.zh-CN/旧版API参考/域名操作接口/获取基本配置信息.md)|调用DescribeCdnDomainDetail获取指定加速域名配置的基本信息。|
|[ModifyCdnDomain](/cn.zh-CN/旧版API参考/域名操作接口/修改加速域名信息.md)|调用ModifyCdnDomain修改加速域名配置信息。|
|[StartCdnDomain](/cn.zh-CN/旧版API参考/域名操作接口/启用状态为停用的加速域名.md)|调用StartCdnDomain启用状态为停用的加速域名，将DomainStatus变更为online。|
|[StopCdnDomain](/cn.zh-CN/旧版API参考/域名操作接口/停用加速域名.md)|调用StopCdnDomain停用指定加速域名。|
|[DeleteCdnDomain](/cn.zh-CN/旧版API参考/域名操作接口/删除已添加的加速域名.md)|调用DeleteCdnDomain删除已添加的加速域名。|
|[DescribeDomainsBySource](/cn.zh-CN/旧版API参考/域名操作接口/获取源站对应的加速域名.md)|调用DescribeDomainsBySource查询用户名下源站对应的所有域名名称列表。|

## 刷新预热类接口

|API|描述|
|---|--|
|[RefreshObjectCaches](/cn.zh-CN/旧版API参考/刷新预热类接口/刷新节点上的文件内容.md)|调用RefreshObjectCaches刷新节点上的文件内容。|
|[PushObjectCache](/cn.zh-CN/旧版API参考/刷新预热类接口/预热源站内容到缓存节点.md)|调用PushObjectCache接口将源站的内容主动预热到L2 Cache节点上。|
|[DescribeRefreshTasks](/cn.zh-CN/旧版API参考/刷新预热类接口/获取刷新预热任务信息.md)|调用DescribeRefreshTasks查询刷新、预热状态是否在全网生效。|
|[DescribeRefreshQuota](/cn.zh-CN/旧版API参考/刷新预热类接口/获取缓存刷新预热数量信息.md)|调用DescribeRefreshQuota查询url刷新、目录刷新、url预热的最大限制数量及剩余量。|

## 配置操作接口

|API|描述|
|---|--|
|[DescribeDomainConfigs](/cn.zh-CN/旧版API参考/配置操作接口/获取加速域名的配置信息.md)|调用DescribeDomainConfigs获取指定加速域名的配置。|
|[SetOptimizeConfig](/cn.zh-CN/旧版API参考/配置操作接口/设置页面优化功能.md)|调用SetOptimizeConfig设置页面优化功能。|
|[SetPageCompressConfig](/cn.zh-CN/旧版API参考/配置操作接口/设置智能压缩功能.md)|调用SetPageCompressConfig设置智能压缩功能。|
|[SetIgnoreQueryStringConfig](/cn.zh-CN/旧版API参考/配置操作接口/设置过滤参数功能.md)|调用SetIgnoreQueryStringConfig设置过滤参数功能。|
|[SetRangeConfig](/cn.zh-CN/旧版API参考/配置操作接口/设置Range回源功能.md)|调用SetRangeConfig设置Range回源功能。|
|[SetVideoSeekConfig](/cn.zh-CN/旧版API参考/配置操作接口/设置拖拽播放功能.md)|调用SetVideoSeekConfig设置拖拽播放功能。|
|[SetSourceHostConfig](/cn.zh-CN/旧版API参考/配置操作接口/设置回源HOST功能.md)|调用SetSourceHostConfig设置回源host功能。|
|[SetForceRedirectConfig](/cn.zh-CN/旧版API参考/配置操作接口/设置强制访问跳转方式.md)|调用SetForceRedirectConfig设置强制访问跳转方式。|
|[SetRefererConfig](/cn.zh-CN/旧版API参考/配置操作接口/设置加速域名的防盗链功能.md)|调用SetRefererConfig设置加速域名的Refer防盗链功能。|
|[SetPathCacheExpiredConfig](/cn.zh-CN/旧版API参考/配置操作接口/设置目录缓存过期功能.md)|调用SetPathCacheExpiredConfig修改目录过期配置。|
|[DeleteCacheExpiredConfig](/cn.zh-CN/旧版API参考/配置操作接口/删除自定义缓存策略.md)|调用DeleteCacheExpiredConfig删除自定义缓存策略。|
|[SetReqAuthConfig](/cn.zh-CN/旧版API参考/配置操作接口/设置访问鉴权功能.md)|调用SetReqAuthConfig设置加速域名的访问鉴权配置。|
|[SetHttpHeaderConfig](/cn.zh-CN/旧版API参考/配置操作接口/设置自定义HTTP头.md)|调用SetHttpHeaderConfig设置自定义http头的缓存配置。|
|[DeleteHttpHeaderConfig](/cn.zh-CN/旧版API参考/配置操作接口/删除自定义HTTP头.md)|调用DeleteHttpHeaderConfig删除加速域名的Refer防盗链配置。|
|[SetDomainServerCertificate](/cn.zh-CN/旧版API参考/配置操作接口/设置加速域名的证书信息.md)|调用SetDomainServerCertificate设置某域名下证书功能是否启用及修改证书信息。|
|[SetIpBlackListConfig](/cn.zh-CN/旧版API参考/配置操作接口/设置加速域名的IP黑名单.md)|调用SetIpBlackListConfig设置加速域名的IP黑名单。|
|[SetHttpsOptionConfig](/cn.zh-CN/旧版API参考/配置操作接口/设置HTTP2.0功能.md)|调用SetHttpsOptionConfig设置域名的HTTP2.0开关。|
|[BatchDeleteCdnDomainConfig](/cn.zh-CN/旧版API参考/配置操作接口/批量删除加速域名配置.md)|调用BatchDeleteCdnDomainConfig删除域名配置。|
|[DeleteSpecificConfig](/cn.zh-CN/旧版API参考/配置操作接口/删除加速域名配置.md)|调用DeleteSpecificConfig删除加速域名的配置。|
|[SetRemoveQueryStringConfig](/cn.zh-CN/旧版API参考/配置操作接口/设置忽略参数功能.md)|调用SetRemoveQueryStringConfig设置忽略参数。|
|[SetCcConfig](/cn.zh-CN/旧版API参考/配置操作接口/设置CC防护功能.md)|调用SetCcConfig接口设置加速域名的CC防护功能、IP黑白名单设置。|
|[SetReqHeaderConfig](/cn.zh-CN/旧版API参考/配置操作接口/设置回源自定义头.md)|调用SetReqHeaderConfig设置回源自定义头。|
|[SetIpAllowListConfig](/cn.zh-CN/旧版API参考/配置操作接口/设置加速域名的IP白名单.md)|调用SetIpAllowListConfig设置加速域名的IP白名单。|
|[DescribeUserConfigs](/cn.zh-CN/旧版API参考/配置操作接口/获取用户对应的配置信息.md)|调用DescribeUserConfigs获取用户相应的配置。|

## 资源监控接口

|API|描述|
|---|--|
|[DescribeDomainBpsData](/cn.zh-CN/旧版API参考/资源监控接口/获取网络带宽监控数据.md)|调用DescribeDomainBpsData获取加速域名的网络带宽监控数据。|
|[DescribeDomainFlowData](/cn.zh-CN/旧版API参考/资源监控接口/获取网络流量监控数据.md)|调用DescribeDomainFlowData获取加速域名的网络流量监控数据。|
|[DescribeDomainSrcBpsData](/cn.zh-CN/旧版API参考/资源监控接口/获取回源带宽监控数据.md)|调用DescribeDomainSrcBpsData接口获取加速域名的回源带宽监控数据。|
|[DescribeDomainSrcFlowData](/cn.zh-CN/旧版API参考/资源监控接口/获取回源流量监控数据.md)|调用DescribeDomainSrcFlowData获取加速域名的回源流量监控数据。|
|[DescribeDomainHitRateData](/cn.zh-CN/旧版API参考/资源监控接口/获取加速域名的字节命中率.md)|调用DescribeDomainHitRateData获取加速域名的字节命中率（命中字节百分比）。|
|[DescribeDomainReqHitRateData](/cn.zh-CN/旧版API参考/资源监控接口/获取加速域名的请求命中率.md)|调用DescribeDomainReqHitRateData获取加速域名的请求命中率（命中请求百分比）。|
|[DescribeDomainHttpCodeData](/cn.zh-CN/旧版API参考/资源监控接口/获取HTTP返回码数据.md)|调用DescribeDomainHttpCodeData获取加速域名5分钟粒度的HTTP返回码总数和占比数据。|
|[DescribeDomainsUsageByDay](/cn.zh-CN/旧版API参考/资源监控接口/获取天粒度的监控统计数据.md)|调用DescribeDomainsUsageByDay获取加速域名天粒度的监控统计数据。|
|[DescribeTopDomainsByFlow](/cn.zh-CN/旧版API参考/资源监控接口/获取按流量排名的加速域名.md)|调用DescribeTopDomainsByFlow获取按流量排名的域名。|
|[DescribeDomainPvData](/cn.zh-CN/旧版API参考/资源监控接口/获取PV页面访问统计.md)|调用DescribeDomainPvData获取加速域名1小时粒度的PV（访问量）页面访问统计。|
|[DescribeDomainUvData](/cn.zh-CN/旧版API参考/资源监控接口/获取UV页面独立访问统计.md)|调用DescribeDomainUvData获取加速域名1小时粒度的UV页面独立访问统计。|
|[DescribeDomainRegionData](/cn.zh-CN/旧版API参考/资源监控接口/获取用户区域分布数据统计.md)|调用DescribeDomainRegionData获取加速域名天粒度的用户区域分布数据统计。|
|[DescribeDomainISPData](/cn.zh-CN/旧版API参考/资源监控接口/获取运营商分布数据统计.md)|调用DescribeDomainISPData获取加速域名天粒度的用户运营商分布数据统计。|
|[DescribeDomainTopUrlVisit](/cn.zh-CN/旧版API参考/资源监控接口/获取热门URL列表.md)|调用DescribeDomainTopUrlVisit获取加速域名某天内的热门URL列表。|
|[DescribeDomainFileSizeProportionData](/cn.zh-CN/旧版API参考/资源监控接口/获取文件大小占比统计.md)|调用DescribeDomainFileSizeProportionData获取加速域名1小时粒度的文件大小占比统计。|
|[DescribeCdnRegionAndIsp](/cn.zh-CN/旧版API参考/资源监控接口/获取地域和运营商列表.md)|调用DescribeCdnRegionAndIsp获取区域和运营商列表。|
|[DescribeDomainBpsDataByTimeStamp](/cn.zh-CN/旧版API参考/资源监控接口/获取在某个时刻的带宽数据.md)|调用DescribeDomainBpsDataByTimeStamp获取加速域名的在某个时刻不同运营商和区域的带宽数据。|
|[DescribeDomainMax95BpsData](/cn.zh-CN/旧版API参考/资源监控接口/获取95带宽峰值监控数据.md)|调用DescribeDomainMax95BpsData获取加速域名95带宽峰值监控数据。|
|[DescribeDomainPathData](/cn.zh-CN/旧版API参考/资源监控接口/获取不同路径的监控数据.md)|调用DescribeDomainPathData获取加速域名路径级别的5分钟维度的监控数据，包括流量和访问次数。该接口仅限白名单用户使用。|
|[DescribeL2VipsByDomain](/cn.zh-CN/旧版API参考/资源监控接口/获取L2节点的回源IP.md)|调用DescribeL2VipsByDomain查询L2节点vip列表。|
|[DescribeRangeDataByLocateAndIspService](/cn.zh-CN/旧版API参考/资源监控接口/获取运营商和地域带宽数据.md)|调用DescribeRangeDataByLocateAndIspService获取加速域名在某个时刻不同区域和运营商上的带宽数据。|
|[DescribeDomainRealTimeBpsData](/cn.zh-CN/旧版API参考/资源监控接口/获取加速域名的带宽数据.md)|调用DescribeDomainRealTimeBpsData获取加速域名1分钟粒度带宽数据。|
|[DescribeDomainRealTimeByteHitRateData](/cn.zh-CN/旧版API参考/资源监控接口/获取字节命中率数据.md)|调用DescribeDomainRealTimeByteHitRateData获取加速域名1分钟粒度字节命中率数据。|
|[DescribeDomainRealTimeQpsData](/cn.zh-CN/旧版API参考/资源监控接口/获取实时每秒访问次数数据.md)|调用DescribeDomainRealTimeQpsData获取加速域名1分钟粒度每秒访问次数（Qps）数据。|
|[DescribeDomainRealTimeReqHitRateData](/cn.zh-CN/旧版API参考/资源监控接口/获取请求命中率数据.md)|调用DescribeDomainRealTimeReqHitRateData获取加速域名1分钟粒度请求命中率数据。|
|[DescribeDomainTopReferVisit](/cn.zh-CN/旧版API参考/资源监控接口/获取热门页面引用次数排名.md)|调用DescribeDomainTopReferVisit获取加速域名某天的热门页面引用次数排名。|
|[DescribeDomainQpsData](/cn.zh-CN/旧版API参考/资源监控接口/获取每秒访问次数数据.md)|调用DescribeDomainQpsData获取加速域名的每秒访问次数（QPS）。|

## 日志接口

|API|描述|
|---|--|
|[DescribeCdnDomainLogs](/cn.zh-CN/旧版API参考/日志接口/获取加速域名的日志信息.md)|调用DescribeCdnDomainLogs获取指定域名的原始访问日志的下载地址。|
|[DescribeCustomLogConfig](/cn.zh-CN/旧版API参考/日志接口/获取自定义日志配置信息.md)|调用DescribeCustomLogConfig查询日志配置信息。|
|[DescribeDomainCustomLogConfig](/cn.zh-CN/旧版API参考/日志接口/获取加速域名日志配置信息.md)|调用DescribeDomainCustomLogConfig获取域名自定义日志格式配置信息。|
|[DescribeUserCustomLogConfig](/cn.zh-CN/旧版API参考/日志接口/获取自定义日志配置ID.md)|调用DescribeUserCustomLogConfig获取用户下所有自定义日志配置信息。|
|[ListDomainsByLogConfigId](/cn.zh-CN/旧版API参考/日志接口/获取日志配置ID的加速域名.md)|调用ListDomainsByLogConfigId查询应用某自定义日志格式的所有域名列表。|

## 辅助工具接口

|API|描述|
|---|--|
|[DescribeIpInfo](/cn.zh-CN/旧版API参考/辅助工具接口/验证IP是否为CDN节点.md)|调用DescribeIpInfo验证指定的IP是否为阿里云CDN节点的IP地址。|

