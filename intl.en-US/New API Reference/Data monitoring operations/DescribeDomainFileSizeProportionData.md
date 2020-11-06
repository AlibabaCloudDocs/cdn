# DescribeDomainFileSizeProportionData

Queries the proportions of file sizes. The data is collected at an interval of one hour. You can query data collected within the last 90 days.

**When you call this operation, note that:**

-   If you do not set StartTime or EndTime, data collected within the last 24 hours is queried. If you set both StartTime and EndTime, data collected within the specified time range is queried.
-   The maximum number of times that each user can call this operation per second is 10.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainFileSizeProportionData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainFileSizeProportionData|The operation that you want to perform. Set the value to **DescribeDomainFileSizeProportionData**. |
|DomainName|String|Yes|test.test.com|The accelerated domain name. You can specify only one domain name. |
|StartTime|String|No|2019-12-31T01:00:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the YYYY-MM-DDThh:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2019-12-31T02:00:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 The end time must be later than the start time. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DataInterval|String|3600|The time interval between the data entries. Unit: seconds. |
|DomainName|String|test.test.com|The accelerated domain name. |
|StartTime|String|2019-12-31T01:00:00Z|The beginning of the time range that was queried. |
|EndTime|String|2019-12-31T02:00:00Z|The end of the time range that was queried. |
|RequestId|String|23ACE7E2-2302-42E3-98F8-E5E697FD86C3|The ID of the request. |
|FileSizeProportionDataInterval|Array of UsageData| |The number of queries per second at each interval. |
|UsageData| | | |
|TimeStamp|String|2019-12-31T01:00:00Z|The timestamp of the data. |
|Value|Array of FileSizeProportionData| |The proportions of file sizes. |
|FileSizeProportionData| | | |
|FileSize|String|<50K|The file size range. |
|Proportion|String|0.01|The proportion of the file size. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeDomainFileSizeProportionData
&DomainName=test.com
&StartTime=2019-12-31T01:00:00Z
&EndTime=2019-12-31T02:00:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainFileSizeProportionDataResponse>
  <DataInterval>3600</DataInterval>
  <RequestId>2609901D-9AE1-43A4-83C7-75AC76A7FAB3</RequestId>
  <FileSizeProportionDataInterval>
        <UsageData>
              <TimeStamp>2019-12-31T01:00:00Z</TimeStamp>
              <Value>
                    <FileSizeProportionData>
                          <FileSize>&lt;5K</FileSize>
                          <Proportion>56.71</Proportion>
                    </FileSizeProportionData>
                    <FileSizeProportionData>
                          <FileSize>&lt;10K</FileSize>
                          <Proportion>14.17</Proportion>
                    </FileSizeProportionData>
                    <FileSizeProportionData>
                          <FileSize>&lt;20K</FileSize>
                          <Proportion>7.46</Proportion>
                    </FileSizeProportionData>
                    <FileSizeProportionData>
                          <FileSize>&lt;50K</FileSize>
                          <Proportion>3.73</Proportion>
                    </FileSizeProportionData>
                    <FileSizeProportionData>
                          <FileSize>&lt;100K</FileSize>
                          <Proportion>2.98</Proportion>
                    </FileSizeProportionData>
                    <FileSizeProportionData>
                          <FileSize>&lt;1M</FileSize>
                          <Proportion>7.46</Proportion>
                    </FileSizeProportionData>
                    <FileSizeProportionData>
                          <FileSize>&gt;1M</FileSize>
                          <Proportion>7.46</Proportion>
                    </FileSizeProportionData>
              </Value>
        </UsageData>
        <UsageData>
              <TimeStamp>2019-12-31T02:00:00Z</TimeStamp>
              <Value>
                    <FileSizeProportionData>
                          <FileSize>&lt;5K</FileSize>
                          <Proportion>61.11</Proportion>
                    </FileSizeProportionData>
                    <FileSizeProportionData>
                          <FileSize>&lt;10K</FileSize>
                          <Proportion>14.44</Proportion>
                    </FileSizeProportionData>
                    <FileSizeProportionData>
                          <FileSize>&lt;20K</FileSize>
                          <Proportion>7.77</Proportion>
                    </FileSizeProportionData>
                    <FileSizeProportionData>
                          <FileSize>&lt;50K</FileSize>
                          <Proportion>2.22</Proportion>
                    </FileSizeProportionData>
                    <FileSizeProportionData>
                          <FileSize>&lt;100K</FileSize>
                          <Proportion>2.22</Proportion>
                    </FileSizeProportionData>
                    <FileSizeProportionData>
                          <FileSize>&lt;1M</FileSize>
                          <Proportion>6.66</Proportion>
                    </FileSizeProportionData>
                    <FileSizeProportionData>
                          <FileSize>&gt;1M</FileSize>
                          <Proportion>5.55</Proportion>
                    </FileSizeProportionData>
              </Value>
        </UsageData>
  </FileSizeProportionDataInterval>
  <DomainName>test.test.com</DomainName>
  <EndTime>2019-12-31T02:00:00Z</EndTime>
  <StartTime>2019-12-31T01:00:00Z</StartTime>
</DescribeDomainFileSizeProportionDataResponse>
```

`JSON` format

```
{
	"DataInterval": "3600",
	"RequestId": "2609901D-9AE1-43A4-83C7-75AC76A7FAB3",
	"FileSizeProportionDataInterval": {
		"UsageData": [
			{
				"TimeStamp": "2019-12-31T01:00:00Z",
				"Value": {
					"FileSizeProportionData": [
						{
							"FileSize": "<5K",
							"Proportion": "56.71"
						},
						{
							"FileSize": "<10K",
							"Proportion": "14.17"
						},
						{
							"FileSize": "<20K",
							"Proportion": "7.46"
						},
						{
							"FileSize": "<50K",
							"Proportion": "3.73"
						},
						{
							"FileSize": "<100K",
							"Proportion": "2.98"
						},
						{
							"FileSize": "<1M",
							"Proportion": "7.46"
						},
						{
							"FileSize": ">1M",
							"Proportion": "7.46"
						}
					]
				}
			},
			{
				"TimeStamp": "2019-12-31T02:00:00Z",
				"Value": {
					"FileSizeProportionData": [
						{
							"FileSize": "<5K",
							"Proportion": "61.11"
						},
						{
							"FileSize": "<10K",
							"Proportion": "14.44"
						},
						{
							"FileSize": "<20K",
							"Proportion": "7.77"
						},
						{
							"FileSize": "<50K",
							"Proportion": "2.22"
						},
						{
							"FileSize": "<100K",
							"Proportion": "2.22"
						},
						{
							"FileSize": "<1M",
							"Proportion": "6.66"
						},
						{
							"FileSize": ">1M",
							"Proportion": "5.55"
						}
					]
				}
			}
		]
	},
	"DomainName": "test.test.com",
	"EndTime": "2019-12-31T02:00:00Z",
	"StartTime": "2019-12-31T01:00:00Z"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|MissingParameter|StartTime and EndTime can not be single.|The error message returned because both the StartTime and EndTime parameters must be set.|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|The error message returned because the format of the specified start time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|The error message returned because the format of the end time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Mismatch|Specified EndTime does not math the specified start time.|The error message returned because the end time must be later than the start time.|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|The error message returned because the specified start time is not supported.|
|400|InvalidDomainName.ValueNotSupported|The specified value of parameter DomainName only support one or empty value.|The error message returned because you can specify at most one accelerated domain name for the DomainName parameter.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

