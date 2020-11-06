# DescribeDomainHttpCodeData

Queries the total number and proportions of HTTP status codes returned from accelerated domain names. You can query data collected within the last 90 days.

**When you call this operation, note that:**

-   If you do not set StartTime or EndTime, data collected within the last 24 hours is queried. If you set both StartTime and EndTime, data collected within the specified time range is queried.
-   You can specify one or more accelerated domain names. Separate multiple domain names with commas \(,\).
-   Data is collected at an interval of five minutes.
-   The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainHttpCodeData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainHttpCodeData|The operation that you want to perform. Set the value to **DescribeDomainHttpCodeData**. |
|DomainName|String|No|test.test.com|The accelerated domain names. Separate multiple domain names with commas \(,\).

By default, this operation queries the number of queries per second for all accelerated domain names. |
|StartTime|String|No|2015-11-30T05:33:00Z|The start of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2015-11-30T05:40:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

The end time must be later than the start time. |
|Interval|String|No|300|The time interval between the data entries. Unit: seconds. The value varies based on the values of the **StartTime** and **EndTime** parameters. Valid values:

-   If the time span between StartTime and EndTime is less than 3 days, valid values are **300**, **3600**, and **86400**. Default value: **300**.
-   If the time span between StartTime and EndTime is from 3 to 31 days \(31 days excluded\), valid values are **3600** and **86400**. Default value: **3600**.
-   If the time span between StartTime and EndTime is 31 days or longer, the valid value is **86400**. Default value: **86400**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DataInterval|String|300|The time interval between the data entries. |
|DomainName|String|test.test.com|The accelerated domain name. |
|EndTime|String|2015-11-30T05:40:00Z|The end of the time range that was queried. |
|HttpCodeData|Array of UsageData| |The proportions of HTTP status codes at each time interval. |
|UsageData| | | |
|TimeStamp|String|2015-11-30T05:30:00Z|The timestamp of the data. |
|Value|Array of CodeProportionData| |The proportions of each HTTP status code. |
|CodeProportionData| | | |
|Code|String|200|The HTTP status code. |
|Count|String|300|The total number of the HTTP status codes returned. |
|Proportion|String|66.046511627907|The proportion of the HTTP status code. |
|RequestId|String|BC858082-736F-4A25-867B-E5B67C85ACF7|The ID of the request. |
|StartTime|String|2015-11-30T05:33:00Z|The beginning of the time range that was queried. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeDomainHttpCodeData
&DomainName="test.com,abc.com"
&StartTime=2015-11-30T05:33:00Z
&EndTime=2015-11-30T05:40:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainHttpCodeDataResponse>
      <HttpCodeData>
            <UsageData>
                  <TimeStamp>2015-11-30T05:40:00Z</TimeStamp>
                  <Value>
                        <CodeProportionData>
                              <Proportion>66.046511627907</Proportion>
                              <Code>200</Code>
                        </CodeProportionData>
                        <CodeProportionData>
                              <Proportion>4.72868217054264</Proportion>
                              <Code>206</Code>
                        </CodeProportionData>
                        <CodeProportionData>
                              <Proportion>0.155038759689922</Proportion>
                              <Code>302</Code>
                        </CodeProportionData>
                        <CodeProportionData>
                              <Proportion>0.62015503875969</Proportion>
                              <Code>304</Code>
                        </CodeProportionData>
                        <CodeProportionData>
                              <Proportion>28.4496124031008</Proportion>
                              <Code>500</Code>
                        </CodeProportionData>
                  </Value>
            </UsageData>
            <UsageData>
                  <TimeStamp>2015-11-30T05:35:00Z</TimeStamp>
                  <Value>
                        <CodeProportionData>
                              <Proportion>64.7822765469824</Proportion>
                              <Code>200</Code>
                        </CodeProportionData>
                        <CodeProportionData>
                              <Proportion>3.74331550802139</Proportion>
                              <Code>206</Code>
                        </CodeProportionData>
                        <CodeProportionData>
                              <Proportion>0.152788388082506</Proportion>
                              <Code>302</Code>
                        </CodeProportionData>
                        <CodeProportionData>
                              <Proportion>1.90985485103132</Proportion>
                              <Code>304</Code>
                        </CodeProportionData>
                        <CodeProportionData>
                              <Proportion>29.4117647058824</Proportion>
                              <Code>500</Code>
                        </CodeProportionData>
                  </Value>
            </UsageData>
            <UsageData>
                  <TimeStamp>2015-11-30T05:30:00Z</TimeStamp>
                  <Value>
                        <CodeProportionData>
                              <Proportion>67.1458998935037</Proportion>
                              <Code>200</Code>
                        </CodeProportionData>
                        <CodeProportionData>
                              <Proportion>12.6730564430245</Proportion>
                              <Code>206</Code>
                        </CodeProportionData>
                        <CodeProportionData>
                              <Proportion>0.053248136315229</Proportion>
                              <Code>302</Code>
                        </CodeProportionData>
                        <CodeProportionData>
                              <Proportion>0.958466453674121</Proportion>
                              <Code>304</Code>
                        </CodeProportionData>
                        <CodeProportionData>
                              <Proportion>19.1693290734824</Proportion>
                              <Code>500</Code>
                        </CodeProportionData>
                  </Value>
            </UsageData>
      </HttpCodeData>
      <DataInterval>300</DataInterval>
      <RequestId>BC858082-736F-4A25-867B-E5B67C85ACF7</RequestId>
      <DomainName>example1.com,example2.com</DomainName>
      <EndTime>2015-11-30T05:40:00Z</EndTime>
      <StartTime>2015-11-30T05:33:00Z</StartTime>
</DescribeDomainHttpCodeDataResponse>
```

`JSON` format

```
{
    "HttpCodeData": {
        "UsageData": [
            {
                "TimeStamp": "2015-11-30T05:40:00Z",
                "Value": {
                    "CodeProportionData": [
                        {
                            "Proportion": "66.046511627907",
                            "Code": "200"
                        },
                        {
                            "Proportion": "4.72868217054264",
                            "Code": "206"
                        },
                        {
                            "Proportion": "0.155038759689922",
                            "Code": "302"
                        },
                        {
                            "Proportion": "0.62015503875969",
                            "Code": "304"
                        },
                        {
                            "Proportion": "28.4496124031008",
                            "Code": "500"
                        }
                    ]
                }
            },
            {
                "TimeStamp": "2015-11-30T05:35:00Z",
                "Value": {
                    "CodeProportionData": [
                        {
                            "Proportion": "64.7822765469824",
                            "Code": "200"
                        },
                        {
                            "Proportion": "3.74331550802139",
                            "Code": "206"
                        },
                        {
                            "Proportion": "0.152788388082506",
                            "Code": "302"
                        },
                        {
                            "Proportion": "1.90985485103132",
                            "Code": "304"
                        },
                        {
                            "Proportion": "29.4117647058824",
                            "Code": "500"
                        }
                    ]
                }
            },
            {
                "TimeStamp": "2015-11-30T05:30:00Z",
                "Value": {
                    "CodeProportionData": [
                        {
                            "Proportion": "67.1458998935037",
                            "Code": "200"
                        },
                        {
                            "Proportion": "12.6730564430245",
                            "Code": "206"
                        },
                        {
                            "Proportion": "0.053248136315229",
                            "Code": "302"
                        },
                        {
                            "Proportion": "0.958466453674121",
                            "Code": "304"
                        },
                        {
                            "Proportion": "19.1693290734824",
                            "Code": "500"
                        }
                    ]
                }
            }
        ]
    },
    "DataInterval": "300",
    "RequestId": "BC858082-736F-4A25-867B-E5B67C85ACF7",
    "DomainName": "example1.com,example2.com",
    "EndTime": "2015-11-30T05:40:00Z",
    "StartTime": "2015-11-30T05:33:00Z"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

