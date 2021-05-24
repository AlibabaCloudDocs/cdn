# DescribeCdnUserResourcePackage

Queries the resource plans that you have purchased for Alibaba Cloud Content Delivery Network \(CDN\).

**Note:** The maximum number of times that each user can call this operation per second is 30.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeCdnUserResourcePackage&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCdnUserResourcePackage|The operation that you want to perform. Set the value to **DescribeCdnUserResourcePackage**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|84839536-2B7E-457D-9D8C-82E6C7D4E1A3|The ID of the request. |
|ResourcePackageInfos|Array of ResourcePackageInfo| |The details about each resource plan. The details are organized in an array. The array consists of the subparameter values of the ResourcePackageInfo parameter. |
|ResourcePackageInfo| | | |
|CommodityCode|String|cdnflowbag|The code of the data transfer plan. |
|CurrCapacity|String|10995089554629|The remaining quota of the resource plan.

 -   The remaining amount of data transfer provided by the resource plan. Unit: bytes.
-   The remaining number of requests provided by the resource plan. |
|DisplayName|String|CDN resource plan \(mainland China\)|The name of the resource plan. |
|EndTime|String|2018-07-01T08:00:00Z|The time when the resource plan expires. |
|InitCapacity|String|536870912000|The total quota of the resource plan.

 -   The total amount of data transfer provided by the resource plan. Unit: bytes.
-   The total number of requests provided by the resource plan. |
|InstanceId|String|FP-ilttxc23a|The ID of the instance. |
|StartTime|String|2017-12-05T19:10:58Z|The time when the resource plan took effect. |
|Status|String|valid|The status of the data transfer plan. Valid values: Valid values:

 -   **valid**: The resource plan is valid.
-   **closed**: The resource package is invalid. |
|TemplateName|String|CDN resource plan|The name of the template. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/?Action=DescribeCdnUserResourcePackage
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeCdnUserResourcePackageResponse>
	  <ResourcePackageInfos>
		    <ResourcePackageInfo>
			      <Status>closed</Status>
			      <InstanceId>FP-mkqgwsyui</InstanceId>
			      <CommodityCode>cdnflowbag</CommodityCode>
			      <InitCapacity>10995116277760</InitCapacity>
			      <EndTime>2017-01-30T08:00:00Z</EndTime>
			      <StartTime>2016-01-30T03:40:06Z</StartTime>
			      <DisplayName>CDN resource plan (mainland China)</DisplayName>
			      <CurrCapacity>10995089554629</CurrCapacity>
		    </ResourcePackageInfo>
		    <ResourcePackageInfo>
			      <Status>valid</Status>
			      <InstanceId>FP-ilttxc23a</InstanceId>
			      <CommodityCode>cdnflowbag</CommodityCode>
			      <InitCapacity>536870912000</InitCapacity>
			      <EndTime>2018-07-01T08:00:00Z</EndTime>
			      <StartTime>2017-07-01T01:26:41Z</StartTime>
			      <DisplayName>CDN resource plan (mainland China)</DisplayName>
			      <CurrCapacity>0</CurrCapacity>
		    </ResourcePackageInfo>
		    <ResourcePackageInfo>
			      <Status>valid</Status>
			      <InstanceId>CDNHTTPSBAG-cn-v0h0dnlq4000m9</InstanceId>
			      <CommodityCode>cdnhttpsbag</CommodityCode>
			      <InitCapacity>10000000</InitCapacity>
			      <EndTime>2018-12-06T08:00:00Z</EndTime>
			      <StartTime>2017-12-05T19:10:58Z</StartTime>
			      <DisplayName>CDN resource plan for HTTPS requests</DisplayName>
			      <CurrCapacity>9999645</CurrCapacity>
		    </ResourcePackageInfo>
	  </ResourcePackageInfos>
	  <RequestId>84839536-2B7E-457D-9D8C-82E6C7D4E1A3</RequestId>
</DescribeCdnUserResourcePackageResponse>
```

`JSON` format

```
{
    "ResourcePackageInfos": {
        "ResourcePackageInfo": [
            {
                "Status": "closed",
                "InstanceId": "FP-mkqgwsyui",
                "CommodityCode": "cdnflowbag",
                "InitCapacity": "10995116277760",
                "EndTime": "2017-01-30T08:00:00Z",
                "StartTime": "2016-01-30T03:40:06Z",
                "DisplayName": "CDN resource plan (mainland China)",
                "CurrCapacity": "10995089554629"
            },
            {
                "Status": "valid",
                "InstanceId": "FP-ilttxc23a",
                "CommodityCode": "cdnflowbag",
                "InitCapacity": "536870912000",
                "EndTime": "2018-07-01T08:00:00Z",
                "StartTime": "2017-07-01T01:26:41Z",
                "DisplayName": "CDN resource plan (mainland China)",
                "CurrCapacity": "0"
            },
            {
                "Status": "valid",
                "InstanceId": "CDNHTTPSBAG-cn-v0h0dnlq4000m9",
                "CommodityCode": "cdnhttpsbag",
                "InitCapacity": "10000000",
                "EndTime": "2018-12-06T08:00:00Z",
                "StartTime": "2017-12-05T19:10:58Z",
                "DisplayName": "CDN resource plan for HTTPS requests",
                "CurrCapacity": "9999645"
            }
        ]
    },
    "RequestId": "84839536-2B7E-457D-9D8C-82E6C7D4E1A3"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

