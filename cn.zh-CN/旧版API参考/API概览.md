# API概览 {#doc_5189 .concept}

CDN提供以下相关API接口。

## 资源监控接口 {#section_6mo_o6n_gav .section}

|API|描述|
|---|--|
|[DescribeTopDomainsByFlow](cn.zh-CN/旧版API参考/资源监控接口/DescribeTopDomainsByFlow.md)|调用DescribeTopDomainsByFlow接口获取用户按流量排名的域名。|
|[DescribeDomainBpsData](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainBpsData.md)|调用DescribeDomainBpsData接口获取加速域名的网络带宽监控数据。|
|[DescribeDomainFlowData](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainFlowData.md)|调用DescribeDomainFlowData接口获取加速域名的网络流量监控数据。|
|[DescribeDomainSrcBpsData](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainSrcBpsData.md)|调用DescribeDomainSrcBpsData接口获取加速域名的回源带宽监控数据。|
|[DescribeDomainSrcFlowData](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainSrcFlowData.md)|调用DescribeDomainSrcFlowData接口获取加速域名的回源流量监控数据。|
|[DescribeDomainHitRateData](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainHitRateData.md)|调用DescribeDomainHitRateData接口获取加速域名的字节命中率（命中字节百分比）。|
|[DescribeDomainReqHitRateData](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainReqHitRateData.md)|调用DescribeDomainReqHitRateData接口获取加速域名的请求命中率（命中请求百分比）。|
|[DescribeDomainHttpCodeData](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainHttpCodeData.md)|调用DescribeDomainHttpCodeData接口获取加速域名最小5分钟粒度的HTTP返回码占比数据。|
|[DescribeDomainsUsageByDay](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainsUsageByDay.md)|调用DescribeDomainsUsageByDay接口获取加速域名天粒度监控统计数据。|
|[DescribeDomainPvData](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainPvData.md)|调用DescribeDomainPvData接口获取加速域名最小1小时粒度的 PV页面访问统计。|
|[DescribeDomainUvData](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainUvData.md)|调用DescribeDomainUvData接口获取加速域名最小1小时粒度的 UV页面独立访问统计。|
|[DescribeDomainRegionData](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainRegionData.md)|调用DescribeDomainRegionData接口获取加速域名天粒度的用户区域分布数据统计。|
|[DescribeDomainISPData](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainISPData.md)|调用DescribeDomainISPData接口获取加速域名天粒度的用户运营商分布数据统计。|
|[DescribeDomainTopUrlVisit](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainTopUrlVisit.md)|调用DescribeDomainTopUrlVisit接口获取加速域名某天内的热门URL列表。|
|[DescribeDomainFileSizeProportionData](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainFileSizeProportionData.md)|调用DescribeDomainFileSizeProportionData接口获取加速域名最小1小时粒度的文件大小占比统计。|
|[DescribeCdnRegionAndIsp](cn.zh-CN/旧版API参考/资源监控接口/DescribeCdnRegionAndIsp.md)|调用DescribeCdnRegionAndIsp接口获取区域和运营商列表。|
|[DescribeDomainBpsDataByTimeStamp](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainBpsDataByTimeStamp.md)|调用DescribeDomainBpsDataByTimeStamp接口获取加速域名的在某个时刻不同Locate和Isp上的带宽数据。|
|[DescribeDomainMax95BpsData](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainMax95BpsData.md)|调用DescribeDomainMax95BpsData接口获取加速域名95带宽峰值监控数据。|
|[DescribeDomainPathData](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainPathData.md)|调用DescribeDomainPathData接口获取加速域名路径级别的5分钟维度的监控数据。|
|[DescribeL2VipsByDomain](cn.zh-CN/旧版API参考/资源监控接口/DescribeL2VipsByDomain.md)|调用DescribeL2VipsByDomain接口查询L2节点vip列表。|
|[DescribeRangeDataByLocateAndIspService](cn.zh-CN/旧版API参考/资源监控接口/DescribeRangeDataByLocateAndIspService.md)|调用DescribeRangeDataByLocateAndIspService接口获取加速域名的在某个时刻不同Locate和Isp上的带宽数据。|
|[DescribeDomainRealTimeBpsData](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainRealTimeBpsData.md)|调用DescribeDomainRealTimeBpsData接口获取域名1分钟粒度带宽数据。|
|[DescribeDomainRealTimeByteHitRateData](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainRealTimeByteHitRateData.md)|调用DescribeDomainRealTimeByteHitRateData接口获取域名1分钟粒度字节命中率数据。|
|[DescribeDomainRealTimeQpsData](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainRealTimeQpsData.md)|调用DescribeDomainRealTimeQpsData接口获取域名1分钟粒度每秒访问次数数据。|
|[DescribeDomainRealTimeReqHitRateData](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainRealTimeReqHitRateData.md)|调用DescribeDomainRealTimeReqHitRateData接口获取域名1分钟粒度请求命中率数据。|
|[DescribeDomainTopReferVisit](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainTopReferVisit.md)|调用DescribeDomainTopReferVisit接口获取加速域名某天的热门页面引用次数排名。|
|[DescribeDomainQpsData](cn.zh-CN/旧版API参考/资源监控接口/DescribeDomainQpsData.md)|调用DescribeDomainQpsData接口获取加速域名的每秒访问次数QPS。|

## 服务操作接口 {#section_5zf_cuk_org .section}

|API|描述|
|---|--|
|[OpenCdnService](cn.zh-CN/旧版API参考/服务操作接口/OpenCdnService.md)|调用OpenCdnService接口开通CDN服务。|
|[DescribeCdnService](cn.zh-CN/旧版API参考/服务操作接口/DescribeCdnService.md)|调用DescribeCdnService接口查询CDN服务状态。|
|[ModifyCdnService](cn.zh-CN/旧版API参考/服务操作接口/ModifyCdnService.md)|调用ModifyCdnService接口变更CDN服务的计费类型。|

## 日志信息接口 {#section_xwa_d9p_l0p .section}

|API|描述|
|---|--|
|[DescribeCdnDomainLogs](cn.zh-CN/旧版API参考/日志接口/DescribeCdnDomainLogs.md)|调用DescribeCdnDomainLogs接口获取指定域名的原始访问日志的下载地址。|
|[DescribeCustomLogConfig](cn.zh-CN/旧版API参考/日志接口/DescribeCustomLogConfig.md)|调用DescribeCustomLogConfig接口查询日志配置信息。|
|[DescribeDomainCustomLogConfig](cn.zh-CN/旧版API参考/日志接口/DescribeDomainCustomLogConfig.md)|调用DescribeDomainCustomLogConfig接口获取域名自定义日志格式配置信息。|
|[DescribeUserCustomLogConfig](cn.zh-CN/旧版API参考/日志接口/DescribeUserCustomLogConfig.md)|调用DescribeUserCustomLogConfig接口获取用户下所有自定义日志配置信息。|
|[ListDomainsByLogConfigId](cn.zh-CN/旧版API参考/日志接口/ListDomainsByLogConfigId.md)|调用ListDomainsByLogConfigId接口查询应用某自定义日志格式的所有域名列表。|
|[ModifyDomainCustomLogConfig](cn.zh-CN/旧版API参考/日志接口/ModifyDomainCustomLogConfig.md)|调用ModifyDomainCustomLogConfig接口修改域名所属日志自定义日志配置信息。|
|[ModifyUserCustomLogConfig](cn.zh-CN/旧版API参考/日志接口/ModifyUserCustomLogConfig.md)|调用ModifyUserCustomLogConfig接口修改用户下自定义日志配置信息。|

## 域名接口 {#section_mrg_uue_snq .section}

|API|描述|
|---|--|
|[AddCdnDomain](cn.zh-CN/旧版API参考/域名操作接口/AddCdnDomain.md)|调用AddCdnDomain接口添加加速域名。|
|[DescribeUserDomains](cn.zh-CN/旧版API参考/域名操作接口/DescribeUserDomains.md)|调用DescribeUserDomains接口查询用户名下所有的域名与状态。|
|[DescribeCdnDomainDetail](cn.zh-CN/旧版API参考/域名操作接口/DescribeCdnDomainDetail.md)|调用DescribeCdnDomainDetail接口获取指定加速域名配置的基本信息。|
|[ModifyCdnDomain](cn.zh-CN/旧版API参考/域名操作接口/ModifyCdnDomain.md)|调用ModifyCdnDomain接口修改加速域名。|
|[StartCdnDomain](cn.zh-CN/旧版API参考/域名操作接口/StartCdnDomain.md)|调用StartCdnDomain接口启用状态为“停用”的加速域名，将DomainStatus变更为online。|
|[StopCdnDomain](cn.zh-CN/旧版API参考/域名操作接口/StopCdnDomain.md)|调用StopCdnDomain接口停用某个加速域名。|
|[DeleteCdnDomain](cn.zh-CN/旧版API参考/域名操作接口/DeleteCdnDomain.md)|调用DeleteCdnDomain接口删除已添加的加速域名。|
|[DescribeDomainsBySource](cn.zh-CN/旧版API参考/域名操作接口/DescribeDomainsBySource.md)|调用DescribeDomainsBySource接口查询用户名下源站对应的所有域名名称列表|

## 配置操作接口 {#section_1rp_nbd_azr .section}

|API|描述|
|---|--|
|[DescribeDomainConfigs](cn.zh-CN/旧版API参考/配置操作接口/DescribeDomainConfigs.md)|调用DescribeDomainConfigs接口获取指定加速域名的配置。|
|[SetOptimizeConfig](cn.zh-CN/旧版API参考/配置操作接口/SetOptimizeConfig.md)|调用SetOptimizeConfig接口设置页面优化功能。|
|[SetPageCompressConfig](cn.zh-CN/旧版API参考/配置操作接口/SetPageCompressConfig.md)|调用SetPageCompressConfig接口设置智能压缩功能。|
|[SetIgnoreQueryStringConfig](cn.zh-CN/旧版API参考/配置操作接口/SetIgnoreQueryStringConfig.md)|调用SetIgnoreQueryStringConfig接口设置过滤参数功能。|
|[SetRangeConfig](cn.zh-CN/旧版API参考/配置操作接口/SetRangeConfig.md)|调用SetRangeConfig接口设置range回源功能。|
|[SetVideoSeekConfig](cn.zh-CN/旧版API参考/配置操作接口/SetVideoSeekConfig.md)|调用SetVideoSeekConfig接口设置拖拽播放功能。|
|[SetSourceHostConfig](cn.zh-CN/旧版API参考/配置操作接口/SetSourceHostConfig.md)|调用SetSourceHostConfig接口设置回源host功能。|
|[SetErrorPageConfig](cn.zh-CN/旧版API参考/配置操作接口/SetErrorPageConfig.md)|调用SetErrorPageConfig接口设置加速域名自定义404错误页面跳转。|
|[SetForceRedirectConfig](cn.zh-CN/旧版API参考/配置操作接口/SetForceRedirectConfig.md)|调用SetForceRedirectConfig接口设置强制访问跳转方式。|
|[SetRefererConfig](cn.zh-CN/旧版API参考/配置操作接口/SetRefererConfig.md)|调用SetRefererConfig接口设置加速域名的Refer防盗链功能。|
|[SetFileCacheExpiredConfig](cn.zh-CN/旧版API参考/配置操作接口/SetFileCacheExpiredConfig.md)|调用SetFileCacheExpiredConfig接口设置文件过期配置。|
|[SetPathCacheExpiredConfig](cn.zh-CN/旧版API参考/配置操作接口/SetPathCacheExpiredConfig.md)|调用SetPathCacheExpiredConfig接口修改目录过期配置。|
|[ModifyFileCacheExpiredConfig](cn.zh-CN/旧版API参考/配置操作接口/ModifyFileCacheExpiredConfig.md)|调用ModifyFileCacheExpiredConfig接口修改文件过期配置。|
|[ModifyPathCacheExpiredConfig](cn.zh-CN/旧版API参考/配置操作接口/ModifyPathCacheExpiredConfig.md)|调用ModifyPathCacheExpiredConfig接口修改路径过期配置。|
|[DeleteCacheExpiredConfig](cn.zh-CN/旧版API参考/配置操作接口/DeleteCacheExpiredConfig.md)|调用DeleteCacheExpiredConfig接口删除自定义缓存策略.。|
|[SetReqAuthConfig](cn.zh-CN/旧版API参考/配置操作接口/SetReqAuthConfig.md)|调用SetReqAuthConfig接口设置加速域名的访问鉴权配置。|
|[SetHttpHeaderConfig](cn.zh-CN/旧版API参考/配置操作接口/SetHttpHeaderConfig.md)|调用SetHttpHeaderConfig接口设置自定义http头。|
|[ModifyHttpHeaderConfig](cn.zh-CN/旧版API参考/配置操作接口/ModifyHttpHeaderConfig.md)|调用ModifyHttpHeaderConfig接口修改自定义HTTP头。|
|[DeleteHttpHeaderConfig](cn.zh-CN/旧版API参考/配置操作接口/DeleteHttpHeaderConfig.md)|调用DeleteHttpHeaderConfig接口删除加速域名的Refer防盗链配置。|
|[SetDomainServerCertificate](cn.zh-CN/旧版API参考/配置操作接口/SetDomainServerCertificate.md)|调用SetDomainServerCertificate接口设置某域名下证书功能是否启用及修改证书信息。|
|[SetIpBlackListConfig](cn.zh-CN/旧版API参考/配置操作接口/SetIpBlackListConfig.md)|调用SetIpBlackListConfig接口设置加速域名的IP黑名单。|
|[SetHttpsOptionConfig](cn.zh-CN/旧版API参考/配置操作接口/SetHttpsOptionConfig.md)|调用SetHttpsOptionConfig接口设置域名的HTTP2.0开关。|
|[BatchDeleteCdnDomainConfig](cn.zh-CN/旧版API参考/配置操作接口/BatchDeleteCdnDomainConfig.md)|调用BatchDeleteCdnDomainConfig接口删除域名配置。|
|[DeleteSpecificConfig](cn.zh-CN/旧版API参考/配置操作接口/DeleteSpecificConfig.md)|调用DeleteSpecificConfig接口删除加速域名的配置。|
|[SetDomainGreenManagerConfig](cn.zh-CN/旧版API参考/配置操作接口/SetDomainGreenManagerConfig.md)|调用SetDomainGreenManagerConfig接口设置域名图片鉴黄功能开关。|
|[SetForwardSchemeConfig](cn.zh-CN/旧版API参考/配置操作接口/SetForwardSchemeConfig.md)|调用SetForwardSchemeConfig接口设置回源协议。|
|[SetHttpErrorPageConfig](cn.zh-CN/旧版API参考/配置操作接口/SetHttpErrorPageConfig.md)|调用SetHttpErrorPageConfig接口设置加速域名自定义错误页面跳转。|
|[SetRemoveQueryStringConfig](cn.zh-CN/旧版API参考/配置操作接口/SetRemoveQueryStringConfig.md)|调用SetRemoveQueryStringConfig接口设置过滤参数功能（删除\)。|
|[SetCcConfig](cn.zh-CN/旧版API参考/配置操作接口/SetCcConfig.md)|调用SetCcConfig接口设置加速域名的CC防护功能、IP黑白名单设置。|
|[SetReqHeaderConfig](cn.zh-CN/旧版API参考/配置操作接口/SetReqHeaderConfig.md)|调用SetReqHeaderConfig接口设置回源自定义头。|
|[SetUserGreenManagerConfig](cn.zh-CN/旧版API参考/配置操作接口/SetUserGreenManagerConfig.md)|调用SetUserGreenManagerConfig接口设置用户的图片鉴黄配置，包括抽检比例和限额。|
|[SetIpAllowListConfig](cn.zh-CN/旧版API参考/配置操作接口/SetIpAllowListConfig.md)|调用SetIpAllowListConfig接口设置加速域名的IP白名单。|
|[DescribeUserConfigs](cn.zh-CN/旧版API参考/配置操作接口/DescribeUserConfigs.md)|调用DescribeUserConfigs接口获取用户相应的配置。|

## 辅助工具接口 {#section_fer_4pe_ffo .section}

|API|描述|
|---|--|
|[DescribeIpInfo](cn.zh-CN/旧版API参考/辅助工接口/DescribeIpInfo.md)|调用DescribeIpInfo接口验证指定的IP是否为阿里云CDN节点的IP地址。|

## 刷新预热接口 {#section_4x9_jjb_pjs .section}

|API|描述|
|---|--|
|[RefreshObjectCaches](cn.zh-CN/旧版API参考/刷新预热类接口/RefreshObjectCaches.md)|调用RefreshObjectCaches接口刷新节点上的文件内容。|
|[PushObjectCache](cn.zh-CN/旧版API参考/刷新预热类接口/PushObjectCache.md)|调用PushObjectCache接口将源站的内容主动预热到L2 Cache节点上。|
|[DescribeRefreshTasks](cn.zh-CN/旧版API参考/刷新预热类接口/DescribeRefreshTasks.md)|调用DescribeRefreshTasks接口查询刷新、预热状态是否在全网生效。|
|[DescribeRefreshQuota](cn.zh-CN/旧版API参考/刷新预热类接口/DescribeRefreshQuota.md)|调用DescribeRefreshQuota接口刷新（包含预热）URL及目录的最大限制数量。|

## 全站加速接口 {#section_aa7_4vj_dg9 .section}

|API|描述|
|---|--|
|[SetDynamicConfig](cn.zh-CN/旧版API参考/全站加速接口/SetDynamicConfig.md)|调用SetDynamicConfig接口配置全站加速缓存规则。|

## RAM资源授权 {#section_fnj_fmu_myt .section}

|API|描述|
|---|--|
|[CDN API鉴权规则](cn.zh-CN/旧版API参考/RAM资源授权/CDN API鉴权规则.md)|CDN API鉴权规则|

## 数据类型 {#section_5fm_vcx_k0h .section}

|API|描述|
|---|--|
|[MonitorDataItem数据类型](cn.zh-CN/旧版API参考/数据类型/MonitorDataItem数据类型.md)|MonitorDataItem数据的类型。|
|[Domains数据类型](cn.zh-CN/旧版API参考/数据类型/Domains数据类型.md)|Domains数据的类型。|
|[Taskitem数据类型](cn.zh-CN/旧版API参考/数据类型/Taskitem数据类型.md)|TaskItem数据的类型。|
|[LogDetail数据类型](cn.zh-CN/旧版API参考/数据类型/LogDetail数据类型.md)|LogDetail数据的类型。|

