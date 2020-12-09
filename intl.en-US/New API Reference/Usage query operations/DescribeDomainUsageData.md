# DescribeDomainUsageData

Queries the resource usage information of specific domain names in a specified region.

**When you call this operation, note that:**

-   You can query usage data for a maximum of 100 accelerated domain names in each call. Separate multiple domain names with commas \(,\). If you do not specify an accelerated domain name, usage data of all accelerated domain names under your Alibaba Cloud account is queried.
-   If you do not set the Interval parameter, the maximum time range that can be queried in a call is one month. If you specify a time range of one to three days in a call, the time interval between the entries that are returned is one hour. If you specify a time range of more than four days in a call, the time interval between the entries that are returned is one day.
-   If you set the Interval parameter to 300, the maximum time range that can be queried in a call is three days.
-   If you set the Interval parameter to 300, you can query data that was collected within the last six months. If you set the Interval parameter to 3600 or 86400, you can query data that was collected within the last 12 months.
-   Usage data includes network traffic \(measured in bytes\), bandwidth values \(measured in bits/s\), and the number of requests.
-   The maximum number of times that each user can call this operation per second is 10.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainUsageData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainUsageData|The operation that you want to perform. Set the value to **DescribeDomainUsageData**. |
|EndTime|String|Yes|2015-12-10T22:00:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 **Note:** The end time must be later than the start time. The maximum time range that can be queried is 31 days. |
|Field|String|Yes|bps|The type of data to query. Valid values: **bps** \(bandwidth\), **traf** \(network traffic\), and **acc** \(number of requests\).

 **Note:** If the value is set to **acc**, the **area** parameter is not supported. |
|StartTime|String|Yes|2015-12-10T20:00:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 The data is collected at intervals of five minutes. |
|DataProtocol|String|No|all|The protocol of the data to query. Valid values: **https**, **http**, and **all**. Default value: all. |
|DomainName|String|No|example.com|The accelerated domain names that you want to query. Separate multiple domain names with commas \(,\).

 If you do not set this parameter, the usage data of all accelerated domain names is returned. |
|Area|String|No|CN|The ID of the region.

 -   **CN**: \(default value\) mainland China
-   **OverSeas**: regions outside mainland China
-   **AP1**: Asia Pacific 1
-   **AP2**: Asia Pacific 2
-   **AP3**: Asia Pacific 3
-   **NA**: North America
-   **SA**: South America
-   **EU**: Europe
-   **MEAA**: Middle East and Africa
-   **All**: all regions |
|Interval|String|No|300|The time interval between the data entries to return. Unit: seconds. Valid values: **300** \(5 minutes\), **3600** \(1 hour\), and **86400** \(1 day\).

 -   If you set the Interval parameter to 300, you can query data that was collected within the last six months. In this case, the maximum time range that can be queried in each call is three days.
-   If you set the Interval parameter to 3600 or 86400, you can query data that was collected within the last 12 months.
-   If you do not set the Interval parameter, the maximum time range that can be queried at a time is one month. If you specify a time range of one to three days for a query, the time interval between the entries that are returned is one hour. If you specify a time range of at least four days for a query, the time interval between the entries that are returned is one day. |

The following table lists the parameters for different billable items.

|Billable item

|Valid value of DataProtocol

|Valid value of Type

|Valid value of Field

|Valid value of Area |
|---------------|-----------------------------|---------------------|----------------------|---------------------|
|Network traffic

|all. The value of this parameter can be empty.

|all. The value of this parameter can be empty.

|traf

|CN, OverSeas, AP1, AP2, AP3, NA, SA, EU, and MEAA. |
|Bandwidth

|all. The value of this parameter can be empty.

|all. The value of this parameter can be empty.

|bps

|CN, OverSeas, AP1, AP2, AP3, NA, SA, EU, and MEAA. |
|Number of HTTPS requests for static content

|https

|static

|acc

|all |
|Number of HTTP requests for dynamic content

|http

|dynamic

|acc

|all |
|Number of HTTPS requests for dynamic content

|https

|dynamic

|acc

|all |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Area|String|CN|The region where the usage information was collected. |
|DataInterval|String|300|The time interval between the data entries. Unit: seconds. |
|DomainName|String|example.com|The accelerated domain name. |
|EndTime|String|2015-12-10T22:00:00Z|The end of the time range that was queried. |
|RequestId|String|B955107D-E658-4E77-B913-E0AC3D31693E|The ID of the request. |
|StartTime|String|2015-12-10T20:00:00Z|The beginning of the time range where the data was queried. |
|Type|String|static|The type of content based on which the usage information was collected. |
|UsageDataPerInterval|Array of DataModule| |The data transfer value collected at each interval. |
|DataModule| | | |
|PeakTime|String|2015-12-10T21:30:00Z|If the **Field** parameter in the request is set to **bps**, this parameter returns the time of the highest bandwidth value. Otherwise, this parameter returns the same value as the **TimeStamp** parameter. |
|SpecialValue|String|xxxx|The data usage in a specific scenario. |
|TimeStamp|String|2015-12-10T21:30:00Z|The timestamp of the data. |
|Value|String|423304182|The amount of data that was used. |

## Examples

Sample requests

```
Queries data usage in mainland China:
http://cdn.aliyuncs.com/?Action=DescribeDomainUsageData
&DomainName=example.com
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T22:00:00Z
&Field=traf
&Area=CN
&<Common request parameters>

Queries bandwidth usage in Europe:
http://cdn.aliyuncs.com/?Action=DescribeDomainUsageData&DomainName=example.com
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T22:00:00Z
&Field=bps
&Area=EU
&<Common request parameters>

Queries the number of HTTPS requests for static content:
http://cdn.aliyuncs.com/?Action=DescribeDomainUsageData&DomainName=example.com
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T22:00:00Z
&Type=static
&DataProtocol=https
&Field=acc
&Area=all
&<Common request parameters>

Queries the number of HTTP requests for dynamic content:
http://cdn.aliyuncs.com/?Action=DescribeDomainUsageData&DomainName=example.com
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T22:00:00Z
&Type=dynamic
&DataProtocol=http
&Field=acc
&Area=all
&<Common request parameters>

Queries the number of HTTPS requests for dynamic content:
http://cdn.aliyuncs.com/?Action=DescribeDomainUsageData&DomainName=example.com
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T22:00:00Z
&Type=dynamic
&DataProtocol=https
&Field=acc
&Area=all
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DomainName>example.com</DomainName>
<DataInterval>300</DataInterval>
<UsageDataPerInterval>
    <DataModule>
        <TimeStamp>2015-12-10T20:00:00Z</TimeStamp>
        <PeakTime>2015-12-10T20:05:00Z</PeakTime>
        <Value>423304182</Value>
        <SpecialValue>423304182</SpecialValue>
    </DataModule>
    <DataModule>
        <TimeStamp>2015-12-10T21:00:00Z</TimeStamp>
        <PeakTime>2015-12-10T21:30:00Z</PeakTime>
        <Value>454680793</Value>
        <SpecialValue>423304182</SpecialValue>
    </DataModule>
</UsageDataPerInterval>
<RequestId>B955107D-E658-4E77-B913-E0AC3D31693E</RequestId>
<StartTime>2015-12-10T20:00Z</StartTime>
<EndTime>2015-12-10T21:00Z</EndTime>
<Area>CN</Area>
<Type>traf</Type>
```

`JSON` format

```
{
    "DomainName": "example.com",
    "DataInterval": "300",
    "UsageDataPerInterval": {
        "DataModule": [
            {
                "TimeStamp": "2015-12-10T20:00:00Z",
                "PeakTime": "2015-12-10T20:05:00Z",
                "Value": "423304182",
                "SpecialValue": "423304182"
            },
            {
                "TimeStamp": "2015-12-10T21:00:00Z",
                "PeakTime": "2015-12-10T21:30:00Z",
                "Value": "454680793",
                "SpecialValue": "423304182"
            }
        ]
    },
    "RequestId": "B955107D-E658-4E77-B913-E0AC3D31693E",
    "StartTime": "2015-12-10T20:00Z",
    "EndTime": "2015-12-10T21:00Z",
    "Area": "CN",
    "Type": "traf"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

