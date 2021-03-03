# DescribeDomainRealTimeBpsData

Queries the bandwidth information about one or more accelerated domain names. The data is collected every minute.

**Note:**

-   You can query data collected within the last seven days. The time range specified by the **StartTime** and **EndTime** parameters cannot exceed 24 hours in each call.
-   If you do not set **StartTime** or **EndTime**, data collected within the last one hour is queried.
-   The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer automatically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainRealTimeBpsData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainRealTimeBpsData|The operation that you want to perform. Set the value to **DescribeDomainRealTimeBpsData**. |
|DomainName|String|Yes|example.com|The accelerated domain name. You can specify one or more accelerated domain names. Separate multiple accelerated domain names with commas \(,\).

 **Note:** You can specify at most 500 accelerated domain names in each call. |
|IspNameEn|String|No|telecom|The name of the Internet service provider \(ISP\) for your Alibaba Cloud Content Delivery Network \(DCDN\) service.

 You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query ISP names. If you do not set this parameter, all ISPs are queried. |
|LocationNameEn|String|No|beijing|The name of the region.

 You can call the [DescribeCdnRegionAndIsp](~~91077~~) operation to query the most recent region list. If you do not set this parameter, all regions are queried. |
|StartTime|String|No|2019-11-30T05:33:00Z|The beginning of the time range to query.

 Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2019-11-30T05:40:00Z|The end of the time range to query.

 Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 **Note:** The end time must be later than the start time. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Data|Array of BpsModel| |The bandwidth information about the accelerated domain names. |
|BpsModel| | | |
|Bps|Float|16710625.733333332|The bandwidth value. Unit: bit/s. |
|TimeStamp|String|2019-11-30T05:41:00Z|The timestamp of the data entry. The time follows the ISO 8601 standard in the yyyy-MM-ddThh:mmZ format. The time is displayed in UTC. |
|RequestId|String|B49E6DDA-F413-422B-B58E-2FA23F286726|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=DescribeDomainRealTimeBpsData
&DomainName=example.com
&EndTime=2019-11-30T05:40:00Z
&StartTime=2019-11-30T05:33:00Z
&IspNameEn=telecom
&LocationNameEn=beijing
&<common request parameters>
```

Sample responses

`XML` format

```
<DescribeDomainRealTimeBpsDataResponse>
  <Data>
        <BpsModel>
              <TimeStamp>2019-11-30T05:41:00Z</TimeStamp>
              <Bps>16710625.733333332</Bps>
        </BpsModel>
        <BpsModel>
              <TimeStamp>2019-11-30T05:42:00Z</TimeStamp>
              <Bps>59392614.8</Bps>
        </BpsModel>
  </Data>
  <RequestId>B49E6DDA-F413-422B-B58E-2FA23F286726</RequestId>
</DescribeDomainRealTimeBpsDataResponse>
```

`JSON` format

```
{
   "Data":{
      "BpsModel":[
         {
            "TimeStamp":"2019-11-30T05:41:00Z",
            "Bps":16710625.733333332
         },
         {
            "TimeStamp":"2019-11-30T05:42:00Z",
            "Bps":59392614.8
         }
      ]
   },
   "RequestId":"B49E6DDA-F413-422B-B58E-2FA23F286726"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidTime.Malformed|Specified StartTime or EndTime is malformed.|The error message returned because the format of the specified start time or end time is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

