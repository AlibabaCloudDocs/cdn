# DescribeDomainUsageData {#reference4231 .reference}

调用DescribeDomainUsageData查询域名在特定计费区域的用量数据。

**说明：** 

-   支持批量域名查询，多个域名用`,`分隔，最多可以一次查询100个域名。如果为空则返回账号下所有域名的数据。
-   用量数据包括流量、带宽和请求数三类，单位分别为byte、bps和次。

## 请求参数 { .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。取值：DescribeDomainUsageData。|
|DomainName|String|否| -   若参数为空，默认返回所有加速域名合并后数据。
-   可输入需要查询的加速域名，支持批量域名查询，多个域名用`,`分隔。

 |
|StartTime|String|是|获取数据起始时间点。日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。最小数据粒度为5分钟。|
|EndTime|String|是|结束时间需大于起始时间，不能相差超过31天。获日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。|
|DataProtocol|String|否|需要获取的数据的协议。包括https、http和all。默认为all。|
|Type|String|否|需要获取的用量类型。默认为all。 -   static：静态。
-   dynamic：动态。
-   all：全部。

 |
|Area|String|否|区域代号。包括：CN、OverSeas、AP1、AP2、AP3、NA、SA、EU、MEAA、all。不传为CN：中国大陆。|
|Field|String|是|请求的数据类型。包括：bps、traf、acc，其中acc不支持area。|
|Interval|String|否|强制指定获取指定时间粒度的数据。支持300、3600或86400，分别代表5分钟、1小时和1天。 **说明：** 

-   如果指定Interval为300，最长可查询近半年的数据，单次查询时间跨度最长为3天。
-   如果指定Interval为3600或86400，最长可查询近1年的数据。
-   如果不指定Interval，单次查询跨度最长为1个月。
    -   当查询时间为1-3天时，数据按小时粒度返回。
    -   当查询时间大于4天时，数据按天粒度返回。

 |

## 参数组合说明 {#section_zk4_tzf_2hb .section}

计费数据和参数取值的对应关系如下表，具体调用方法参见请求示例。

|计费数据|DataProtocol参数取值|Type参数取值|Field参数取值|Area参数取值|
|:---|:---------------|:-------|:--------|:-------|
|流量|all或不传|all或不传|traf|CN、OverSeas、AP1、AP2、AP3、NA、SA、EU、MEAA|
|带宽|all或不传|all或不传|bps|CN、OverSeas、AP1、AP2、AP3、NA、SA、EU、MEAA|
|静态HTTPS请求数|https|static|acc|all|
|动态HTTP请求数|http|dynamic|acc|all|
|动态HTTPS请求数|https|dynamic|acc|all|

## 返回参数 { .section}

|名称|类型|描述|
|:-|:-|:-|
|DomainName|String|加速域名信息。|
|DataInterval|String|每条记录的时间间隔，以秒为单位。|
|StartTime|DateTime|开始时间。|
|EndTime|DateTime|结束时间。|
|Type|String|用量类型。|
|Area|String|用量区域。|
|UsageDataPerInterval|UsageData\[\]|每个时间间隔的流量数据。|

## UsageData { .section}

|名称|类型|描述|
|:-|:-|:-|
|TimeStamp|String|时间片起始时刻。|
|PeakTime|String|Field为bps时，该值为峰值带宽时刻，否则值和TimeStamp相同。|
|Value|String|用量。|

## 示例 { .section}

请求示例

-   获取国内流量

    ```
    http://cdn.aliyuncs.com?Action=DescribeDomainUsageData&DomainName=example.com
    &StartTime=2015-12-10T20:00:00Z
    &EndTime=2015-12-10T22:00:00Z
    &Field=traf
    &Area=CN
    &<公共请求参数>
    ```

-   获取EU大区的带宽

    ```
    http://cdn.aliyuncs.com?Action=DescribeDomainUsageData&DomainName=example.com
    &StartTime=2015-12-10T20:00:00Z
    &EndTime=2015-12-10T22:00:00Z
    &Field=bps
    &Area=EU
    &<公共请求参数>
    ```

-   获取静态https请求数

    ```
    http://cdn.aliyuncs.com?Action=DescribeDomainUsageData&DomainName=example.com
    &StartTime=2015-12-10T20:00:00Z
    &EndTime=2015-12-10T22:00:00Z
    &Type=static
    &DataProtocol=https
    &Field=acc
    &Area=all
    &<公共请求参数>
    ```

-   获取动态http请求数

    ```
    http://cdn.aliyuncs.com?Action=DescribeDomainUsageData&DomainName=example.com
    &StartTime=2015-12-10T20:00:00Z
    &EndTime=2015-12-10T22:00:00Z
    &Type=dynamic
    &DataProtocol=http
    &Field=acc
    &Area=all
    &<公共请求参数>
    ```

-   获取动态https请求数

    ```
    http://cdn.aliyuncs.com?Action=DescribeDomainUsageData&DomainName=example.com
    &StartTime=2015-12-10T20:00:00Z
    &EndTime=2015-12-10T22:00:00Z
    &Type=dynamic
    &DataProtocol=https
    &Field=acc
    &Area=all
    &<公共请求参数>
    ```


正常返回示例

`JSON`格式

```
{
    "DomainName": "example.com",
    "DataInterval": "300",
    "UsageDataPerInterval": {
        "DataModule": [
            {
                "TimeStamp": "2015-12-10T20:00:00Z",
                "PeakTime": "2015-12-10T20:05:00Z",
                "Value": "423304182"
            },
            {
                "TimeStamp": "2015-12-10T21:00:00Z",
                "PeakTime": "2015-12-10T21:30:00Z",
                "Value": "454680793"
            }
        ]
    },
    "RequestId": "B955107D-E658-4E77-B913-E0AC3D31693E",
    "StartTime": "2015-12-10T20:00Z",
    "EndTime": "2015-12-10T21:00Z",
    "Area": "CN",
    "Type": "traf"
}
```

## 错误码 { .section}

|错误代码|错误信息|HTTP 状态码|描述|
|:---|:---|:-------|:-|
|Throttling|Request was denied due to request throttling.|503|请求被流量控制限制。|
|IllegalOperation|Illegal domain, operation is not permitted.|403|非法域名，无法操作。|
|OperationDenied|Your account does not open CDN service yet.|403|未开通CDN服务。|
|OperationDenied|Your CDN service is suspended.|403|CDN服务已被停止。|
|InvalidDomain.NotFound|The domain provided does not belong to you.|404|域名不存在或不属于当前用户。|
|InvalidDomain.Offline|The domain provided is offline.|404|域名已下线。|
|ServiceBusy|The specified Domain is configuring, please retry later.|403|域名正在配置中，请您稍后再试。|
|InvalidDomain.Configure\_failed|Failed to configure the provided domain.|500|域名配置失败。|
|InvalidParameter|Invalid Parameter.|400|参数错误。|
|InvalidParameterProduct|Invalid Parameter Product.|400|Product参数错误。|
|InvalidParameterArea|Invalid Parameter Area.|400|Area参数错误。|
|InvalidParameterField|Invalid Parameter Field.|400|Field参数错误。|
|InvalidParameterStartTime|Invalid Parameter StartTime.|400|StartTime参数错误。|
|InvalidParameterEndTime|Invalid Parameter EndTime.|400|EndTime参数错误。|
|InvalidTimeRange|StartTime and EndTime range should less than 1 month.|400|EndTime和StartTime差值不能超过31天。|
|InvalidParameterInterval|Invalid Parameter Interval.|400|Interval参数错误。|

