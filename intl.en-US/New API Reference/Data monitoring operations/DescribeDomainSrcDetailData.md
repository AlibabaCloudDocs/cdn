# DescribeDomainSrcDetailData

Queries the back-to-origin information about one or more accelerated domain names at a time. The data is collected at an interval of five minutes. You can query data collected within the last seven days.

**When you call this operation, note that:**

-   In each query, the time range specified by the StartTime and EndTime parameters cannot exceed 24 hours.
-   The maximum number of times that each user can call this operation per second is 10.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainSrcDetailData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainSrcDetailData|The operation that you want to perform. Set the value to **DescribeDomainSrcTrafficData**. |
|DomainName|String|Yes|example.com|The accelerated domain names. Separate multiple domain names with commas \(,\). |
|StartTime|String|Yes|2018-06-05T20:00:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|Yes|2018-06-05T20:10:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|Field|String|Yes|qps,bps,http\_code|The types of information. Separate multiple types with commas \(,\). Valid values:

-   qps
-   bps
-   http\_code |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Data|String|\{ "bps": 306202454542.3067, "domain\_name": "example.com", "qps": 71814.53333333334, "http\_code": \{ "200": 466521, "304": 35, "400": 16594, "404": 112, "502": 10038, "504": 151 \}, "time\_stp": "2018-06-05T20:00:00Z" \}|The detailed back-to-origin information. |
|RequestId|String|B49E6DDA-F413-422B-B58E-2FA23F286726|The ID of the request |

## Examples

Sample requests

```
https://cdn.aliyuncs.com?Action=DescribeDomainSrcDetailData
&DomainName=example.com
&Field=qps,bps,http_code
&StartTime=2018-06-05T20:00:00Z
&EndTime=2018-06-05T20:10:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainSrcDetailDataResponse>
<Data>
    <bps>306202454542.3067</bps>
    <domain_name>example.com</domain_name>
    <qps>71814.53333333334</qps>
    <http_code>
        <200>466521</200>
        <304>35</304>
        <400>16594</400>
        <404>112</404>
        <502>10038</502>
        <504>151</504>
    </http_code>
    <time_stp>2018-06-05T20:00:00Z</time_stp>
</Data>
<RequestId>B49E6DDA-F413-422B-B58E-2FA23F286726</RequestId>
</DescribeDomainSrcDetailDataResponse>
```

`JSON` format

```
{
   "Data":[
        {
            "bps": 306202454542.3067,
            "domain_name": "example.com",
            "qps": 71814.53333333334,
            "http_code": {
                "200": 466521,
                "304": 35,
                "400": 16594,
                "404": 112,
                "502": 10038,
                "504": 151
            },
            "time_stp": "2018-06-05T20:00:00Z"
        }
   ],
   "RequestId":"B49E6DDA-F413-422B-B58E-2FA23F286726"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidEndTime.Mismatch|Specified end time does not math the specified start time.|The error message returned because the end time must be later than the start time.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

