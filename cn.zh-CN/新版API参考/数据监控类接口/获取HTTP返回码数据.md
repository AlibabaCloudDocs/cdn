# 获取HTTP返回码数据

调用DescribeDomainHttpCodeData获取加速域名HTTP返回码的总数和占比数据，支持获取最近90天的数据。

**说明：**

-   如果您不指定**StartTime**和**EndTime**，该接口返回过去24小时的数据；指定**StartTime**和**EndTime**，返回起止时间的数据。
-   您可以查询批量域名的数据，多个域名用英文逗号（,）分隔。
-   该接口的计算粒度为5分钟。
-   单用户调用频率：100次/秒。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeDomainHttpCodeData&type=RPC&version=2018-05-10)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeDomainHttpCodeData|操作接口名，系统规定参数。取值：**DescribeDomainHttpCodeData**。 |
|DomainName|String|否|test.test.com|加速域名，多个域名用英文逗号（,）分隔。

 默认查询所有加速域名。 |
|StartTime|String|否|2021-06-29T05:30:00Z|获取数据起始时间点。日期格式按照ISO8601表示法，并使用UTC时间，格式为yyyy-MM-ddTHH:mm:ssZ。 |
|EndTime|String|否|2021-06-29T05:45:00Z|获取数据结束时间点。日期格式按照ISO8601表示法，并使用UTC时间，格式为yyyy-MM-ddTHH:mm:ssZ。

 结束时间需大于起始时间。 |
|Interval|String|否|300|查询数据的时间粒度，单位：秒。根据您指定**StartTime**和**EndTime**两者的时间跨度，该参数取值如下：

 -   3天以内（不包含3天整）支持**300**、**3600**、 **86400**，如果不传该参数，默认值为**300**。
-   3-31天（不包含31天整）支持**3600**和**86400**，如果不传该参数，默认值为**3600**。
-   31天及以上支持**86400**，如果不传该参数，默认值为**86400**。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|300|时间间隔。 |
|DomainName|String|test.test.com|加速域名。 |
|EndTime|String|2021-06-29T05:45:00Z|结束时间。 |
|HttpCodeData|Array of UsageData| |每个时间间隔的HTTP返回码占比数据。 |
|UsageData| | | |
|TimeStamp|String|2021-06-29T05:40:00Z|时间片起始时刻。 |
|Value|Array of CodeProportionData| |各返回码占比使用数据列表。 |
|CodeProportionData| | | |
|Code|String|200|HTTP返回码。 |
|Count|String|300|总数。 |
|Proportion|String|66.046511627907|占比使用数据。 |
|RequestId|String|BC858082-736F-4A25-867B-E5B67C85ACF7|请求ID。 |
|StartTime|String|2021-06-29T05:30:00Z|开始时间。 |

## 示例

请求示例

```
http(s)://cdn.aliyuncs.com/?Action=DescribeDomainHttpCodeData
&DomainName="test.com,abc.com"
&StartTime=2021-06-29T05:30:00Z
&EndTime=2021-06-29T05:45:00Z
&<公共请求参数>
```

正常返回示例

`XML`格式

```
<RequestId>BC858082-736F-4A25-867B-E5B67C85ACF7</RequestId>
<EndTime>2021-06-29T05:45:00Z</EndTime>
<DomainName>test.test.com</DomainName>
<DataInterval>300</DataInterval>
<StartTime>2021-06-29T05:30:00Z</StartTime>
<HttpCodeData>
    <UsageData>
        <Value>
            <CodeProportionData>
                <Proportion>64.26332288401254</Proportion>
                <Count>205</Count>
                <Code>200</Code>
            </CodeProportionData>
            <CodeProportionData>
                <Proportion>22.570532915360502</Proportion>
                <Count>72</Count>
                <Code>403</Code>
            </CodeProportionData>
            <CodeProportionData>
                <Proportion>10.344827586206897</Proportion>
                <Count>33</Count>
                <Code>499</Code>
            </CodeProportionData>
            <CodeProportionData>
                <Proportion>2.8213166144200628</Proportion>
                <Count>9</Count>
                <Code>504</Code>
            </CodeProportionData>
        </Value>
        <TimeStamp>2021-06-29T05:30:00Z</TimeStamp>
    </UsageData>
    <UsageData>
        <Value>
            <CodeProportionData>
                <Proportion>66.96969696969697</Proportion>
                <Count>221</Count>
                <Code>200</Code>
            </CodeProportionData>
            <CodeProportionData>
                <Proportion>18.787878787878785</Proportion>
                <Count>62</Count>
                <Code>403</Code>
            </CodeProportionData>
            <CodeProportionData>
                <Proportion>12.121212121212121</Proportion>
                <Count>40</Count>
                <Code>499</Code>
            </CodeProportionData>
            <CodeProportionData>
                <Proportion>2.1212121212121215</Proportion>
                <Count>7</Count>
                <Code>504</Code>
            </CodeProportionData>
        </Value>
        <TimeStamp>2021-06-29T05:35:00Z</TimeStamp>
    </UsageData>
    <UsageData>
        <Value>
            <CodeProportionData>
                <Proportion>79.6976241900648</Proportion>
                <Count>369</Count>
                <Code>200</Code>
            </CodeProportionData>
            <CodeProportionData>
                <Proportion>15.118790496760258</Proportion>
                <Count>70</Count>
                <Code>403</Code>
            </CodeProportionData>
            <CodeProportionData>
                <Proportion>4.535637149028078</Proportion>
                <Count>21</Count>
                <Code>499</Code>
            </CodeProportionData>
            <CodeProportionData>
                <Proportion>0.21598272138228944</Proportion>
                <Count>1</Count>
                <Code>502</Code>
            </CodeProportionData>
            <CodeProportionData>
                <Proportion>0.4319654427645789</Proportion>
                <Count>2</Count>
                <Code>504</Code>
            </CodeProportionData>
        </Value>
        <TimeStamp>2021-06-29T05:40:00Z</TimeStamp>
    </UsageData>
</HttpCodeData>
```

`JSON`格式

```
{
  "RequestId": "BC858082-736F-4A25-867B-E5B67C85ACF7",
  "EndTime": "2021-06-29T05:45:00Z",
  "DomainName": "test.test.com",
  "DataInterval": 300,
  "StartTime": "2021-06-29T05:30:00Z",
  "HttpCodeData": {
    "UsageData": [
      {
        "Value": {
          "CodeProportionData": [
            {
              "Proportion": 64.26332288401254,
              "Count": 205,
              "Code": "200"
            },
            {
              "Proportion": 22.570532915360502,
              "Count": 72,
              "Code": "403"
            },
            {
              "Proportion": 10.344827586206897,
              "Count": 33,
              "Code": "499"
            },
            {
              "Proportion": 2.8213166144200628,
              "Count": 9,
              "Code": "504"
            }
          ]
        },
        "TimeStamp": "2021-06-29T05:30:00Z"
      },
      {
        "Value": {
          "CodeProportionData": [
            {
              "Proportion": 66.96969696969697,
              "Count": 221,
              "Code": "200"
            },
            {
              "Proportion": 18.787878787878785,
              "Count": 62,
              "Code": "403"
            },
            {
              "Proportion": 12.121212121212121,
              "Count": 40,
              "Code": "499"
            },
            {
              "Proportion": 2.1212121212121215,
              "Count": 7,
              "Code": "504"
            }
          ]
        },
        "TimeStamp": "2021-06-29T05:35:00Z"
      },
      {
        "Value": {
          "CodeProportionData": [
            {
              "Proportion": 79.6976241900648,
              "Count": 369,
              "Code": "200"
            },
            {
              "Proportion": 15.118790496760258,
              "Count": 70,
              "Code": "403"
            },
            {
              "Proportion": 4.535637149028078,
              "Count": 21,
              "Code": "499"
            },
            {
              "Proportion": 0.21598272138228944,
              "Count": 1,
              "Code": "502"
            },
            {
              "Proportion": 0.4319654427645789,
              "Count": 2,
              "Code": "504"
            }
          ]
        },
        "TimeStamp": "2021-06-29T05:40:00Z"
      }
    ]
  }
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

