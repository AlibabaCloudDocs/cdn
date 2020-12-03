# 获取回源热门URL

调用DescribeDomainSrcTopUrlVisit获取加速域名的回源热门URL。

**说明：** 查询的时间粒度为5分钟。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainSrcTopUrlVisit&type=RPC&version=2018-05-10)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDomainSrcTopUrlVisit|操作接口名，系统规定参数。取值：**DescribeDomainSrcTopUrlVisit**。 |
|DomainName|String|是|example.com|加速域名，多个域名用英文逗号（,）分隔。 |
|StartTime|String|否|2018-10-03T16:00:00Z|获取数据起始时间点。日期格式按照ISO8601表示法，并使用UTC时间，格式为yyyy-MM-ddTHH:mm:ssZ。

 **说明：** 如果不指定StartTime，默认读取前一天的数据。 |
|EndTime|String|否|2018-10-03T20:00:00Z|获取数据结束时间点。日期格式按照ISO8601表示法，并使用UTC时间，格式为yyyy-MM-ddTHH:mm:ssZ。

 **说明：** 结束时间需大于起始时间，并且结束时间和开始时间相差不超过7天。 |
|SortBy|String|否|pv|排序方式，默认值为**pv**。取值：

 -   **traf**：流量。
-   **pv**：访问量。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|AllUrlList|Array of UrlList| |全部热门URL列表。 |
|UrlList| | | |
|Flow|String|460486880|流量。单位：byte。 |
|FlowProportion|Float|0.35|流量占比。 |
|UrlDetail|String|http://example.com/nn\_live/nn\_x64/a0.m3u8|完整的URL地址。 |
|VisitData|String|161673|访问次数。 |
|VisitProportion|Float|0.35|访问占比。 |
|DomainName|String|example.com|加速域名信息。 |
|RequestId|String|64D28B53-5902-409B-94F6-FD46680144FE|请求ID。 |
|StartTime|String|2018-10-03T16:00:00Z|查询指定日期。 |
|Url200List|Array of UrlList| |返回为2xx的URL列表。 |
|UrlList| | | |
|Flow|String|460486880|流量。单位：byte。 |
|FlowProportion|Float|0.35|流量占比。 |
|UrlDetail|String|http://example.com/nn\_live/nn\_x64/a0.m3u8|完整的URL地址。 |
|VisitData|String|161673|访问次数。 |
|VisitProportion|Float|0.35|访问占比。 |
|Url300List|Array of UrlList| |返回为3xx的URL列表。 |
|UrlList| | | |
|Flow|String|460486880|流量。单位：byte。 |
|FlowProportion|Float|0.35|流量占比。 |
|UrlDetail|String|http://example.com/nn\_live/nn\_x64/a0.m3u8|完整的URL地址。 |
|VisitData|String|161673|访问次数。 |
|VisitProportion|Float|0.35|访问占比。 |
|Url400List|Array of UrlList| |返回为4xx的URL列表。 |
|UrlList| | | |
|Flow|String|460486880|流量。单位：byte。 |
|FlowProportion|Float|0.35|流量占比。 |
|UrlDetail|String|http://example.com/nn\_live/nn\_x64/a0.m3u8|完整的URL地址。 |
|VisitData|String|161673|访问次数。 |
|VisitProportion|Float|0.35|访问占比。 |
|Url500List|Array of UrlList| |返回为5xx的URL列表。 |
|UrlList| | | |
|Flow|String|460486880|流量，单位：byte。 |
|FlowProportion|Float|0.35|流量占比。 |
|UrlDetail|String|http://example.com/nn\_live/nn\_x64/a0.m3u8|完整的URL地址。 |
|VisitData|String|161673|访问次数。 |
|VisitProportion|Float|0.35|访问占比。 |

## 示例

请求示例

```
http://cdn.aliyuncs.com?Action=DescribeDomainSrcTopUrlVisit
&DomainName=example.com
&StartTime=2018-10-03T16:00:00Z
&EndTime=2018-10-03T20:00:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeDomainSrcTopUrlVisitResponse>
  <AllUrlList>
        <UrlList>
              <VisitData>161673</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/a0.m3u8</UrlDetail>
              <VisitProportion>0.35</VisitProportion>
              <Flow>460486880</Flow>
              <FlowProportion>0.35</FlowProportion>
        </UrlList>
        <UrlList>
              <VisitData>37</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/ZXg9MQ,,/HNJSMPP360.ts</UrlDetail>
              <VisitProportion>0.35</VisitProportion>
              <Flow>460486880</Flow>
              <FlowProportion>0.35</FlowProportion>
        </UrlList>
  </AllUrlList>
  <Url300List>
        <UrlList>
              <VisitData>161673</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8</UrlDetail>
              <VisitProportion>0.35</VisitProportion>
              <Flow>460486880</Flow>
              <FlowProportion>0.35</FlowProportion>
        </UrlList>
        <UrlList>
              <VisitData>3</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/aWQ9SE5KU01QUDZXg9MQ,,/HNJSMPP360.ts</UrlDetail>
              <VisitProportion>0.35</VisitProportion>
              <Flow>460486880</Flow>
              <FlowProportion>0.35</FlowProportion>
        </UrlList>
  </Url300List>
  <Url400List>
        <UrlList>
              <VisitData>1884</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/aWQ9SE5KU01QUhb,,/HNJSMPP360.m3u8</UrlDetail>
              <VisitProportion>0.35</VisitProportion>
              <Flow>460486880</Flow>
              <FlowProportion>0.35</FlowProportion>
        </UrlList>
        <UrlList>
              <VisitData>1</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/aWQ9SEEwODgm,/HNJSMPP360.ts</UrlDetail>
              <VisitProportion>0.35</VisitProportion>
              <Flow>460486880</Flow>
              <FlowProportion>0.35</FlowProportion>
        </UrlList>
  </Url400List>
  <RequestId>64D28B53-5902-409B-94F6-FD46680144FE</RequestId>
  <DomainName>example.com</DomainName>
  <Url200List>
        <UrlList>
              <VisitData>161673</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/aWQ9SE5KU0bGxfcG,,/HNJSMPP360.m3u8</UrlDetail>
              <VisitProportion>0.35</VisitProportion>
              <Flow>460486880</Flow>
              <FlowProportion>0.35</FlowProportion>
        </UrlList>
        <UrlList>
              <VisitData>3</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/aWQ9SE5KDMlPTIwMTQ,,/HNJSMPP360.ts</UrlDetail>
              <VisitProportion>0.35</VisitProportion>
              <Flow>460486880</Flow>
              <FlowProportion>0.35</FlowProportion>
        </UrlList>
  </Url200List>
  <StartTime>2018-10-03T16:00:00Z</StartTime>
  <Url500List>
        <UrlList>
              <VisitData>161673</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8</UrlDetail>
              <VisitProportion>0.35</VisitProportion>
              <Flow>460486880</Flow>
              <FlowProportion>0.35</FlowProportion>
        </UrlList>
        <UrlList>
              <VisitData>3</VisitData>
              <UrlDetail>http://example.com/nn_live/nn_x64/aWQ9SE5KU01QUDZXg9MQ,,/HNJSMPP360.ts</UrlDetail>
              <VisitProportion>0.35</VisitProportion>
              <Flow>460486880</Flow>
              <FlowProportion>0.35</FlowProportion>
        </UrlList>
  </Url500List>
</DescribeDomainSrcTopUrlVisitResponse>
```

`JSON` 格式

```
{
    "AllUrlList": {
        "UrlList": [
            {
                "VisitData": "161673",
                "UrlDetail": "http://example.com/nn_live/nn_x64/a0.m3u8",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            },
            {
                "VisitData": "37",
                "UrlDetail": "http://example.com/nn_live/nn_x64/ZXg9MQ,,/HNJSMPP360.ts",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            }                      
        ]
    },
    "Url300List": {
        "UrlList": [
            {
                "VisitData": "161673",
                "UrlDetail": "http://example.com/nn_live/nn_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            },
            {
                "VisitData": "3",
                "UrlDetail": "http://example.com/nn_live/nn_x64/aWQ9SE5KU01QUDZXg9MQ,,/HNJSMPP360.ts",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            }
        ]
    },
    "Url400List": {
        "UrlList": [
            {
                "VisitData": "1884",
                "UrlDetail": "http://example.com/nn_live/nn_x64/aWQ9SE5KU01QUhb,,/HNJSMPP360.m3u8",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            },
            {
                "VisitData": "1",
                "UrlDetail": "http://example.com/nn_live/nn_x64/aWQ9SEEwODgm,/HNJSMPP360.ts",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            }           
        ]
    },
    "RequestId": "64D28B53-5902-409B-94F6-FD46680144FE",
    "DomainName": "example.com",
    "Url200List": {
        "UrlList": [
            {
                "VisitData": "161673",
                "UrlDetail": "http://example.com/nn_live/nn_x64/aWQ9SE5KU0bGxfcG,,/HNJSMPP360.m3u8",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            },
            {
                "VisitData": "3",
                "UrlDetail": "http://example.com/nn_live/nn_x64/aWQ9SE5KDMlPTIwMTQ,,/HNJSMPP360.ts",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            }
        ]
    },
    "StartTime": "2018-10-03T16:00:00Z",
    "Url500List": {
        "UrlList": [
            {
                "VisitData": "161673",
                "UrlDetail": "http://example.com/nn_live/nn_x64/aWQ9SE5KU0GNfbGl2ZQ,,/HNJSMPP360.m3u8",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            },           
            {
                "VisitData": "3",
                "UrlDetail": "http://example.com/nn_live/nn_x64/aWQ9SE5KU01QUDZXg9MQ,,/HNJSMPP360.ts",
                "VisitProportion": 0.35,
                "Flow": "460486880",
                "FlowProportion": 0.35
            }
        ]
    }
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|起始时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|结束时间格式错误。日期格式请参考所调用API的帮助文档说明。|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|开始时间设置错误，请检查更新后重试。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Cdn)查看更多错误码。

