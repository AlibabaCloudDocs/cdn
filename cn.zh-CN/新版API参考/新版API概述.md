# 新版API概述 {#reference_ckk_xml_vdb .reference}

本文为您介绍了CDN可以调用的所有API，具体API信息请参见相关文档。

## 数据监控接口 {#section_tsp_qnl_vdb .section}

|API|描述|
|:--|:-|
|[DescribeDomainSrcHttpCodeData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainSrcHttpCodeData.md#)|获取加速域名最小5分钟粒度的回源HTTP返回码占比数据。|
|[DescribeDomainTopReferVisit](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainTopReferVisit.md#)|获取加速域名某天的热门页面引用次数排名。|
|[DescribeDomainTopUrlVisit](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainTopUrlVisit.md#)|获取加速域名某天内的热门URL列表。|
|[DescribeDomainAverageResponseTime](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainAverageResponseTime.md#)|获取加速域名的平均响应时间。|
|[DescribeDomainFileSizeProportionData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainFileSizeProportionData.md#)|获取加速域名最小1小时粒度的文件大小占比统计。|
|[DescribeDomainBpsDataByTimeStamp](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainBpsDataByTimeStamp.md#)|获取加速域名的在某个时刻不同Locate和Isp上的带宽数据，单位：bit/second。|
|[DescribeDomainISPData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainISPData.md#)|获取加速域名天粒度的 用户运营商分布数据统计。|
|[DescribeCdnRegionAndIsp](cn.zh-CN/新版API参考/数据监控接口/DescribeCdnRegionAndIsp.md#)|获取区域和运营商列表。|
|[DescribeRangeDataByLocateAndIspService](cn.zh-CN/新版API参考/数据监控接口/DescribeRangeDataByLocateAndIspService.md#)|获取加速域名的在某个时刻不同Locate和Isp上的带宽数据，单位：bit/second。|
|[DescribeDomainRealTimeBpsData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainRealTimeBpsData.md#)|获取域名1分钟粒度带宽数据。|
|[DescribeDomainRealTimeSrcBpsData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainRealTimeSrcBpsData.md#)|获取域名1分钟粒度回源带宽数据。|
|[DescribeDomainRealTimeSrcHttpCodeData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainRealTimeSrcHttpCodeData.md#)|获取加速域名回源 1 分钟粒度的HTTP返回码占比数据。|
|[DescribeDomainRealTimeSrcTrafficData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainRealTimeSrcTrafficData.md#)|获取加速域名的 1 分钟回源流量监控数据，单位：bit。|
|[DescribeDomainRealTimeByteHitRateData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainRealTimeByteHitRateData.md#)|获取域名1分钟粒度字节命中率数据。|
|[DescribeDomainRealTimeQpsData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainRealTimeQpsData.md#)|获取域名1分钟粒度每秒访问次数数据。|
|[DescribeDomainRealTimeHttpCodeData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainRealTimeHttpCodeData.md#)|获取加速域名 1 分钟粒度的HTTP返回码占比数据。|
|[DescribeDomainRealTimeTrafficData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainRealTimeTrafficData.md#)|获取加速域名的 1 分钟流量监控数据，单位：Byte。|
|[DescribeDomainRealTimeReqHitRateData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainRealTimeReqHitRateData.md#)|获取域名1分钟粒度请求命中率数据。|
|[DescribeDomainBpsData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainBpsData.md#)|获取加速域名的网络带宽监控数据，单位：bit/second。|
|[DescribeDomainSrcBpsData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainSrcBpsData.md#)|获取加速域名的回源带宽监控数据，单位：bit/second。|
|[DescribeDomainSrcTrafficData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainSrcTrafficData.md#)|获取加速域名的回源流量监控数据，单位：bit。|
|[DescribeDomainQpsData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainQpsData.md#)|获取加速域名的每秒访问次数QPS。|
|[DescribeDomainsUsageByDay](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainsUsageByDay.md#)|获取加速域名天粒度监控统计数据。|
|[DescribeDomainHitRateData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainHitRateData.md#)|获取加速域名的字节命中率（命中字节百分比）。|
|[DescribeL2VipsByDomain](cn.zh-CN/新版API参考/数据监控接口/DescribeL2VipsByDomain.md#)|按域名查询L2节点的回源IP。|
|[DescribeDomainReqHitRateData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainReqHitRateData.md#)|获取加速域名的请求命中率（命中请求百分比）。|
|[DescribeDomainHttpCodeData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainHttpCodeData.md#)|获取加速域名最小5分钟粒度的HTTP返回码占比数据。|
|[DescribeDomainTrafficData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainTrafficData.md#)|获取加速域名的网络流量监控数据，单位：byte。|
|[DescribeTopDomainsByFlow](cn.zh-CN/新版API参考/数据监控接口/DescribeTopDomainsByFlow.md#)|获取用户按流量排名的域名。|
|[DescribeDomainRegionData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainRegionData.md#)|获取加速域名天粒度的 用户区域分布数据统计。|
|[DescribeDomainUvData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainUvData.md#)|获取加速域名最小1小时粒度的 UV页面独立访问统计。|
|[DescribeDomainPvData](cn.zh-CN/新版API参考/数据监控接口/DescribeDomainPvData.md#)|获取加速域名最小1小时粒度的 PV页面访问统计。|

## 域名管理接口 {#section_tzc_vnl_vdb .section}

|API|描述|
|:--|:-|
|[AddCdnDomain](cn.zh-CN/新版API参考/域名管理接口/AddCdnDomain.md#)|添加加速域名。|
|[DeleteCdnDomain](cn.zh-CN/新版API参考/域名管理接口/DeleteCdnDomain.md#)|删除已添加的加速域名。|
|[StopCdnDomain](cn.zh-CN/新版API参考/域名管理接口/StopCdnDomain.md#)|停用某个加速域名。|
|[StartCdnDomain](cn.zh-CN/新版API参考/域名管理接口/StartCdnDomain.md#)|启用状态为停用的加速域名。|
|[BatchStartCdnDomain](cn.zh-CN/新版API参考/域名管理接口/BatchStartCdnDomain.md#)|启用状态为停用的加速域名。|
|[BatchSetCdnDomainConfig](cn.zh-CN/新版API参考/域名管理接口/BatchSetCdnDomainConfig.md#)|域名批量配置。|
|[ModifyCdnDomain](cn.zh-CN/新版API参考/域名管理接口/ModifyCdnDomain.md#)|修改加速域名。|
|[DescribeUserDomains](cn.zh-CN/新版API参考/域名管理接口/DescribeUserDomains.md#)|查询用户名下所有的域名与状态。|
|[DescribeCdnCertificateList](cn.zh-CN/新版API参考/域名管理接口/DescribeCdnCertificateList.md#)|获取证书列表信息。|
|[DescribeDomainCertificateInfo](cn.zh-CN/新版API参考/域名管理接口/DescribeDomainCertificateInfo.md#)|获取指定加速域名证书信息。|
|[DescribeCdnDomainDetail](cn.zh-CN/新版API参考/域名管理接口/DescribeCdnDomainDetail.md#)|获取指定加速域名配置的基本信息。|
|[DescribeDomainsBySource](cn.zh-CN/新版API参考/域名管理接口/DescribeDomainsBySource.md#)|查询用户名下，源站对应的所有域名名称列表。|
|[SetDomainServerCertificate](cn.zh-CN/新版API参考/域名管理接口/SetDomainServerCertificate.md#)|该接口用于设置某域名下证书功能是否启用及修改证书信息。|
|[BatchStopCdnDomain](cn.zh-CN/新版API参考/域名管理接口/BatchStopCdnDomain.md#)|批量停用加速域名。|
|[DeleteSpecificConfig](cn.zh-CN/新版API参考/域名管理接口/DescribeCdnDomainConfigs.md#)|删除加速域名的配置。|
|[DescribeCdnDomainConfigs](cn.zh-CN/新版API参考/域名管理接口/DeleteSpecificConfig.md#)|查询域名配置。|
|[DescribeUserVipsByDomain](cn.zh-CN/新版API参考/域名管理接口/DescribeUserVipsByDomain.md#)|按域名查询vip列表。|

## 日志类接口 {#section_c3h_xnl_vdb .section}

|API|描述|
|:--|:-|
|[DescribeCdnDomainLogs](cn.zh-CN/新版API参考/日志类接口/DescribeCdnDomainLogs.md#)|查询域名实时日志投递信息。|
|[CreateRealtimeLogDelivery](cn.zh-CN/新版API参考/日志类接口/CreateRealtimeLogDelivery.md#)|创建域名实时日志投递。|
|[DeleteRealtimeLogDelivery](cn.zh-CN/新版API参考/日志类接口/DeleteRealtimeLogDelivery.md#)|删除实时日志推送域名。|
|[DescribeDomainRealtimeLogDelivery](cn.zh-CN/新版API参考/日志类接口/DescribeDomainRealtimeLogDelivery.md#)|获取用户所有自定义日志配置信息。|
|[DescribeRealtimeDeliveryAcc](cn.zh-CN/新版API参考/日志类接口/DescribeRealtimeDeliveryAcc.md#)|实时日志投递次数查询。|
|[DisableRealtimeLogDelivery](cn.zh-CN/新版API参考/日志类接口/DisableRealtimeLogDelivery.md#)|暂停域名实时日志投递。|
|[EnableRealtimeLogDelivery](cn.zh-CN/新版API参考/日志类接口/EnableRealtimeLogDelivery.md#)|开启域名实时日志投递。|
|[ListRealtimeLogDeliveryDomains](cn.zh-CN/新版API参考/日志类接口/ListRealtimeLogDeliveryDomains.md#)|查询实时日志投递服务下所有域名。|
|[ModifyRealtimeLogDelivery](cn.zh-CN/新版API参考/日志类接口/ModifyRealtimeLogDelivery.md#)|更改域名实时日志投递\(一个域名同时仅支持投递单个logstore\)。|
|[ListRealtimeLogDeliveryInfos](cn.zh-CN/新版API参考/日志类接口/ListRealtimeLogDeliveryInfos.md#)|查询所有实时日志投递服务信息。|
|[DescribeCustomLogConfig](cn.zh-CN/新版API参考/日志类接口/DescribeCustomLogConfig.md#)|根据configId查询自定义日志配置详细信。|
|[DescribeDomainCustomLogConfig](cn.zh-CN/新版API参考/日志类接口/DescribeDomainCustomLogConfig.md#)|获取域名自定义日志格式配置信息。|
|[ListDomainsByLogConfigId](cn.zh-CN/新版API参考/日志类接口/ListDomainsByLogConfigId.md#)|查询应用某自定义日志格式的所有域名列表。|
|[ListUserCustomLogConfig](cn.zh-CN/新版API参考/日志类接口/ListUserCustomLogConfig.md#)|获取用户下所有自定义日志配置信息。|
|[ModifyDomainCustomLogConfig](cn.zh-CN/新版API参考/日志类接口/ModifyDomainCustomLogConfig.md#)|修改域名所属日志自定义日志配置信息。|
|[ModifyUserCustomLogConfig](cn.zh-CN/新版API参考/日志类接口/ModifyUserCustomLogConfig.md#)|修改用户下自定义日志配置信息。|

## 刷新预热接口 {#section_lqd_5nl_vdb .section}

|API|描述|
|:--|:-|
|[PushObjectCache](cn.zh-CN/新版API参考/刷新预热接口/PushObjectCache.md#)|将源站的内容主动预热到L2 Cache节点上。|
|[DescribeRefreshQuota](cn.zh-CN/新版API参考/刷新预热接口/DescribeRefreshQuota.md#)|查询刷新、预热URL及目录的最大限制数量，以及当日剩余刷新、预热URL及目录的次数。|
|[DescribeRefreshTasks](cn.zh-CN/新版API参考/刷新预热接口/DescribeRefreshTasks.md#)|查询刷新、预热状态是否在全网生效。|
|[RefreshObjectCaches](cn.zh-CN/新版API参考/刷新预热接口/RefreshObjectCaches.md#)|刷新节点上的文件内容。|

## 服务类接口 {#section_iv2_tnl_vdb .section}

|API|描述|
|:--|:-|
|[OpenCdnService](cn.zh-CN/新版API参考/服务类接口/OpenCdnService.md#)|开通CDN服务。|
|[ModifyCdnService](cn.zh-CN/新版API参考/服务类接口/ModifyCdnService.md#)|变更CDN服务的计费类型。|
|[DescribeCdnService](cn.zh-CN/新版API参考/服务类接口/DescribeCdnService.md#)|查询CDN服务状态。|
|[DescribeCdnUserResourcePackage](cn.zh-CN/新版API参考/服务类接口/DescribeCdnUserResourcePackage.md#)|查询CDN用户当前流量包。|
|[DescribeCdnUserQuota](cn.zh-CN/新版API参考/服务类接口/DescribeCdnUserQuota.md#)|查询用户资源上限及已使用情况。|

## 用量查询接口 {#section_ttd_ynl_vdb .section}

|API|描述|
|:--|:-|
|[DescribeUserUsageDataExportTask](cn.zh-CN/新版API参考/用量查询接口/DescribeUserUsageDataExportTask.md#)|列出用户最近三个月的用量导出任务信息。|
|[CreateUserUsageDataExportTask](cn.zh-CN/新版API参考/用量查询接口/CreateUserUsageDataExportTask.md#)|创建账号历史用量数据导出任务，将历史用量生成PDF文件用于下载。|
|[CreateUsageDetailDataExportTask](cn.zh-CN/新版API参考/用量查询接口/CreateUsageDetailDataExportTask.md#)|创建用量详细数据导出任务，将详细用量生成excel文件用于下载。|
|[DescribeUserUsageDetailDataExportTask](cn.zh-CN/新版API参考/用量查询接口/DescribeUserUsageDetailDataExportTask.md#)|列出用户最近三个月的详细用量导出任务信息。|
|[DescribeDomainUsageData](cn.zh-CN/新版API参考/用量查询接口/DescribeDomainUsageData.md#)|查询域名特定在特定计费区域的用量数据。|

## 标签接口 {#section_vro_llp_b5m .section}

|API|描述|
|---|--|
|[DescribeTagResources](cn.zh-CN/新版API参考/标签接口/DescribeTagResources.md#)|查询资源对应的标签。|
|[DescribeUserTags](cn.zh-CN/新版API参考/标签接口/DescribeUserTags.md#)|查询用户标签。|
|[TagResources](cn.zh-CN/新版API参考/标签接口/TagResources.md#)|资源打标接口。|
|[UntagResources](cn.zh-CN/新版API参考/标签接口/UntagResources.md#)|删除资源标签接口。|

