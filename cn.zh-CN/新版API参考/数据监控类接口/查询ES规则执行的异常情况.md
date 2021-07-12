# 查询ES规则执行的异常情况

调用DescribeEsExceptionData查询ES规则执行的异常情况。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Cdn&api=DescribeEsExceptionData&type=RPC&version=2018-05-10)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeEsExceptionData|系统规定参数。取值：**DescribeEsExceptionData**。 |
|EndTime|String|是|2021-02-18T20:00:00Z|获取数据的结束时间点。日期格式按照ISO8601表示法，并使用UTC时间表示，格式为yyyy-MM-ddTHH:mm:ssZ。

 **说明：** 结束时间需大于起始时间。 |
|RuleId|String|是|212896\*\*|规则ID。您可以调用[DescribeCdnDomainConfigs](~~90924~~)接口获取规则ID。 |
|StartTime|String|是|2021-02-17T20:00:00Z|获取数据的起始时间点。日期格式按照ISO8601表示法，并使用UTC时间表示，格式为yyyy-MM-ddTHH:mm:ssZ。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|Contents|Array of Content| |ES执行异常情况的规则内容。 |
|Columns|List|time,401|ES规则执行异常情况图表的列名和时间。 |
|Name|String|401|ES规则执行异常情况图表的表名。 |
|Points|List|2021-02-18T19:05:00Z,0|图表对应列的数值和时间。 |
|RequestId|String|99D61AB3-6164-4CF2-A0DE-129C9B07618B|请求ID。 |

## 示例

请求示例

```
http(s)://cdn.aliyuncs.com/?Action=DescribeEsExceptionData
&EndTime=2021-02-18T20:00:00Z
&RuleId=212896**
&StartTime=2021-02-17T20:00:00Z
&<公共请求参数>
```

正常返回示例

`XML`格式

```
<DescribeEsExceptionDataResponse>
<content>
    <columns>time</columns>
    <columns>401</columns>
    <name>401</name>
    <points>
        <0>2021-02-18T19:07:00Z</0>
        <1>0</1>
    </points>
    <points>
        <0>2021-02-18T19:06:00Z</0>
        <1>0</1>
    </points>
    <points>
        <0>2021-02-18T19:05:00Z</0>
        <1>0</1>
    </points>
</content>
<content>
    <columns>time</columns>
    <columns>402</columns>
    <name>402</name>
    <points>
        <0>2021-02-18T19:07:00Z</0>
        <1>0</1>
    </points>
    <points>
        <0>2021-02-18T19:06:00Z</0>
        <1>0</1>
    </points>
    <points>
        <0>2021-02-18T19:05:00Z</0>
        <1>0</1>
    </points>
</content>
<content>
    <columns>time</columns>
    <columns>403</columns>
    <name>403</name>
    <points>
        <0>2021-02-18T19:07:00Z</0>
        <1>0</1>
    </points>
    <points>
        <0>2021-02-18T19:06:00Z</0>
        <1>0</1>
    </points>
    <points>
        <0>2021-02-18T19:05:00Z</0>
        <1>0</1>
    </points>
</content>
<content>
    <columns>time</columns>
    <columns>404</columns>
    <name>404</name>
    <points>
        <0>2021-02-18T19:07:00Z</0>
        <1>0</1>
    </points>
    <points>
        <0>2021-02-18T19:06:00Z</0>
        <1>0</1>
    </points>
    <points>
        <0>2021-02-18T19:05:00Z</0>
        <1>0</1>
    </points>
</content>
<content>
    <columns>time</columns>
    <columns>405</columns>
    <name>405</name>
    <points>
        <0>2021-02-18T19:07:00Z</0>
        <1>0</1>
    </points>
    <points>
        <0>2021-02-18T19:06:00Z</0>
        <1>0</1>
    </points>
    <points>
        <0>2021-02-18T19:05:00Z</0>
        <1>0</1>
    </points>
</content>
<content>
    <columns>time</columns>
    <columns>406</columns>
    <name>406</name>
    <points>
        <0>2021-02-18T19:07:00Z</0>
        <1>0</1>
    </points>
    <points>
        <0>2021-02-18T19:06:00Z</0>
        <1>0</1>
    </points>
    <points>
        <0>2021-02-18T19:05:00Z</0>
        <1>0</1>
    </points>
</content>
<content>
    <columns>time</columns>
    <columns>407</columns>
    <name>407</name>
    <points>
        <0>2021-02-18T19:07:00Z</0>
        <1>6</1>
    </points>
    <points>
        <0>2021-02-18T19:06:00Z</0>
        <1>6</1>
    </points>
    <points>
        <0>2021-02-18T19:05:00Z</0>
        <1>8</1>
    </points>
</content>
<content>
    <columns>time</columns>
    <columns>408</columns>
    <name>408</name>
    <points>
        <0>2021-02-18T19:07:00Z</0>
        <1>0</1>
    </points>
    <points>
        <0>2021-02-18T19:06:00Z</0>
        <1>0</1>
    </points>
    <points>
        <0>2021-02-18T19:05:00Z</0>
        <1>0</1>
    </points>
</content>
<content>
    <columns>time</columns>
    <columns>409</columns>
    <name>409</name>
    <points>
        <0>2021-02-18T19:07:00Z</0>
        <1>0</1>
    </points>
    <points>
        <0>2021-02-18T19:06:00Z</0>
        <1>0</1>
    </points>
    <points>
        <0>2021-02-18T19:05:00Z</0>
        <1>0</1>
    </points>
</content>
<content>
    <columns>time</columns>
    <columns>410</columns>
    <name>410</name>
    <points>
        <0>2021-02-18T19:07:00Z</0>
        <1>0</1>
    </points>
    <points>
        <0>2021-02-18T19:06:00Z</0>
        <1>0</1>
    </points>
    <points>
        <0>2021-02-18T19:05:00Z</0>
        <1>0</1>
    </points>
</content>
<content>
    <columns>time</columns>
    <columns>499</columns>
    <name>499</name>
    <points>
        <0>2021-02-18T19:07:00Z</0>
        <1>0</1>
    </points>
    <points>
        <0>2021-02-18T19:06:00Z</0>
        <1>0</1>
    </points>
    <points>
        <0>2021-02-18T19:05:00Z</0>
        <1>0</1>
    </points>
</content>
<RequestId>99D61AB3-6164-4CF2-A0DE-129C9B07618B</RequestId>
</DescribeEsExceptionDataResponse>
```

`JSON`格式

```
{
    "content": [
        {
            "columns": [
                "time",
                "401"
            ],
            "name": "401",
            "points": [
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
        },
        {
            "columns": [
                "time",
                "402"
            ],
            "name": "402",
            "points": [
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
        },
        {
            "columns": [
                "time",
                "403"
            ],
            "name": "403",
            "points": [
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
        },
        {
            "columns": [
                "time",
                "404"
            ],
            "name": "404",
            "points": [
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
        },
        {
            "columns": [
                "time",
                "405"
            ],
            "name": "405",
            "points": [
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
        },
        {
            "columns": [
                "time",
                "406"
            ],
            "name": "406",
            "points": [
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
        },
        {
            "columns": [
                "time",
                "407"
            ],
            "name": "407",
            "points": [
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
            "columns": [
                "time",
                "408"
            ],
            "name": "408",
            "points": [
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
        },
        {
            "columns": [
                "time",
                "409"
            ],
            "name": "409",
            "points": [
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
        },
        {
            "columns": [
                "time",
                "410"
            ],
            "name": "410",
            "points": [
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
        },
        {
            "columns": [
                "time",
                "499"
            ],
            "name": "499",
            "points": [
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

