# DescribeDomainQpsData

Queries the number of queries per second for an accelerated domain name. The data is collected at an interval of five minutes. You can query data collected within the last 90 days.

**When you call this operation, note that:**

-   If you do not set StartTime or EndTime, data collected within the last 24 hours is queried. If you set both StartTime and EndTime, data collected within the specified time range is queried.
-   You can specify one or more domain names. Separate multiple domain names with commas \(,\).
-   The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainQpsData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainQpsData|The operation that you want to perform. Set the value to **DescribeDomainQpsData**. |
|DomainName|String|No|test.test.com|The accelerated domain names. Separate multiple domain names with commas \(,\).

By default, this operation queries the number of queries per second for all accelerated domain names. |
|StartTime|String|No|2019-11-30T05:33:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2019-11-30T05:40:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

The end time must be later than the start time. |
|Interval|String|No|300|The time interval between the data entries. Unit: seconds. The value varies based on the values of the **StartTime** and **EndTime** parameters. Valid values:

-   If the time span between StartTime and EndTime is less than 3 days, valid values are **300**, **3600**, and **86400**. Default value: **300**.
-   If the time span between StartTime and EndTime is from 3 to 31 days \(31 days excluded\), valid values are **3600** and **86400**. Default value: **3600**.
-   No less than 31 days: **86400**. Default value:**86400**. |
|IspNameEn|String|No|unicom|The name of the Internet service provider \(ISP\) for your Content Delivery Network \(CDN\) service. You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query ISPs. If you do not set this parameter, all ISPs are queried. |
|LocationNameEn|String|No|beijing|The name of the region. You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query regions. If you do not set this parameter, all regions are queried. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DataInterval|String|300|The time interval between the entries returned. Unit: seconds. |
|DomainName|String|test.test.com|The accelerated domain name. |
|StartTime|String|2019-11-30T05:33:00Z|The beginning of the time range that was queried. |
|EndTime|String|2019-11-30T05:40:00Z|The end of the time range that was queried. |
|RequestId|String|B8333EDB-4595-46E0-AFE9-29BAA290D0E0|The ID of the request. |
|QpsDataInterval|Array of DataModule| |The number of queries per second at each time interval. |
|DataModule| | | |
|AccDomesticValue|String|0|The number of visits inside mainland China. |
|AccOverseasValue|String|0|The number of visits outside mainland China. |
|AccValue|String|0|The total number of visits. |
|DomesticValue|String|0|The number of queries per second in mainland China. |
|HttpsAccDomesticValue|String|1|The number of HTTPS requests sent to L1 CDN nodes inside mainland China. |
|HttpsAccOverseasValue|String|1|The number of HTTPS requests sent to L1 CDN nodes outside mainland China. |
|HttpsAccValue|String|1|The number of HTTPS requests sent to L1 CDN nodes. |
|HttpsDomesticValue|String|1|The number of queries per second that is calculated based on the HTTPS requests sent to L1 CDN nodes inside mainland China. |
|HttpsOverseasValue|String|1|The number of queries per second that is calculated based on the HTTPS requests sent to L1 CDN nodes outside mainland China. |
|HttpsValue|String|1|The number of queries per second that is calculated based on the HTTPS requests sent to L1 CDN nodes. |
|OverseasValue|String|0|The number of queries per second outside mainland China. |
|TimeStamp|String|2019-11-30T05:40:00Z|The timestamp of the data. |
|Value|String|0|The total number of queries per second. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeDomainQpsData
&DomainName=test.com
&StartTime=2019-11-30T05:33:00Z
&EndTime=2019-11-30T05:40:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainQpsDataResponse>
  <QpsDataInterval>
        <DataModule>
              <HttpsOverseasValue>0</HttpsOverseasValue>
              <TimeStamp>2019-11-30T05:35:00Z</TimeStamp>
              <HttpsAccOverseasValue>0</HttpsAccOverseasValue>
              <Value>0.006666666666666667</Value>
              <OverseasValue>0</OverseasValue>
              <HttpsDomesticValue>0</HttpsDomesticValue>
              <AccOverseasValue>0</AccOverseasValue>
              <AccValue>2</AccValue>
              <HttpsAccValue>0</HttpsAccValue>
              <DomesticValue>0.006666666666666667</DomesticValue>
              <HttpsAccDomesticValue>0</HttpsAccDomesticValue>
              <HttpsValue>0</HttpsValue>
        </DataModule>
  </QpsDataInterval>
  <DataInterval>300</DataInterval>
  <RequestId>C2416D6C-B10A-474C-8FE8-0F9EF7ACA674</RequestId>
  <EndTime>2019-11-30T05:40:00Z</EndTime>
  <StartTime>2019-11-30T05:33:00Z</StartTime>
</DescribeDomainQpsDataResponse>
```

`JSON` format

```
{
    "QpsDataInterval": {
        "DataModule": [
            {
                "HttpsOverseasValue": 0,
                "TimeStamp": "2019-11-30T05:35:00Z",
                "HttpsAccOverseasValue": 0,
                "Value": "0.006666666666666667",
                "OverseasValue": 0,
                "HttpsDomesticValue": 0,
                "AccOverseasValue": 0,
                "AccValue": 2,
                "HttpsAccValue": 0,
                "DomesticValue": "0.006666666666666667",
                "HttpsAccDomesticValue": 0,
                "HttpsValue": 0
            }
        ]
    },
    "DataInterval": 300,
    "RequestId": "C2416D6C-B10A-474C-8FE8-0F9EF7ACA674",
    "EndTime": "2019-11-30T05:40:00Z",
    "StartTime": "2019-11-30T05:33:00Z"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

