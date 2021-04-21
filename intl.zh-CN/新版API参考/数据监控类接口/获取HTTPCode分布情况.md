# 获取HTTPCode分布情况

调用DescribeDomainHttpCodeDataByLayer获取HTTPCode分布情况。

-   不指定**StartTime**和**EndTime**时，该接口默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   支持批量域名查询，多个域名用英文逗号（,）分隔。
-   最多可获取最近90天的数据。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainHttpCodeDataByLayer&type=RPC&version=2018-05-10)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainHttpCodeDataByLayer|系统规定参数。取值：**DescribeDomainHttpCodeDataByLayer**。 |
|DomainName|String|否|example.com|需要查询的加速域名。支持批量域名查询，多个域名用英文逗号（,）分隔。

 若参数为空，默认返回所有加速域名合并后的数据。 |
|StartTime|String|否|2020-07-05T22:00:00Z|获取数据起始时间。日期格式按照ISO8601表示法，并使用UTC时间，格式为yyyy-MM-ddTHH:mm:ssZ。

 最小数据粒度为5分钟。

 若该参数为空，默认读取过去24小时数据。 |
|EndTime|String|否|2020-07-06T22:00:00Z|获取数据结束时间。日期格式按照ISO8601表示法，并使用UTC时间，格式为yyyy-MM-ddTHH:mm:ssZ。

 结束时间需大于起始时间。 |
|Interval|String|否|300|查询数据的时间粒度，支持300秒，3600秒和86400秒。

 该参数使用限制如下：

 -   3天以内（不包含3天整）：支持**300**秒、**3600**秒、**86400**秒。
-   3~31天（不包含31天整）：支持**3600**秒和**86400**秒。
-   31天及以上：支持**86400**秒。

 不传值和传的值不支持时，使用默认值。 |
|LocationNameEn|String|否|hangzhou|地域英文名，通过[DescribeCdnRegionAndIsp](~~91077~~)接口获得。

 不传值代表所有区域。 |
|IspNameEn|String|否|telecom|运营商英文名，通过[DescribeCdnRegionAndIsp](~~91077~~)接口获得。

 不传值代表所有运营商。 |
|Layer|String|否|all|查询维度，可选网络层（**IPv4**、**IPv6**）或应用层（**http**、**https**、**quic**）或 **all**。

 默认为**all**。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|300|每条记录的时间间隔，单位：秒。 |
|HttpCodeDataInterval|Array of DataModule| |每个时间间隔的HTTPCode分布情况，单位：个。 |
|DataModule| | | |
|TimeStamp|String|2015-12-10T20:35:00Z|时间片起始时刻。 |
|TotalValue|String|110|总响应次数。 |
|Value|String|"Value": \{ "200": 10, "206": 100\}|每个HttpCode对应的响应次数。 |
|RequestId|String|BEA5625F-8FCF-48F4-851B-CA63946DA664|请求ID。 |

## 示例

请求示例

```
http(s)://cdn.aliyuncs.com/?Action=DescribeDomainHttpCodeDataByLayer
&DomainName=example.com
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T21:00:00Z
&<公共请求参数>
```

正常返回示例

`XML`格式

```
<DescribeDomainHttpCodeDataByLayerResponse>
<HttpCodeDataInterval>
    <DataModule>
        <TimeStamp>2015-12-10T21:00:00Z</TimeStamp>
        <Value>
            <200>10</200>
            <206>100</206>
        </Value>
        <TotalValue>110</TotalValue>
    </DataModule>
    <DataModule>
        <TimeStamp>2015-12-10T20:35:00Z</TimeStamp>
        <Value>
            <200>12</200>
            <206>120</206>
        </Value>
        <TotalValue>132</TotalValue>
    </DataModule>
</HttpCodeDataInterval>
<DataInterval>300</DataInterval>
<RequestId>BEA5625F-8FCF-48F4-851B-CA63946DA664</RequestId>
</DescribeDomainHttpCodeDataByLayerResponse>
```

`JSON`格式

```
{
    "HttpCodeDataInterval": {
        "DataModule": [
            {
                "TimeStamp": "2015-12-10T21:00:00Z",
                "Value": {
                    "200": 10,
                    "206": 100
                },
                "TotalValue": 110
            },
            {
                "TimeStamp": "2015-12-10T20:35:00Z",
                "Value": {
                    "200": 12,
                    "206": 120
                },
                "TotalValue": 132
            }
        ]
    },
    "DataInterval": "300",
    "RequestId": "BEA5625F-8FCF-48F4-851B-CA63946DA664"
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/Cdn)查看更多错误码。

