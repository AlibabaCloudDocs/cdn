# DescribeRangeDataByLocateAndIspService

Queries the bandwidth data at a specified time of an Internet service provider \(ISP\) in different regions for an accelerated domain name.

**Before you call this operation, take note of the following rules:**

-   You can specify only one accelerated domain name in each call.
-   The data is collected every 5 minutes.
-   The bandwidth is measured in bit/s.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeRangeDataByLocateAndIspService&type=RPC&version=2014-11-11)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeRangeDataByLocateAndIspService|The operation that you want to perform. Set the value to **DescribeRangeDataByLocateAndIspService**. |
|DomainNames|String|Yes|abc.com|The accelerated domain name. You can specify only one accelerated domain name in each call. |
|EndTime|String|Yes|2017-12-22T08:00:00:00Z|The end of the time range to query.

 -   Specify the time in the ISO 8601 standard in the YYYY-MM-DDThh:mm:ssZ format.
-   The time must be in UTC. |
|StartTime|String|Yes|2016-08-01T22:00Z|The beginning of the time range to query.

 -   Specify the time in the ISO 8601 standard in the YYYY-MM-DDThh:mm:ssZ format.
-   The time must be in UTC.
-   The data is collected every 5 minutes. |
|IspNames|String|No|unicom|The ISP that you want to query. You can specify only one ISP in each call.

 You can call the [DescribeCdnRegionAndIsp](~~43474~~) operation to query ISPs. |
|LocationNames|String|No|liaoning,guangxi|The region that you want to query. You can specify one or more regions. Separate regions with commas \(,\).

 You can call the [DescribeCdnRegionAndIsp](~~43474~~) operation to query the recent region list. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|JsonResult|String|\{"1505973300":\{"Sudan":\{"Other ISP":\{"http\_codes":\{"000":0,"200":6,"400":0\},"rt":4183,"bandwidth":46639,"avg\_speed":7773,"pv":6,"hit\_rate":0.93,"request\_hit\_rate":0.66\}\}\}\}|The response parameters in JSON format. |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/?Action=DescribeRangeDataByLocateAndIspService
&EndTime=2017-12-22T08:00:00:00Z
&startTime=2016-08-01T22:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeRangeDataByLocateAndIspServiceResponse>
		  <Tianjin>
			    <China Telecom>
				      <bandwidth>7024681.44</bandwidth>
				      <pv>5819</pv>
				      <hit_rate>0</hit_rate>
				      <http_codes>
				</http_codes>
				      <rt>0</rt>
			    </China Telecom>
			    <China Unicom></China Unicom>
			    <China Mobile></China Mobile>
		  </Tianjin>
	  <description>Ok</description>
	  <retCode>0</retCode>
</DescribeRangeDataByLocateAndIspServiceResponse>
```

`JSON` format

```
{
        "1472659500": {
            "Tianjin": { {
                "China Telecom" {
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
                "China Unicom":{},
                "China Mobile":{}
        }
    },
    "description": "Ok", 
    "retCode": 0
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|The error message returned because the format of the specified start time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|The error message returned because the format of the specified end time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|The error message returned because the specified start time is invalid. Rectify the start time and try again.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

