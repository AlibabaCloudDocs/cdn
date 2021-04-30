# API概览

CDN提供以下相关API接口。

## 数据监控类接口

|API|描述|
|---|--|
|[DescribeDomainSrcHttpCodeData](/cn.zh-CN/新版API参考/数据监控类接口/获取回源HTTP返回码数据.md)|调用DescribeDomainSrcHttpCodeData获取加速域名5分钟计算粒度的回源HTTP返回码的总数和占比数据，支持获取最近90天的数据。|
|[DescribeDomainTopReferVisit](/cn.zh-CN/新版API参考/数据监控类接口/获取热门页面引用次数排名.md)|调用DescribeDomainTopReferVisit获取加速域名某天的热门页面引用次数排名，支持获取最近90天的数据。|
|[DescribeDomainTopUrlVisit](/cn.zh-CN/新版API参考/数据监控类接口/获取热门URL列表.md)|调用DescribeDomainTopUrlVisit获取加速域名某天内的热门URL列表，支持获取最近90天的数据。|
|[DescribeDomainAverageResponseTime](/cn.zh-CN/新版API参考/数据监控类接口/获取平均响应时间数据.md)|调DescribeDomainAverageResponseTime获取加速域名的平均响应时间，支持获取最近90天的数据。|
|[DescribeDomainFileSizeProportionData](/cn.zh-CN/新版API参考/数据监控类接口/获取文件大小占比统计.md)|调用DescribeDomainFileSizeProportionData获取加速域名1小时粒度的文件大小占比统计，支持获取最近90天的数据。|
|[DescribeDomainBpsDataByTimeStamp](/cn.zh-CN/新版API参考/数据监控类接口/获取在某个时刻的带宽数据.md)|调用DescribeDomainBpsDataByTimeStamp获取加速域名在某个时刻的带宽数据。|
|[DescribeDomainISPData](/cn.zh-CN/新版API参考/数据监控类接口/获取用户运营商分布数据.md)|调用DescribeDomainISPData获取加速域名天粒度的用户运营商分布数据统计，支持获取最近90天的数据。|
|[DescribeCdnRegionAndIsp](/cn.zh-CN/新版API参考/数据监控类接口/获取地域和运营商列表.md)|调用DescribeCdnRegionAndIsp获取区域和运营商列表。|
|[DescribeRangeDataByLocateAndIspService](/cn.zh-CN/新版API参考/数据监控类接口/获取运营商和地域带宽数据.md)|调用DescribeRangeDataByLocateAndIspService获取加速域名在某个时刻不同运营商和区域上的带宽数据。|
|[DescribeDomainRealTimeBpsData](/cn.zh-CN/新版API参考/数据监控类接口/获取加速域名的带宽数据.md)|调用DescribeDomainRealTimeBpsData获取加速域名1分钟粒度带宽数据，支持查询7天内的数据。|
|[DescribeDomainRealTimeSrcBpsData](/cn.zh-CN/新版API参考/数据监控类接口/获取回源带宽数据.md)|调用DescribeDomainRealTimeSrcBpsData获取域名1分钟粒度回源带宽数据，支持获取最近7天的数据。|
|[DescribeDomainRealTimeSrcHttpCodeData](/cn.zh-CN/新版API参考/数据监控类接口/获取实时回源HTTP返回码数据.md)|调用DescribeDomainRealTimeSrcHttpCodeData获取加速域名回源1分钟粒度HTTP返回码的总数和占比数据，支持获取最近7天的数据。|
|[DescribeDomainRealTimeSrcTrafficData](/cn.zh-CN/新版API参考/数据监控类接口/获取实时回源流量监控数据.md)|调用DescribeDomainRealTimeSrcTrafficData获取加速域名的1分钟回源流量监控数据，支持获取最近90天的数据，数据单位：bit。|
|[DescribeDomainRealTimeByteHitRateData](/cn.zh-CN/新版API参考/数据监控类接口/获取字节命中率数据.md)|调用DescribeDomainRealTimeByteHitRateData获取域名1分钟粒度字节命中率数据，支持查询7天内的数据。|
|[DescribeDomainRealTimeQpsData](/cn.zh-CN/新版API参考/数据监控类接口/获取实时每秒访问次数数据.md)|调用DescribeDomainRealTimeQpsData获取加速域名1分钟粒度每秒访问次数数据，支持查询7天内的数据。|
|[DescribeDomainRealTimeHttpCodeData](/cn.zh-CN/新版API参考/数据监控类接口/获取实时HTTP返回码数据.md)|调用DescribeDomainRealTimeHttpCodeData获取加速域名1分钟粒度HTTP返回码的总数和占比数据，支持获取最近7天的数据。|
|[DescribeDomainRealTimeTrafficData](/cn.zh-CN/新版API参考/数据监控类接口/获取流量监控数据.md)|调用DescribeDomainRealTimeTrafficData获取加速域名的1分钟粒度流量监控数据，支持获取最近90天的数据，数据单位：Byte。|
|[DescribeDomainRealTimeReqHitRateData](/cn.zh-CN/新版API参考/数据监控类接口/获取请求命中率数据.md)|调用DescribeDomainRealTimeReqHitRateData获取加速域名1分钟粒度请求命中率数据，支持查询7天内的数据。|
|[DescribeDomainBpsData](/cn.zh-CN/新版API参考/数据监控类接口/获取网络带宽监控数据.md)|调用DescribeDomainBpsData获取加速域名的网络带宽监控数据，支持获取最近90天的数据。|
|[DescribeDomainSrcBpsData](/cn.zh-CN/新版API参考/数据监控类接口/获取回源带宽监控数据.md)|调用DescribeDomainSrcBpsData获取加速域名的回源带宽监控数据，支持获取最近90天的数据。|
|[DescribeDomainSrcTrafficData](/cn.zh-CN/新版API参考/数据监控类接口/获取回源流量监控数据.md)|调用DescribeDomainSrcTrafficData获取加速域名的回源流量监控数据，支持获取最近90天的数据，单位：bit。|
|[DescribeDomainsUsageByDay](/cn.zh-CN/新版API参考/数据监控类接口/获取天粒度的监控统计数据.md)|调用DescribeDomainsUsageByDay获取加速域名天粒度监控统计数据，支持获取最近90天的数据。|
|[DescribeDomainHitRateData](/cn.zh-CN/新版API参考/数据监控类接口/获取加速域名的字节命中率.md)|调用DescribeDomainHitRateData获取加速域名的字节命中率（命中字节百分比），支持获取最近90天的数据。|
|[DescribeL2VipsByDomain](/cn.zh-CN/新版API参考/数据监控类接口/获取L2节点的回源IP.md)|调用DescribeL2VipsByDomain查询指定域名的L2节点的回源IP。|
|[DescribeDomainReqHitRateData](/cn.zh-CN/新版API参考/数据监控类接口/获取加速域名的请求命中率.md)|调用DescribeDomainReqHitRateData获取加速域名的请求命中率（命中请求百分比），支持获取最近90天的数据。|
|[DescribeDomainHttpCodeData](/cn.zh-CN/新版API参考/数据监控类接口/获取HTTP返回码数据.md)|调用DescribeDomainHttpCodeData获取加速域名HTTP返回码的总数和占比数据，支持获取最近90天的数据。|
|[DescribeDomainTrafficData](/cn.zh-CN/新版API参考/数据监控类接口/获取网络流量监控数据.md)|调用DescribeDomainTrafficData获取加速域名的网络流量监控数据，支持获取最近90天的数据，单位：Byte。|
|[DescribeTopDomainsByFlow](/cn.zh-CN/新版API参考/数据监控类接口/获取按流量排名的加速域名.md)|调用DescribeTopDomainsByFlow获取用户按流量排名的域名，支持获取最近90天的数据。|
|[DescribeDomainRegionData](/cn.zh-CN/新版API参考/数据监控类接口/获取用户区域分布数据统计.md)|调用DescribeDomainRegionData获取加速域名天粒度的用户区域分布数据统计。|
|[DescribeDomainUvData](/cn.zh-CN/新版API参考/数据监控类接口/获取UV页面独立访问统计.md)|调用DescribeDomainUvData获取加速域名1小时粒度的UV页面独立访问统计，支持获取最近90天的数据。|
|[DescribeDomainPvData](/cn.zh-CN/新版API参考/数据监控类接口/获取PV页面访问统计.md)|调用DescribeDomainPvData获取加速域名1小时粒度的PV页面访问统计。|
|[DescribeDomainQpsData](/cn.zh-CN/新版API参考/数据监控类接口/获取每秒访问次数QPS.md)|调用DescribeDomainQpsData获取5分钟计算粒度加速域名的每秒访问次数QPS，支持获取最近90天的数据。|
|[ListFCTrigger](/cn.zh-CN/新版API参考/数据监控类接口/获取指定事件的触发器列表.md)|调用ListFCTrigger获取指定事件的函数计算触发器列表。|
|[DescribeDomainQpsDataByLayer](/cn.zh-CN/新版API参考/数据监控类接口/获取各维度的每秒访问次数.md)|调用DescribeDomainQpsDataByLayer获取加速域名的每秒访问次数QPS，支持获取最近90天的数据。|
|[DescribeDomainTopClientIpVisit](/cn.zh-CN/新版API参考/数据监控类接口/获取Client IP列表排序数据.md)|调用DescribeDomainTopClientIpVisit获取加速域名在指定时间范围内按照访问次数或流量排序的Client IP排行，支持获取最近90天的数据。|
|[DescribeDomainRealTimeDetailData]()|调用DescribeDomainRealTimeDetailData批量获取域名的各地区运营商流量和访问次数的1分钟粒度数据，支持查询7天内的数据。|
|[DescribeDomainSrcTopUrlVisit](/cn.zh-CN/新版API参考/数据监控类接口/获取回源热门URL.md)|调用DescribeDomainSrcTopUrlVisit获取加速域名回源的热门URL。|
|[DescribeDomainSrcQpsData](/cn.zh-CN/新版API参考/数据监控类接口/获取回源请求QPS数据.md)|调用DescribeDomainSrcQpsData获取加速域名的回源请求QPS数据。|

## 域名管理类接口

|API|描述|
|---|--|
|[AddCdnDomain](/cn.zh-CN/新版API参考/域名管理类接口/添加加速域名.md)|调用AddCdnDomain添加加速域名。|
|[DeleteCdnDomain](/cn.zh-CN/新版API参考/域名管理类接口/删除已添加的加速域名.md)|调用DeleteCdnDomain删除已添加的加速域名。|
|[StopCdnDomain](/cn.zh-CN/新版API参考/域名管理类接口/停用加速域名.md)|调用StopCdnDomain停用某个加速域名，将DomainStatus变更为Offline。|
|[StartCdnDomain](/cn.zh-CN/新版API参考/域名管理类接口/启用状态为停用的加速域名.md)|调用StartCdnDomain启用状态为停用的加速域名，将DomainStatus变更为Online。|
|[BatchStartCdnDomain](/cn.zh-CN/新版API参考/域名管理类接口/批量启用加速域名.md)|调用BatchStartCdnDomain批量启用状态为停用的加速域名，将DomainStatus变更为Online。|
|[BatchSetCdnDomainConfig](/cn.zh-CN/新版API参考/域名管理类接口/批量配置域名.md)|调用BatchSetCdnDomainConfig进行域名批量配置。|
|[ModifyCdnDomain](/cn.zh-CN/新版API参考/域名管理类接口/修改加速域名信息.md)|调用ModifyCdnDomain修改加速域名信息。|
|[DescribeUserDomains](/cn.zh-CN/新版API参考/域名管理类接口/获取用户的加速域名信息.md)|调用DescribeUserDomains查询用户名下所有的域名与状态，支持域名模糊匹配过滤和域名状态过滤。|
|[DescribeCdnDomainDetail](/cn.zh-CN/新版API参考/域名管理类接口/获取基本配置信息.md)|调用DescribeCdnDomainDetail获取指定加速域名配置的基本信息。|
|[DescribeDomainsBySource](/cn.zh-CN/新版API参考/域名管理类接口/获取源站对应的加速域名.md)|调用DescribeDomainsBySource查询用户名下，源站对应的所有域名名称列表。|
|[BatchStopCdnDomain](/cn.zh-CN/新版API参考/域名管理类接口/批量停用加速域名.md)|调用BatchStopCdnDomain批量停用加速域名，将DomainStatus变更为Offline。|
|[DescribeCdnDomainConfigs](/cn.zh-CN/新版API参考/域名管理类接口/获取加速域名的配置信息.md)|调用DescribeCdnDomainConfigs查询域名配置，一次可查询多个功能配置。|
|[DeleteSpecificConfig](/cn.zh-CN/新版API参考/域名管理类接口/删除加速域名的配置.md)|调用DeleteSpecificConfig删除加速域名的配置。|
|[DescribeUserVipsByDomain](/cn.zh-CN/新版API参考/域名管理类接口/获取按域名查询的Vip列表.md)|调用DescribeUserVipsByDomain按域名查询vip列表。|
|[BatchAddCdnDomain](/cn.zh-CN/新版API参考/域名管理类接口/批量添加加速域名.md)|调用BatchAddCdnDomain批量添加加速域名，一个用户最多添加20个域名。|
|[ModifyCdnDomainSchdmByProperty](/cn.zh-CN/新版API参考/域名管理类接口/修改加速域名的加速区域.md)|调用ModifyCdnDomainSchdmByProperty修改加速域名加速区域。|
|[BatchUpdateCdnDomain](/cn.zh-CN/新版API参考/域名管理类接口/批量更新加速域名信息.md)|调用BatchUpdateCdnDomain批量更新加速域名信息。|
|[SetWaitingRoomConfig](/cn.zh-CN/新版API参考/域名管理类接口/设置WaitingRoom功能.md)|调用SetWaitingRoomConfig设置waiting\_room功能，只支持全站加速类型域名。|

## 日志信息类接口

|API|描述|
|---|--|
|[DescribeCdnDomainLogs](/cn.zh-CN/新版API参考/日志信息类接口/获取加速域名的日志信息.md)|调用DescribeCdnDomainLogs获取指定域名的原始访问日志的下载地址。|
|[CreateRealTimeLogDelivery](/cn.zh-CN/新版API参考/日志信息类接口/创建加速域名实时日志投递.md)|调用CreateRealTimeLogDelivery创建域名实时日志投递。|
|[DeleteRealtimeLogDelivery](/cn.zh-CN/新版API参考/日志信息类接口/删除加速域名实时日志推送.md)|调用DeleteRealtimeLogDelivery删除实时日志推送域名。|
|[DescribeDomainRealtimeLogDelivery](/cn.zh-CN/新版API参考/日志信息类接口/获取实时日志投递信息.md)|调用DescribeDomainRealtimeLogDelivery查询域名实时日志投递信息。|
|[DisableRealtimeLogDelivery](/cn.zh-CN/新版API参考/日志信息类接口/暂停加速域名实时日志投递.md)|调用DisableRealtimeLogDelivery暂停域名实时日志投递。|
|[EnableRealtimeLogDelivery](/cn.zh-CN/新版API参考/日志信息类接口/开启域名实时日志投递.md)|调用EnableRealtimeLogDelivery开启域名实时日志投递。|
|[ListRealtimeLogDeliveryDomains](/cn.zh-CN/新版API参考/日志信息类接口/获取日志投递的加速域名.md)|调用ListRealtimeLogDeliveryDomains查询实时日志投递服务下所有域名。|
|[ListRealtimeLogDeliveryInfos](/cn.zh-CN/新版API参考/日志信息类接口/获取实时日志投递服务信息.md)|调用ListRealtimeLogDeliveryInfos查询所有实时日志投递服务信息。|
|[ModifyRealtimeLogDelivery](/cn.zh-CN/新版API参考/日志信息类接口/修改加速域名实时日志投递.md)|调用ModifyRealtimeLogDelivery更改域名实时日志投递。一个域名同时仅支持投递单个logstore。|
|[DescribeDomainCustomLogConfig](/cn.zh-CN/新版API参考/日志信息类接口/获取加速域名日志配置信息.md)|调用DescribeDomainCustomLogConfig获取域名自定义日志格式配置信息。|
|[ListDomainsByLogConfigId](/cn.zh-CN/新版API参考/日志信息类接口/获取日志配置ID的加速域名.md)|调用ListDomainsByLogConfigId查询应用某自定义日志格式的所有域名列表。|
|[ListUserCustomLogConfig](/cn.zh-CN/新版API参考/日志信息类接口/获取自定义日志配置ID.md)|调用ListUserCustomLogConfig获取用户下所有自定义日志配置信息。|
|[DescribeCustomLogConfig](/cn.zh-CN/新版API参考/日志信息类接口/获取自定义日志配置信息.md)|调用DescribeCustomLogConfig根据configId查询自定义日志配置详细信息。|

## 刷新预热类接口

|API|描述|
|---|--|
|[PushObjectCache](/cn.zh-CN/新版API参考/刷新预热类接口/预热源站内容到缓存节点.md)|调用PushObjectCache将源站的内容主动预热到L2 Cache节点上，您首次访问可直接命中缓存，缓解源站压力。|
|[DescribeRefreshQuota](/cn.zh-CN/新版API参考/刷新预热类接口/获取刷新预热的配额信息.md)|DescribeRefreshQuota查询当天URL刷新、目录刷新、预热及封禁的最大限制数量和剩余量。|
|[DescribeRefreshTasks](/cn.zh-CN/新版API参考/刷新预热类接口/获取刷新预热任务信息.md)|调用DescribeRefreshTasks查询刷新、预热状态是否在全网生效。|
|[RefreshObjectCaches](/cn.zh-CN/新版API参考/刷新预热类接口/刷新节点上的文件内容.md)|调用RefreshObjectCaches刷新节点上的文件内容。被刷新的文件缓存将立即失效，新的请求将回源获取最新的文件，支持URL批量刷新。|

## 服务类接口

|API|描述|
|---|--|
|[OpenCdnService](/cn.zh-CN/新版API参考/服务类接口/开通CDN服务.md)|调用OpenCdnService开通CDN服务。只有开通服务后，才能进行域名操作。|
|[DescribeCdnService](/cn.zh-CN/新版API参考/服务类接口/获取CDN服务状态.md)|调用DescribeCdnService查询CDN服务状态。包括：当前计费类型、服务开通时间、下次生效的计费类型、当前业务状态等。|
|[DescribeCdnUserResourcePackage](/cn.zh-CN/新版API参考/服务类接口/获取CDN用户流量包信息.md)|调用DescribeCdnUserResourcePackage查询CDN用户当前流量包。|
|[DescribeCdnUserQuota](/cn.zh-CN/新版API参考/服务类接口/获取用户资源使用信息.md)|调用DescribeCdnUserQuota查询用户资源上限及已使用情况。|

## 证书类接口

|API|描述|
|---|--|
|[CreateCdnCertificateSigningRequest](/cn.zh-CN/新版API参考/证书类接口/创建证书签名请求文件.md)|调用CreateCdnCertificateSigningRequest创建 CSR（证书签名请求）文件。|
|[DescribeDomainCertificateInfo](/cn.zh-CN/新版API参考/证书类接口/获取加速域名的证书信息.md)|调用DescribeDomainCertificateInfo获取指定加速域名证书信息。|
|[SetDomainServerCertificate](/cn.zh-CN/新版API参考/证书类接口/设置加速域名的证书信息.md)|调用SetDomainServerCertificate设置指定域名下证书功能是否启用及修改证书信息。|
|[SetCdnDomainCSRCertificate](/cn.zh-CN/新版API参考/证书类接口/设置加速域名的证书信息.md)|调用SetCdnDomainCSRCertificate设置指定域名下的HTTPS证书。|
|[DescribeCdnDomainByCertificate](/cn.zh-CN/新版API参考/证书类接口/获取证书信息对应加速域名.md)|调用DescribeCdnDomainByCertificate根据证书信息获取加速域名。|
|[DescribeCdnCertificateDetail](/cn.zh-CN/新版API参考/证书类接口/获取CDN证书的详细信息.md)|调用DescribeCdnCertificateDetail查询CDN证书详细信息。|
|[DescribeCdnCertificateList](/cn.zh-CN/新版API参考/证书类接口/获取证书列表信息.md)|调用DescribeCdnCertificateList获取证书列表信息。|
|[DescribeCertificateInfoByID](/cn.zh-CN/新版API参考/证书类接口/获取证书ID对应的证书信息.md)|调用DescribeCertificateInfoByID获取指定证书信息。|
|[BatchSetCdnDomainServerCertificate](/cn.zh-CN/新版API参考/证书类接口/批量设置加速域名证书信息.md)|调用BatchSetCdnDomainServerCertificate批量设置域名下证书功能是否启用及修改证书信息。|
|[DescribeCdnHttpsDomainList](/cn.zh-CN/新版API参考/证书类接口/获取用户所有证书信息.md)|调用DescribeCdnHttpsDomainList获取用户所有证书信息。|

## 用量查询类接口

|API|描述|
|---|--|
|[DescribeUserUsageDataExportTask](/cn.zh-CN/新版API参考/用量查询类接口/获取用量数据导出任务信息.md)|调用DescribeUserUsageDataExportTask查询用户最近三个月的用量导出任务信息。|
|[CreateUserUsageDataExportTask](/cn.zh-CN/新版API参考/用量查询类接口/创建历史用量数据导出任务.md)|调用CreateUserUsageDataExportTask创建账号历史用量数据导出任务，将历史用量生成PDF文件用于下载。|
|[CreateUsageDetailDataExportTask](/cn.zh-CN/新版API参考/用量查询类接口/创建用量数据导出任务.md)|调用CreateUsageDetailDataExportTask创建用量详细数据导出任务，将详细用量生成Excel文件用于下载。|
|[DescribeUserUsageDetailDataExportTask](/cn.zh-CN/新版API参考/用量查询类接口/获取用量明细导出任务信息.md)|调用DescribeUserUsageDetailDataExportTask查询您账户下单个或多个域名5分钟明细数据的导出任务。|
|[DescribeDomainUsageData](/cn.zh-CN/新版API参考/用量查询类接口/获取特定区域的用量数据.md)|调用DescribeDomainUsageData查询域名在特定计费区域的用量数据。|
|[DeleteUserUsageDataExportTask](/cn.zh-CN/新版API参考/用量查询类接口/删除历史用量数据导出任务.md)|调用DeleteUserUsageDataExportTask删除账号历史用量数据导出任务。|
|[DeleteUsageDetailDataExportTask](/cn.zh-CN/新版API参考/用量查询类接口/删除用户用量数据导出任务.md)|调用DeleteUsageDetailDataExportTask删除用量详细数据导出任务。|

## 标签类接口

|API|描述|
|---|--|
|[DescribeTagResources](/cn.zh-CN/新版API参考/标签类接口/获取资源对应的标签.md)|调用DescribeTagResources查询资源对应的标签。|
|[DescribeUserTags](/cn.zh-CN/新版API参考/标签类接口/获取用户标签.md)|调用DescribeUserTags查询用户标签。|
|[UntagResources](/cn.zh-CN/新版API参考/标签类接口/删除资源标签.md)|调用UntagResources删除资源标签。|
|[TagResources](/cn.zh-CN/新版API参考/标签类接口/添加资源标签.md)|调用TagResources添加资源标签。|

## 辅助工具类接口

|API|描述|
|---|--|
|[DescribeIpInfo](/cn.zh-CN/新版API参考/辅助工具类接口/验证IP是否为CDN节点.md)|调用DescribeIpInfo验证指定的IP是否为阿里云CDN节点的IP地址。|
|[CreateIllegalUrlExportTask](/cn.zh-CN/新版API参考/日志信息类接口/创建违规URL导出任务.md)|调用CreateIllegalUrlExportTask提交违规URL导出任务。|
|[DescribeIllegalUrlExportTask]()|调用DescribeIllegalUrlExportTask查询违规URL导出任务.。|

