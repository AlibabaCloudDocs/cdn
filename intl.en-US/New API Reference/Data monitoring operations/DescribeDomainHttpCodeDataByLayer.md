# DescribeDomainHttpCodeDataByLayer

Queries the numbers of HTTP status codes during a specified period of time.

**Before you call this operation, take note of the following rules:**

-   If you do not set the StartTime or EndTime parameter, data within the last 24 hours is queried. If you set both the StartTime and EndTime parameters, data within the specified time range is queried. You must set both parameters or leave both of them empty.
-   You can specify multiple domain names and separate them with commas \(,\).
-   You can query data within the last 90 days.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different software development kits \(SDKs\).](https://api.aliyun.com/#product=Cdn&api=DescribeDomainHttpCodeDataByLayer&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainHttpCodeDataByLayer|The operation that you want to perform. Set the value to **DescribeDomainHttpCodeDataByLayer**. |
|DomainName|String|No|example.com|The accelerated domain name. You can specify multiple domain names and separate them with commas \(,\).

 If you do not specify a domain name, data of all domain names are queried and merged. |
|StartTime|String|No|2020-07-05T22:00:00Z|The beginning of the time range to query. The time follows the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time is displayed in UTC.

 The minimum data collection interval is 5 minutes.

 If you do not set this parameter, data within the last 24 hours is queried. |
|EndTime|String|No|2020-07-06T22:00:00Z|The end of the time range to query. The time follows the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 The end of the time range to query. The end time must be later than the start time. |
|Interval|String|No|300|The interval at which data is collected. Unit: seconds. The valid values vary based on the specified time range.

 Valid values are:

 -   If the specified time range is less than 3 days, valid values are 300, 3600, and 86400.
-   If the specified time range is 3 to 31 days \(31 days excluded\), valid values are 3600 and 86400.
-   If the specified time range is 31 days or longer, the valid value is 86400.

 If you do not set this parameter or the specified value is invalid, the default value is used. |
|LocationNameEn|String|No|hangzhou|The name of the region. You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query the most recent region list.

 If you do not specify a region, data in all regions is queried. |
|IspNameEn|String|No|telecom|The name of the Internet service provider \(ISP\) for your Content Delivery Network \(CDN\) service. You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query the most recent ISP list.

 If you do not specify an ISP, data of all ISPs is queried. |
|Layer|String|No|all|The network layer at which you want to query data. You can specify the network layer \(**IPv4** or **IPv6**\), the application layer \(**http**, **https**, or **quic**\), or both layers \(**all**\).

 Default value: **all**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DataInterval|String|300|The time interval between the data entries. Unit: seconds. |
|HttpCodeDataInterval|Array of DataModule| |The number of times that each HTTP status code was returned at each time interval. |
|DataModule| | | |
|TimeStamp|String|2015-12-10T20:35:00Z|The timestamp of the data. |
|TotalValue|String|110|The total number of times that HTTP status codes were returned at each time interval. |
|Value|String|"Value": \{ "200": 10, "206": 100\}|The number of times that the HTTP status code was returned at each time interval. |
|RequestId|String|BEA5625F-8FCF-48F4-851B-CA63946DA664|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com?Action=DescribeDomainHttpCodeDataByLayer
&DomainName=example.com
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T21:00:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainHttpCodeDataByLayerResponse>
<HttpCodeDataInterval>
    <DataModule>
        <TimeStamp>2015-12-10T21:00:00Z</TimeStamp>
        <Value>
            <200>10</200>
            <206>100</206>
        </Value>
        <TotalValue>110</TotalValue>
    </DataModule>
    <DataModule>
        <TimeStamp>2015-12-10T20:35:00Z</TimeStamp>
        <Value>
            <200>12</200>
            <206>120</206>
        </Value>
        <TotalValue>132</TotalValue>
    </DataModule>
</HttpCodeDataInterval>
<DataInterval>300</DataInterval>
<RequestId>BEA5625F-8FCF-48F4-851B-CA63946DA664</RequestId>
</DescribeDomainHttpCodeDataByLayerResponse>
```

`JSON` format

```
{
    "HttpCodeDataInterval": {
        "DataModule": [
            {
                "TimeStamp": "2015-12-10T21:00:00Z",
                "Value": {
                    "200": 10,
                    "206": 100
                },
                "TotalValue": 110
            },
            {
                "TimeStamp": "2015-12-10T20:35:00Z",
                "Value": {
                    "200": 12,
                    "206": 120
                },
                "TotalValue": 132
            }
        ]
    },
    "DataInterval": "300",
    "RequestId": "BEA5625F-8FCF-48F4-851B-CA63946DA664"
}
```

## Errors

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

