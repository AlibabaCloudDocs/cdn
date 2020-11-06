# DescribeDomainSrcHttpCodeData

Queries the total number and proportions of HTTP status codes returned from accelerated domain names. The data is collected at an interval of five minutes. You can query data collected within the last 90 days.

**When you call this operation, note that:**

-   If you do not set StartTime or EndTime, data collected within the last 24 hours is queried. If you set both StartTime and EndTime, data collected within the specified time range is queried.
-   The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainSrcHttpCodeData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainSrcHttpCodeData|The operation that you want to perform. Set the value to **DescribeDomainSrcHttpCodeData**. |
|DomainName|String|No|example1.com,example2.com|The accelerated domain names. Separate multiple domain names with commas \(,\). |
|StartTime|String|No|2019-11-30T05:33:00Z|The start of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2019-11-30T05:40:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

The end time must be later than the start time. |
|Interval|String|No|300|The time interval between the data entries. Unit: seconds. The value varies based on the values of the **StartTime** and **EndTime** parameters. Valid values:

-   If the time span between StartTime and EndTime is less than 3 days, valid values are **300**, **3600**, and **86400**. Default value: **300**.
-   If the time span between StartTime and EndTime is from 3 to 31 days \(31 days excluded\), valid values are **3600** and **86400**. Default value: **3600**.
-   If the time span between StartTime and EndTime is 31 days or longer, the valid value is **86400**. Default value: **86400**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DataInterval|String|300|The time interval between the entries returned. Unit: seconds. |
|DomainName|String|example1.com,example2.com|The accelerated domain name. |
|EndTime|String|2015-11-30T05:40:00Z|The end of the time range that was queried. |
|HttpCodeData|Array of UsageData| |The proportions of HTTP status codes at each time interval. |
|UsageData| | | |
|TimeStamp|String|2015-11-30T05:30:00Z|The timestamp of the data. |
|Value|Array of CodeProportionData| |The proportions of HTTP status codes. |
|CodeProportionData| | | |
|Code|String|200|The HTTP status code. |
|Count|String|2300|The total number of HTTP status codes returned. |
|Proportion|String|67.1458998935037|The proportion of the HTTP status code. |
|RequestId|String|BC858082-736F-4A25-867B-E5B67C85ACF7|The ID of the request. |
|StartTime|String|2015-11-30T05:33:00Z|The beginning of the time range that was queried. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeDomainSrcHttpCodeData
&DomainName=example1.com,example2.com
&StartTime=2019-11-30T05:33:00Z
&EndTime=2019-11-30T05:40:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainSrcHttpCodeDataResponse>    
  <HttpCodeData>
        <UsageData>
              <TimeStamp>2019-11-30T05:35:00Z</TimeStamp>
              <Value>
                    <CodeProportionData>
                          <Count>1</Count>
                          <Proportion>100</Proportion>
                          <Code>200</Code>
                    </CodeProportionData>
              </Value>
        </UsageData>
  </HttpCodeData>
  <DataInterval>300</DataInterval>
  <RequestId>A2E05931-13B7-40C3-843F-ECD9423959C1</RequestId>
  <EndTime>2019-11-30T05:40:00Z</EndTime>
  <StartTime>2019-11-30T05:33:00Z</StartTime>
</DescribeDomainSrcHttpCodeDataResponse>
```

`JSON` format

```
{
    "HttpCodeData": {
        "UsageData": [
            {
                "TimeStamp": "2019-11-30T05:35:00Z",
                "Value": {
                    "CodeProportionData": [
                        {
                            "Count": 1,
                            "Proportion": 100,
                            "Code": "200"
                        }
                    ]
                }
            }
        ]
    },
    "DataInterval": 300,
    "RequestId": "A2E05931-13B7-40C3-843F-ECD9423959C1",
    "EndTime": "2019-11-30T05:40:00Z",
    "StartTime": "2019-11-30T05:33:00Z"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

