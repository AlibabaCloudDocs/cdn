# DescribeUserUsageDataExportTask {#reference1729 .reference}

调用DescribeUserUsageDataExportTask列出用户最近三个月的用量导出任务信息。

## 调试 {#section_t3n_9kb_8rs .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeUserUsageDataExportTask)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_gfj_be8_o3l .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。取值：DescribeUserUsageDataExportTask。|
|PageSize|String|否| -   若参数为空，默认返回所有加速域名合并后数据。
-   可输入需要查询的加速域名。
-   支持批量域名查询，多个域名用逗号`,`分隔。

 |
|PageNumber|String|否|创建任务起始时间点，日期格式按照ISO8601表示法，并使用UTC时间。不写默认读取过去24小时数据。|

## 返回参数 {#section_k4c_454_s4w .section}

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
|Status|String|任务状态。|
|DownloadUrl|String|下载地址。|

## 示例 {#section_j2q_dmk_gze .section}

请求示例

``` {#codeblock_q83_28l_hy0}
http://cdn.aliyuncs.com?Action=DescribeUserUsageDataExportTask&DomainName=example.com
&PageSize=10
&PageNumber=1
&<公共请求参数>         
```

正常返回示例

`JSON`格式

``` {#codeblock_fwy_jud_j64}
{
  "RequestId": "A91BE91F-0B34-4CBF-8E0F-A2977E15AA52",
  "UsageDataPerPage": {
    "PageSize": 10,
    "TotalCount": 1,
    "PageNumber": 1,
    "Data": {
      "DataItem": [
        {
          "TaskId": 11,
          "UpdateTime": "2018-10-09T06:35:01Z",
          "DownloadUrl": "example.com",
          "UpdateTime": "2018-10-09T06:35:46Z",
          "CreateTime": "2018-10-09T06:33:38Z",
          "Status": "success"
          "TaskConfig": {
            "StartTime": "2018-07-31T16:00:00Z",
            "EndTime": "2018-08-31T15:59:59Z"
          },
        }
      ]
    }
  }
}
```

## 错误码 {#section_nu9_m5t_ynh .section}

|错误代码|描述|Http 状态码|语义|
|----|--|--------|--|
|Throttling|Request was denied due to request throttling.|503|请求被流量控制限制。|
|IllegalOperation|Illegal domain, operation is not permitted.|403|非法域名, 无法操作。|
|OperationDenied|Your account does not open Cdn service yet.|403|未开通Cdn服务。|
|OperationDenied|Your Cdn service is suspended.|403|Cdn服务已被停止。|
|InvalidParameter|Invalid Parameter.|400|参数错误。|
|InvalidParameterProduct|Invalid Parameter Product.|400|Product参数错误。|
|InvalidParameterArea|Invalid Parameter Area.|400|Area参数错误。|
|InvalidParameterField|Invalid Parameter Field.|400|Field参数错误。|
|InvalidParameterStartTime|Invalid Parameter StartTime.|400|StartTime参数错误。|
|InvalidParameterEndTime|Invalid Parameter EndTime.|400|EndTime参数错误。|
|InvalidTimeRange|StartTime and EndTime range should less than 1 month.|400|SndTime和StartTime差值不能超过31天。|

