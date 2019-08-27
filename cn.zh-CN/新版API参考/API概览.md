# API概览 {#doc_122676 .concept}

CDN提供以下相关API接口。

## 数据监控接口 {#section_cca_chx_ylo .section}

|API|描述|
|---|--|
|[DescribeDomainSrcHttpCodeData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainSrcHttpCodeData.md)|调用DescribeDomainSrcHttpCodeData获取加速域名最小5分钟粒度的回源HTTP返回码占比数据。|
|[DescribeDomainTopReferVisit](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainTopReferVisit.md)|调用DescribeDomainTopReferVisit获取加速域名某天的热门页面引用次数排名。|
|[DescribeDomainAverageResponseTime](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainAverageResponseTime.md)|调DescribeDomainAverageResponseTime获取加速域名的平均响应时间。|
|[DescribeDomainFileSizeProportionData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainFileSizeProportionData.md)|调用DescribeDomainFileSizeProportionData获取加速域名最小1小时粒度的文件大小占比统计。|
|[DescribeDomainBpsDataByTimeStamp](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainBpsDataByTimeStamp.md)|调用DescribeDomainBpsDataByTimeStamp获取加速域名的在某个时刻的带宽数据。|
|[DescribeDomainISPData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainISPData.md)|调用DescribeDomainISPData获取加速域名天粒度的用户运营商分布数据统计。|
|[DescribeCdnRegionAndIsp](cn.zh-CN/新版API参考/数据监控类接口/DescribeCdnRegionAndIsp.md)|调用DescribeCdnRegionAndIsp获取区域和运营商列表。|
|[DescribeRangeDataByLocateAndIspService](cn.zh-CN/新版API参考/数据监控类接口/DescribeRangeDataByLocateAndIspService.md)|调用DescribeRangeDataByLocateAndIspService获取加速域名的在某个时刻不同Locate和Isp上的带宽数据。|
|[DescribeDomainRealTimeBpsData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainRealTimeBpsData.md)|调用DescribeDomainRealTimeBpsData获取域名1分钟粒度带宽数据。|
|[DescribeDomainRealTimeSrcBpsData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainRealTimeSrcBpsData.md)|调用DescribeDomainRealTimeSrcBpsData获取域名1分钟粒度回源带宽数据。|
|[DescribeDomainRealTimeSrcHttpCodeData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainRealTimeSrcHttpCodeData.md)|调用DescribeDomainRealTimeSrcHttpCodeData获取加速域名回源1分钟粒度的HTTP返回码占比数据。|
|[DescribeDomainRealTimeSrcTrafficData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainRealTimeSrcTrafficData.md)|调用DescribeDomainRealTimeSrcTrafficData获取加速域名的1分钟回源流量监控数据，单位：bit。|
|[DescribeDomainRealTimeByteHitRateData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainRealTimeByteHitRateData.md)|调用DescribeDomainRealTimeByteHitRateData获取域名1分钟粒度字节命中率数据。|
|[DescribeDomainRealTimeQpsData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainRealTimeQpsData.md)|调用DescribeDomainRealTimeQpsData获取域名1分钟粒度每秒访问次数数据。|
|[DescribeDomainRealTimeHttpCodeData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainRealTimeHttpCodeData.md)|调用DescribeDomainRealTimeHttpCodeData获取加速域名1分钟粒度的HTTP返回码占比数据。|
|[DescribeDomainRealTimeTrafficData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainRealTimeTrafficData.md)|调用DescribeDomainRealTimeTrafficData获取加速域名的1分钟流量监控数据，单位：Byte。|
|[DescribeDomainRealTimeReqHitRateData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainRealTimeReqHitRateData.md)|调用DescribeDomainRealTimeReqHitRateData获取域名1分钟粒度请求命中率数据。|
|[DescribeDomainBpsData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainBpsData.md)|调用DescribeDomainBpsData获取加速域名的网络带宽监控数据。|
|[DescribeDomainSrcBpsData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainSrcBpsData.md)|调用DescribeDomainSrcBpsData获取加速域名的回源带宽监控数据。|
|[DescribeDomainSrcTrafficData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainSrcTrafficData.md)|调用DescribeDomainSrcTrafficData获取加速域名的回源流量监控数据，单位：bit。|
|[DescribeDomainsUsageByDay](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainsUsageByDay.md)|调用DescribeDomainsUsageByDay获取加速域名天粒度监控统计数据。|
|[DescribeDomainHitRateData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainHitRateData.md)|调用DescribeDomainHitRateData获取加速域名的字节命中率（命中字节百分比）。|
|[DescribeL2VipsByDomain](cn.zh-CN/新版API参考/数据监控类接口/DescribeL2VipsByDomain.md)|调用DescribeL2VipsByDomain按域名查询L2节点的回源IP。|
|[DescribeDomainReqHitRateData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainReqHitRateData.md)|调用DescribeDomainReqHitRateData获取加速域名的请求命中率（命中请求百分比）。|
|[DescribeDomainHttpCodeData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainHttpCodeData.md)|调用DescribeDomainHttpCodeData获取加速域名最小5分钟粒度的HTTP返回码占比数据。|
|[DescribeDomainTrafficData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainTrafficData.md)|调用DescribeDomainTrafficData获取加速域名的网络流量监控数据，单位：byte。|
|[DescribeTopDomainsByFlow](cn.zh-CN/新版API参考/数据监控类接口/DescribeTopDomainsByFlow.md)|调用DescribeTopDomainsByFlow获取用户按流量排名的域名。|
|[DescribeDomainRegionData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainRegionData.md)|调用DescribeDomainRegionData获取加速域名天粒度的用户区域分布数据统计。|
|[DescribeDomainUvData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainUvData.md)|调用DescribeDomainUvData获取加速域名最小1小时粒度的 UV页面独立访问统计。|
|[DescribeDomainPvData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainPvData.md)|调用DescribeDomainPvData获取加速域名最小1小时粒度的 PV页面访问统计。|
|[ListFCTrigger](cn.zh-CN/新版API参考/数据监控类接口/ListFCTrigger.md)|调用ListFCTrigger获取指定事件的函数计算触发器列表。|
|[DescribeDomainQpsData](cn.zh-CN/新版API参考/数据监控类接口/DescribeDomainQpsData.md)|调用DescribeDomainQpsData获取加速域名的每秒访问次数QPS。|

## 域名管理接口 {#section_ndy_jhp_ynh .section}

|API|描述|
|---|--|
|[AddCdnDomain](cn.zh-CN/新版API参考/域名管理类接口/AddCdnDomain.md)|调用AddCdnDomain添加加速域名。|
|[BatchAddCdnDomain](cn.zh-CN/新版API参考/域名管理类接口/BatchAddCdnDomain.md)|调用BatchAddCdnDomain批量添加加速域名，一个用户最多添加20个域名。|
|[DeleteCdnDomain](cn.zh-CN/新版API参考/域名管理类接口/DeleteCdnDomain.md)|调用DeleteCdnDomain删除已添加的加速域名。|
|[StartCdnDomain](cn.zh-CN/新版API参考/域名管理类接口/StartCdnDomain.md)|调用StartCdnDomain启用状态为停用的加速域名，将 DomainStatus变更为Online。|
|[StopCdnDomain](cn.zh-CN/新版API参考/域名管理类接口/StopCdnDomain.md)|调用StopCdnDomain停用某个加速域名，将DomainStatus变更为Offline。|
|[BatchStartCdnDomain](cn.zh-CN/新版API参考/域名管理类接口/BatchStartCdnDomain.md)|调用BatchStartCdnDomain启用状态为停用的加速域名，将DomainStatus变更为Online。|
|[BatchStopCdnDomain](cn.zh-CN/新版API参考/域名管理类接口/BatchStopCdnDomain.md)|调用BatchStopCdnDomain批量停用加速域名，将DomainStatus变更为Offline。|
|[BatchSetCdnDomainConfig](cn.zh-CN/新版API参考/域名管理类接口/BatchSetCdnDomainConfig.md)|调用BatchSetCdnDomainConfig进行域名批量配置。|
|[ModifyCdnDomain](cn.zh-CN/新版API参考/域名管理类接口/ModifyCdnDomain.md)|调用ModifyCdnDomain修改加速域名。|
|[DescribeUserDomains](cn.zh-CN/新版API参考/域名管理类接口/DescribeUserDomains.md)|调用DescribeUserDomains查询用户名下所有的域名与状态。支持域名模糊匹配过滤和域名状态过滤。|
|[DescribeCdnCertificateList](cn.zh-CN/新版API参考/域名管理类接口/DescribeCdnCertificateList.md)|调用DescribeCdnCertificateList获取证书列表信息。|
|[DescribeDomainCertificateInfo](cn.zh-CN/新版API参考/域名管理类接口/DescribeDomainCertificateInfo.md)|调用DescribeDomainCertificateInfo获取指定加速域名证书信息。|
|[DescribeCdnDomainDetail](cn.zh-CN/新版API参考/域名管理类接口/DescribeCdnDomainDetail.md)|调用DescribeCdnDomainDetail获取指定加速域名配置的基本信息。|
|[DescribeDomainsBySource](cn.zh-CN/新版API参考/域名管理类接口/DescribeDomainsBySource.md)|调用DescribeDomainsBySource查询用户名下，源站对应的所有域名名称列表。不支持模糊匹配。|
|[SetDomainServerCertificate](cn.zh-CN/新版API参考/域名管理类接口/SetDomainServerCertificate.md)|调用SetDomainServerCertificate该接口用于设置某域名下证书功能是否启用及修改证书信息。|
|[DescribeCdnDomainConfigs](cn.zh-CN/新版API参考/域名管理类接口/DescribeCdnDomainConfigs.md)|调用DescribeCdnDomainConfigs查询域名配置，一次可查询多个功能配置。|
|[DeleteSpecificConfig](cn.zh-CN/新版API参考/域名管理类接口/DeleteSpecificConfig.md)|调用DeleteSpecificConfig删除加速域名的配置。|
|[DescribeUserVipsByDomain](cn.zh-CN/新版API参考/域名管理类接口/DescribeUserVipsByDomain.md)|调用DescribeUserVipsByDomain按域名查询vip列表。|
|[DescribeCdnHttpsDomainList](cn.zh-CN/新版API参考/域名管理类接口/DescribeCdnHttpsDomainList.md)|调用DescribeCdnHttpsDomainList获取用户所有证书信息。|
|[ModifyCdnDomainSchdmByProperty](cn.zh-CN/新版API参考/域名管理类接口/ModifyCdnDomainSchdmByProperty.md)|调用ModifyCdnDomainSchdmByProperty修改加速域名。|
|[BatchUpdateCdnDomain](cn.zh-CN/新版API参考/域名管理类接口/BatchUpdateCdnDomain.md)|调用BatchUpdateCdnDomain批量更新加速域名。|
|[BatchSetCdnDomainServerCertificate](cn.zh-CN/新版API参考/域名管理类接口/BatchSetCdnDomainServerCertificate.md)|调用BatchSetCdnDomainServerCertificate批量设置域名下证书功能是否启用及修改证书信息。|
|[SetWafConfig](cn.zh-CN/新版API参考/域名管理类接口/SetWafConfig.md)|调用SetWafConfig设置加速域名的Waf防护功能。|
|[DescribeCdnDomainByCertificate](cn.zh-CN/新版API参考/域名管理类接口/DescribeCdnDomainByCertificate.md)|调用DescribeCdnDomainByCertificate根据证书信息获取加速域名。|
|[SetWaitingRoomConfig](cn.zh-CN/新版API参考/域名管理类接口/SetWaitingRoomConfig.md)|调用SetWaitingRoomConfig设置waiting\_room功能，只支持全站加速类型域名。|
|[DescribeCdnCertificateDetail](cn.zh-CN/新版API参考/域名管理类接口/DescribeCdnCertificateDetail.md)|调用DescribeCdnCertificateDetail查询cdn证书详细信息。|

## 日志类接口 {#section_u5h_73q_srt .section}

|API|描述|
|---|--|
|[DescribeCdnDomainLogs](cn.zh-CN/新版API参考/日志信息类接口/DescribeCdnDomainLogs.md)|调用DescribeCdnDomainLogs获取指定域名的原始访问日志的下载地址。|
|[CreateRealTimeLogDelivery](cn.zh-CN/新版API参考/日志信息类接口/CreateRealTimeLogDelivery.md)|调用CreateRealTimeLogDelivery创建域名实时日志投递。|
|[DeleteRealtimeLogDelivery](cn.zh-CN/新版API参考/日志信息类接口/DeleteRealtimeLogDelivery.md)|调用DeleteRealtimeLogDelivery删除实时日志推送域名。|
|[DescribeDomainRealtimeLogDelivery](cn.zh-CN/新版API参考/日志信息类接口/DescribeDomainRealtimeLogDelivery.md)|调用DescribeDomainRealtimeLogDelivery查询域名实时日志投递信息。|
|[DescribeRealtimeDeliveryAcc](cn.zh-CN/新版API参考/日志信息类接口/DescribeRealtimeDeliveryAcc.md)|调用DescribeRealtimeDeliveryAcc实时日志投递次数查询。|
|[DisableRealtimeLogDelivery](cn.zh-CN/新版API参考/日志信息类接口/DisableRealtimeLogDelivery.md)|调用DisableRealtimeLogDelivery暂停域名实时日志投递。|
|[EnableRealtimeLogDelivery](cn.zh-CN/新版API参考/日志信息类接口/EnableRealtimeLogDelivery.md)|调用EnableRealtimeLogDelivery开启域名实时日志投递。|
|[ListRealtimeLogDeliveryDomains](cn.zh-CN/新版API参考/日志信息类接口/ListRealtimeLogDeliveryDomains.md)|调用ListRealtimeLogDeliveryDomains查询实时日志投递服务下所有域名。|
|[ModifyRealtimeLogDelivery](cn.zh-CN/新版API参考/日志信息类接口/ModifyRealtimeLogDelivery.md)|调用ModifyRealtimeLogDelivery更改域名实时日志投递。一个域名同时仅支持投递单个logstore。|
|[ListRealtimeLogDeliveryInfos](cn.zh-CN/新版API参考/日志信息类接口/ListRealtimeLogDeliveryInfos.md)|调用ListRealtimeLogDeliveryInfos查询所有实时日志投递服务信息。|
|[DescribeDomainCustomLogConfig](cn.zh-CN/新版API参考/日志信息类接口/DescribeDomainCustomLogConfig.md)|调用DescribeDomainCustomLogConfig获取域名自定义日志格式配置信息。|
|[ListDomainsByLogConfigId](cn.zh-CN/新版API参考/日志信息类接口/ListDomainsByLogConfigId.md)|调用ListDomainsByLogConfigId查询应用某自定义日志格式的所有域名列表。|
|[ListUserCustomLogConfig](cn.zh-CN/新版API参考/日志信息类接口/ListUserCustomLogConfig.md)|调用ListUserCustomLogConfig获取用户下所有自定义日志配置信息。|
|[ModifyUserCustomLogConfig](cn.zh-CN/新版API参考/日志信息类接口/ModifyUserCustomLogConfig.md)|调用ModifyUserCustomLogConfig修改用户下自定义日志配置信息。|
|[DescribeCustomLogConfig](cn.zh-CN/新版API参考/日志信息类接口/DescribeCustomLogConfig.md)|调用DescribeCustomLogConfig根据configId查询自定义日志配置详细信息。|

## 刷新预热接口 {#section_nsc_s0d_o6y .section}

|API|描述|
|---|--|
|[RefreshObjectCaches](cn.zh-CN/新版API参考/刷新预热类接口/RefreshObjectCaches.md)|调用RefreshObjectCaches刷新节点上的文件内容。刷新指定URL内容至Cache节点，支持URL批量刷新。|
|[PushObjectCache](cn.zh-CN/新版API参考/刷新预热类接口/PushObjectCache.md)|调用PushObjectCache将源站的内容主动预热到L2 Cache节点上，您首次访问可直接命中缓存，缓解源站压力。|
|[DescribeRefreshQuota](cn.zh-CN/新版API参考/刷新预热类接口/DescribeRefreshQuota.md)|调用DescribeRefreshQuota查询刷新、预热URL及目录的最大限制数量，以及当日剩余刷新、预热URL及目录的次数。|
|[DescribeRefreshTasks](cn.zh-CN/新版API参考/刷新预热类接口/DescribeRefreshTasks.md)|调用DescribeRefreshTasks查询刷新、预热状态是否在全网生效。|

## 服务类接口 {#section_akw_hlk_r9p .section}

|API|描述|
|---|--|
|[OpenCdnService](cn.zh-CN/新版API参考/服务类类接口/OpenCdnService.md)|调用OpenCdnService开通CDN服务。只有开通服务后，才能进行域名操作。|
|[ModifyCdnService](cn.zh-CN/新版API参考/服务类类接口/ModifyCdnService.md)|调用ModifyCdnService变更CDN服务的计费类型。|
|[DescribeCdnService](cn.zh-CN/新版API参考/服务类类接口/DescribeCdnService.md)|调用DescribeCdnService查询CDN服务状态。包括：当前计费类型，服务开通时间，下次生效的计费类型，当前业务状态等。|
|[DescribeCdnUserResourcePackage](cn.zh-CN/新版API参考/服务类类接口/DescribeCdnUserResourcePackage.md)|调用DescribeCdnUserResourcePackage查询CDN用户当前流量包。|
|[DescribeCdnUserQuota](cn.zh-CN/新版API参考/服务类类接口/DescribeCdnUserQuota.md)|调用DescribeCdnUserQuota查询用户资源上限及已使用情况。|

## 用量查询接口 {#section_qky_pup_bkr .section}

|API|描述|
|---|--|
|[DescribeUserUsageDataExportTask](cn.zh-CN/新版API参考/用量查询类接口/DescribeUserUsageDataExportTask.md)|调用DescribeUserUsageDataExportTask列出用户最近三个月的用量导出任务信息。|
|[CreateUserUsageDataExportTask](cn.zh-CN/新版API参考/用量查询类接口/CreateUserUsageDataExportTask.md)|调用CreateUserUsageDataExportTask创建账号历史用量数据导出任务，将历史用量生成PDF文件用于下载。|
|[CreateUsageDetailDataExportTask](cn.zh-CN/新版API参考/用量查询类接口/CreateUsageDetailDataExportTask.md)|调用CreateUsageDetailDataExportTask创建您账户下单个或多个域名5分钟明细数据的导出任务，生成用于下载的excel文件。|
|[DescribeUserUsageDetailDataExportTask](cn.zh-CN/新版API参考/用量查询类接口/DescribeUserUsageDetailDataExportTask.md)|调用DescribeUserUsageDetailDataExportTask查询您账户下单个或多个域名5分钟明细数据的导出任务。|
|[DescribeDomainUsageData](cn.zh-CN/新版API参考/用量查询类接口/DescribeDomainUsageData.md)|调用DescribeDomainUsageData查询域名在特定计费区域的用量数据。|
|[DeleteUserUsageDataExportTask](cn.zh-CN/新版API参考/用量查询类接口/DeleteUserUsageDataExportTask.md)|调用DeleteUserUsageDataExportTask创建历史用量信息导出任务，将详细用量生成excel文件用于下载。最长可创建查询近1年数据的任务，单次导出任务跨度最长为1个月。|
|[DeleteUsageDetailDataExportTask](cn.zh-CN/新版API参考/用量查询类接口/DeleteUsageDetailDataExportTask.md)|调用DeleteUsageDetailDataExportTask删掉用量详细数据导出任务。|

## 标签接口 {#section_2cn_awz_awi .section}

|API|描述|
|---|--|
|[DescribeTagResources](cn.zh-CN/新版API参考/标签类接口/DescribeTagResources.md)|调用DescribeTagResources查询资源对应的标签。|
|[DescribeUserTags](cn.zh-CN/新版API参考/标签类接口/DescribeUserTags.md)|调用DescribeUserTags查询用户标签。|
|[UntagResources](cn.zh-CN/新版API参考/标签类接口/UntagResources.md)|调用UntagResources删除资源标签接口。|
|[TagResources](cn.zh-CN/新版API参考/标签类接口/TagResources.md)|调用TagResources资源打标接口。|

