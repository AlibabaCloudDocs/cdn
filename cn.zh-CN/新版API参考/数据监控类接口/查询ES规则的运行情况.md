# 查询ES规则的运行情况

调用DescribeEsExecuteData查询ES规则的运行情况。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeEsExecuteData&type=RPC&version=2018-05-10)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeEsExecuteData|系统规定参数。取值：**DescribeEsExecuteData**。 |
|EndTime|String|是|2021-02-18T20:00:00Z|获取数据的结束时间点。日期格式按照ISO8601表示法，并使用UTC时间表示，格式为yyyy-MM-ddTHH:mm:ssZ。

 **说明：** 结束时间需大于起始时间。 |
|RuleId|String|是|212896\*\*|规则ID。您可以调用[DescribeCdnDomainConfigs](~~90924~~)接口获取规则ID。 |
|StartTime|String|是|2021-02-17T20:00:00Z|获取数据的起始时间点。日期格式按照ISO8601表示法，并使用UTC时间表示，格式为yyyy-MM-ddTHH:mm:ssZ。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|Contents|Array of Content| |ES规则内容。 |
|Columns|List|time,Exception|ES规则运行情况图表的列名和时间。 |
|Name|String|Exception|ES规则运行情况图表的表名。 |
|Points|List|2021-02-18T19:05:00Z,8|图表对应列的数值和时间。 |
|RequestId|String|99D61AB3-6164-4CF2-A0DE-129C9B07618B|请求ID。 |

## 示例

请求示例

```
http(s)://cdn.aliyuncs.com/?Action=DescribeEsExecuteData
&EndTime=2021-02-18T20:00:00Z
&RuleId=212896**
&StartTime=2021-02-17T20:00:00Z
&<公共请求参数>
```

正常返回示例

`XML`格式

```
<DescribeEsExecuteDataResponse>
<Contents>
    <Columns>time</Columns>
    <Columns>Exception</Columns>
    <Name>Exception</Name>
    <Points>
        <0>2021-02-18T19:07:00Z</0>
        <1>6</1>
    </Points>
    <Points>
        <0>2021-02-18T19:06:00Z</0>
        <1>6</1>
    </Points>
    <Points>
        <0>2021-02-18T19:05:00Z</0>
        <1>8</1>
    </Points>
</Contents>
<Contents>
    <Columns>time</Columns>
    <Columns>ExecutedAndHit</Columns>
    <Name>ExecutedAndHit</Name>
    <Points>
        <0>2021-02-18T19:07:00Z</0>
        <1>0</1>
    </Points>
    <Points>
        <0>2021-02-18T19:06:00Z</0>
        <1>0</1>
    </Points>
    <Points>
        <0>2021-02-18T19:05:00Z</0>
        <1>0</1>
    </Points>
</Contents>
<RequestId>99D61AB3-6164-4CF2-A0DE-129C9B07618B</RequestId>
</DescribeEsExecuteDataResponse>
```

`JSON`格式

```
{
    "Contents": [
        {
            "Columns": [
                "time",
                "Exception"
            ],
            "Name": "Exception",
            "Points": [
                [
                    "2021-02-18T19:07:00Z",
                    6
                ],
                [
                    "2021-02-18T19:06:00Z",
                    6
                ],
                [
                    "2021-02-18T19:05:00Z",
                    8
                ]
            ]
        },
        {
            "Columns": [
                "time",
                "ExecutedAndHit"
            ],
            "Name": "ExecutedAndHit",
            "Points": [
                [
                    "2021-02-18T19:07:00Z",
                    0
                ],
                [
                    "2021-02-18T19:06:00Z",
                    0
                ],
                [
                    "2021-02-18T19:05:00Z",
                    0
                ]
            ]
        }
    ],
"RequestId": "99D61AB3-6164-4CF2-A0DE-129C9B07618B"    
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/Cdn)查看更多错误码。

