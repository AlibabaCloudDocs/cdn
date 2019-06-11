# DescribeUserUsageDetailDataExportTask {#reference1909 .reference}

调用DescribeUserUsageDetailDataExportTask查询您账户下单个或多个域名5分钟明细数据的导出任务。

**说明：** 该功能从2018年7月20日开始，最长可查询近1年的数据。

## 调试 {#section_hzc_tpt_ok7 .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeUserUsageDetailDataExportTask)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_ck0_vel_tqd .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。取值：DescribeUserUsageDetailDataExportTask。|
|PageSize|String|否| -   若参数为空，默认返回所有加速域名合并后数据。
-   可输入需要查询的加速域名支持批量域名查询，多个域名用逗号`,`分隔。

 |
|PageNumber|String|否|创建任务起始时间点，日期格式按照ISO8601表示法，并使用UTC时间。不写默认读取过去24小时数据。|

## 返回参数 {#section_dxm_wjw_ami .section}

|名称|类型|描述|
|:-|:-|:-|
|TotalCount|String|总记录数。|
|PageSize|String|每页记录数。|
|PageNumber|DateTime|当前页。|
|UsageDataPerPage|UsageData\[\]|每页的用量数据。|

UsageData

|名称|类型|描述|
|:-|:-|:-|
|StartTime|String|用量起始时刻。|
|EndTime|String|用量结束时间。|
|CreateTime|String|任务创建时间。|
|UpdateTime|String|任务最后更新时间。|
|TaskId|String|任务ID。|
|TaskName|String|任务名称。|
|Status|String|任务状态。|
|DownloadUrl|String|下载地址。|

## 示例 {#section_q2g_j3q_vul .section}

请求示例

``` {#codeblock_7ui_04d_bdf}
http://cdn.aliyuncs.com?Action=DescribeUserUsageDetailDataExportTask&DomainName=example.com
&PageSize=10
&PageNumber=1
&<公共请求参数>          
```

正常返回示例

`JSON`格式

``` {#codeblock_bhc_2fx_bqf}
{
    "TotalCount": "1",
    "PageSize": "10",
    "PageNumber": "1",
    "UsageDataPerPage": {
        "UsageData": [
            {
                "StartTime": "2017-12-10T00:00:00Z",
                "EndTime": "2017-12-11T00:00:00Z",
                "CreateTime": "2017-12-15T12:33:10Z",
                "ModifyTime": "2017-12-15T12:38:49Z",
                "TaskName":"测试任务",
                "TaskId":"34230590834"
                "Status": "Success",
                "DownloadUrl":"http://example.com/xxxx/xxxx.pdf",
                "UpdateTime": "2017-12-15T12:41:49Z"
            }
        ]
    },
    "RequestId": "B955107D-E658-4E77-B913-E0AC3D31693E"
}
```

## 错误码 {#section_rmo_0tr_e80 .section}

|错误代码|错误信息|HTTP 状态码|描述|
|:---|:---|:-------|:-|
|Throttling|Request was denied due to request throttling.|503|请求被流量控制限制。|
|IllegalOperation|Illegal domain, operation is not permitted.|403|非法域名，无法操作。|
|OperationDenied|Your account does not open Cdn service yet.|403|未开通Cdn服务。|
|OperationDenied|Your Cdn service is suspended.|403|Cdn服务已被停止。|
|InvalidParameter|Invalid Parameter.|400|参数错误。|
|InvalidParameterProduct|Invalid Parameter Product.|400|Product参数错误。|
|InvalidParameterArea|Invalid Parameter Area.|400|Area参数错误。|
|InvalidParameterField|Invalid Parameter Field.|400|Field参数错误。|
|InvalidParameterStartTime|Invalid Parameter StartTime.|400|StartTime参数错误。|
|InvalidParameterEndTime|Invalid Parameter EndTime.|400|EndTime参数错误。|
|InvalidTimeRange|StartTime and EndTime range should less than 1 month.|400|EndTime和StartTime差值不能超过31天。|

