# DescribeRangeDataByLocateAndIspService

Queries the bandwidth values at a specific time based on each Internet service provider \(ISP\) in different regions for an accelerated domain name.

**Note:** The data is collected at an interval of five minutes.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeRangeDataByLocateAndIspService&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeRangeDataByLocateAndIspService|The operation that you want to perform. Set the value to **DescribeRangeDataByLocateAndIspService**. |
|DomainNames|String|Yes|example.com|The accelerated domain name. |
|EndTime|String|Yes|2019-11-30T05:40:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

**Note:** The end time must be later than the start time. The difference between the end time and the start time cannot exceed one hour. |
|StartTime|String|Yes|2019-11-30T05:33:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|IspNames|String|No|unicom,telecom|The name of the ISP.

You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query ISPs. |
|LocationNames|String|No|liaoning,guangxi|The names of the regions. Separate multiple regions with commas \(,\).

You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query regions. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|JsonResult|String|\{"1472659200":\{"Tianjin":\{"China Telecom":\{"http\_codes":\{"000":0,"200":6,"400":0\},"rt":4183,"bandwidth":46639,"avg\_speed":7773,"pv":6,"hit\_rate":0.93,"request\_hit\_rate":0.66\}\}\}\}|The response parameters in the JSON format.

These parameters indicate the following information in sequence: UNIX time, region, ISP, distribution of HTTP status codes, response time, bandwidth \(unit: bit/s\), average response rate, page views, cache hit ratio, and request hit ratio. |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeRangeDataByLocateAndIspService
&DomainNames=example.com
&LocationNames=liaoning,guangxi
&IspNames=unicom,telecom
&startTime=2019-11-30T05:33:00Z
&EndTime=2019-11-30T05:40:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeRangeDataByLocateAndIspServiceResponse>
<JsonResult>
    <1472659200>
        <Tianjin>
            <China Telecom>
                <bandwidth>9889849.592</bandwidth>
                <pv>5739</pv>
                <hit_rate>0</hit_rate>
                <http_codes>
                    <200>5675</200>
                    <206>5</206>
                    <302>5</302>
                    <304>45</304>
                    <400>1</400>
                    <403>8</403>
                    <404>0</404>
                    <405>0</405>
                    <408>0</408>
                    <412>0</412>
                    <416>0</416>
                    <500>0</500>
                    <501>0</501>
                    <502>0</502>
                    <503>0</503>
                    <504>0</504>
                    <000>0</000>
                </http_codes>
                <rt>0</rt>
            </China Telecom>
            <China Unicom/>
            <China Mobile/>
        </Tianjin>
        <Beijing>
            <China Telecom>
                <bandwidth>9889849.592</bandwidth>
                <pv>5739</pv>
                <hit_rate>0</hit_rate>
                <http_codes>
                    <200>5675</200>
                    <206>5</206>
                    <302>5</302>
                    <304>45</304>
                    <400>1</400>
                    <403>8</403>
                    <404>0</404>
                    <405>0</405>
                    <408>0</408>
                    <412>0</412>
                    <416>0</416>
                    <500>0</500>
                    <501>0</501>
                    <502>0</502>
                    <503>0</503>
                    <504>0</504>
                    <000>0</000>
                </http_codes>
                <rt>0</rt>
            </China Telecom>
            <China Unicom/>
            <China Mobile/>
        </Beijing>
    </1472659200>
    <1472659500>
        <Tianjin>
            <China Telecom>
                <bandwidth>7024681.44</bandwidth>
                <pv>5819</pv>
                <hit_rate>0</hit_rate>
                <http_codes>
                    <200>5716</200>
                    <206>11</206>
                    <302>3</302>
                    <304>72</304>
                    <400>1</400>
                    <403>16</403>
                    <404>0</404>
                    <405>0</405>
                    <408>0</408>
                    <412>0</412>
                    <416>0</416>
                    <500>0</500>
                    <501>0</501>
                    <502>0</502>
                    <503>0</503>
                    <504>0</504>
                    <000>0</000>
                </http_codes>
                <rt>0</rt>
            </China Telecom>
            <China Unicom/>
            <China Mobile/>
        </Tianjin>
    </1472659500>
</JsonResult>
<RequestId>16A96B9A-F203-4EC5-8E43-CB92E68F4CD8</RequestId>
</DescribeRangeDataByLocateAndIspServiceResponse>
```

`JSON` format

```
{
    "JsonResult":[{
    "1472659200": {
        "Tianjin": {
            "China Telecom": {
                "bandwidth": 9889849.592,
                "pv": 5739,
                "hit_rate": 0,
                "http_codes": {
                    "200": 5675,
                    "206": 5,
                    "302": 5,
                    "304": 45,
                    "400": 1,
                    "403": 8,
                    "404": 0,
                    "405": 0,
                    "408": 0,
                    "412": 0,
                    "416": 0,
                    "500": 0,
                    "501": 0,
                    "502": 0,
                    "503": 0,
                    "504": 0,
                    "000": 0
                },
                "rt": 0
            },
            "China Unicom": {},
            "China Mobile": {}
        },
        "Beijing": {
            "China Telecom": {
                "bandwidth": 9889849.592,
                "pv": 5739,
                "hit_rate": 0,
                "http_codes": {
                    "200": 5675,
                    "206": 5,
                    "302": 5,
                    "304": 45,
                    "400": 1,
                    "403": 8,
                    "404": 0,
                    "405": 0,
                    "408": 0,
                    "412": 0,
                    "416": 0,
                    "500": 0,
                    "501": 0,
                    "502": 0,
                    "503": 0,
                    "504": 0,
                    "000": 0
                },
                "rt": 0
            },
            "China Unicom": {},
            "China Mobile": {}
        }
    },
    "1472659500": {
        "Tianjin": {
            "China Telecom": {
                "bandwidth": 7024681.44,
                "pv": 5819,
                "hit_rate": 0,
                "http_codes": {
                    "200": 5716,
                    "206": 11,
                    "302": 3,
                    "304": 72,
                    "400": 1,
                    "403": 16,
                    "404": 0,
                    "405": 0,
                    "408": 0,
                    "412": 0,
                    "416": 0,
                    "500": 0,
                    "501": 0,
                    "502": 0,
                    "503": 0,
                    "504": 0,
                    "000": 0
                },
                "rt": 0
            },
            "China Unicom": {},
            "China Mobile": {}
        }
    }
}],
    "RequestId": "16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
}
```

## Error codes

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|The error message returned because the format of the specified start time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|The error message returned because the format of the end time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|The error message returned because the specified start time is invalid. Rectify the start time and try again.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

