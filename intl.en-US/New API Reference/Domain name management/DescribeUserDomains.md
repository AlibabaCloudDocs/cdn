# DescribeUserDomains

Queries all domain names accelerated by Alibaba Cloud Content Delivery Network \(CDN\) under your Alibaba Cloud account and the status of the accelerated domain names. You can filter domain names by name or status. Fuzzy match is supported.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeUserDomains&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description |
|---------|----|--------|-------|------------|
|Action|String|Yes|DescribeUserDomains|The operation that you want to perform. Set the value to **DescribeUserDomains**. |
|PageSize|Integer|No|5|The number of entries to return on each page. Valid value: **1 to 50**. Default value: **20**. Maximum value: **50**. |
|PageNumber|Integer|No|1|The number of the page to return. Valid values: **1** to **100000**. |
|DomainName|String|No|example.com|The domain name that is used as a keyword to filter domain names. Fuzzy match is supported.

 By default, you cannot use keywords to match the domain name. |
|DomainStatus|String|No|configure\_failed|The status of the domain name. You can filter domain names by status. Valid values:

 -   **online**: The domain name is enabled.
-   **offline**: The domain name is disabled.
-   **configuring**: The domain name is being configured.
-   **configure\_failed**: The domain name failed to be configured.
-   **checking**: The domain name is under review.
-   **check\_failed**: The domain name failed the review.
-   **stopping**: The domain name is suspended.
-   **deleting**: The domain name is being deleted.

 If you do not set this parameter, all states are queried. |
|DomainSearchType|String|No|fuzzy\_match|The search method. Valid values:

 -   **fuzzy\_match**: fuzzy match. This is the default value.
-   **pre\_match**: prefix match.
-   **suf\_match**: suffix match.
-   **full\_match**: exact match. |
|CdnType|String|No|download, web, video, video, video|The type of workload accelerated by Alibaba Cloud CDN. Separate multiple types with commas \(,\). Valid values:

 -   **web**: image and small file delivery.
-   **download**: large file delivery.
-   **video**: on-demand video and audio streaming.

 By default, all workload types are queried. |
|CheckDomainShow|Boolean|No|false|Specifies whether to display domain names that are under review, failed the review, and failed to be configured. Valid values: true and false. |
|ResourceGroupId|String|No|abcd1234abcd1234|The ID of the resource group.

 By default, all resource group IDs are queried. |
|ChangeStartTime|String|No|2019-10-10T12:14:55Z|The beginning of the time range to query. Specify the time in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|ChangeEndTime|String|No|2019-10-10T12:14:58Z|The end of the time range to query. Specify the time in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 The end time must be later than the start time. |
|Tag.N.Key|String|No|key|The tag key. Valid values of N: **1** to **20**.

 By default, all tag keys are queried. |
|Tag.N.Value|String|No|value|The tag value. Valid values of N: **1** to **20**.

 By default, all tag values are queried. |
|Coverage|String|No|domestic|The accelerated region. By default, all accelerated regions are queried. Valid values:

 -   **domestic**: accelerated regions in mainland China.
-   **global**: accelerated regions inside and outside mainland China.
-   **overseas**: accelerated regions outside mainland China. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Domains|Array of PageData| |The information about the accelerated domain name. |
|PageData| | | |
|CdnType|String|download|The type of workload accelerated by Alibaba Cloud CDN. Valid values:

 -   **web**: image and small file delivery.
-   **download**: large file delivery.
-   **video**: on-demand video and audio streaming. |
|Cname|String|example.com.w.alikunlun.net|The canonical name \(CNAME\) assigned to the accelerated domain name. |
|Coverage|String|domestic|The accelerated region. Valid values:

 -   **domestic**: accelerated regions in mainland China.
-   **global**: accelerated region inside and outside main China.
-   **overseas**: accelerated regions outside mainland China. |
|Description|String|audit failed|The reason why the accelerated domain name failed the review. |
|DomainName|String|example.com|The accelerated domain name. |
|DomainStatus|String|configure\_failed|The status of the accelerated domain name. Valid values:

 -   **online**: The domain name is enabled.
-   **offline**: The domain name is disabled.
-   **configuring**: The domain name is being configured.
-   **configure\_failed**: The domain name failed to be configured.
-   **checking**: The domain name is under review.
-   **check\_failed**: The domain name failed the review.
-   **stopping**: The domain name is suspended.
-   **deleting**: The domain name is being deleted. |
|GmtCreated|String|2015-10-28T09:32:51Z|The time when the accelerated domain name was added to Alibaba Cloud CDN. |
|GmtModified|String|2015-10-28T11:05:52Z|The last time when the accelerated domain name was modified. |
|ResourceGroupId|String|abcd1234abcd1234|The ID of the resource group. |
|Sandbox|String|normal|Indicates whether the accelerated domain name is in a sandbox. |
|Sources|Array of Source| |The information about the accelerated domain name. |
|Source| | | |
|Content|String|cdn.aliyuncs.com|The address of the origin server. |
|Port|Integer|80|The port of the origin server. |
|Priority|String|high|The priority of the origin server if multiple origin servers have been specified. |
|Type|String|oss|The type of the origin server. |
|Weight|String|weight|The weight of the origin server if multiple origin servers have been specified. |
|SslProtocol|String|on|The status of HTTPS.

 -   **on**: enabled
-   **off**: disabled |
|PageNumber|Long|1|The page number of the returned page. |
|PageSize|Long|5|The number of entries returned per page. |
|RequestId|String|AA75AADB-5E25-4970-B480-EAA1F5658483|The ID of the request. |
|TotalCount|Long|16|The total number of entries returned. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com?&Action=DescribeUserDomains
&PageNumber=1
&PageSize=5
&DomainSearchType=fuzzy_match
&Coverage=domestic
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeUserDomainsResponse>
  <PageNumber>1</PageNumber>
  <TotalCount>5</TotalCount>
  <PageSize>20</PageSize>
  <RequestId>BDA62CE4-3477-439A-B52E-D2D7C829D7C1</RequestId>
  <Domains>
        <PageData>
              <Cname>xxx.alikunlun.com</Cname>
              <Description></Description>
              <CdnType>web</CdnType>
              <ResourceGroupId>xxxklq4a</ResourceGroupId>
              <DomainStatus>online</DomainStatus>
              <SslProtocol>off</SslProtocol>
              <DomainName>xxx.com</DomainName>
              <Coverage>domestic</Coverage>
              <Sources>
                    <Source>
                          <Port>80</Port>
                          <Weight>15</Weight>
                          <Type>oss</Type>
                          <Content>xxx.oss-cn-hangzhou.aliyuncs.com</Content>
                          <Priority>20</Priority>
                    </Source>
              </Sources>
              <GmtModified>2019-09-11T15:03Z</GmtModified>
              <Sandbox></Sandbox>
              <GmtCreated>2019-09-10T06:11:11Z</GmtCreated>
        </PageData>
        <PageData>
              <Cname>xxxalikunlun.com</Cname>
              <Description>xxx-19</Description>
              <CdnType>download</CdnType>
              <ResourceGroupId>xxxrjyolklq4a</ResourceGroupId>
              <DomainStatus>online</DomainStatus>
              <SslProtocol>off</SslProtocol>
              <DomainName>xxxujia.com</DomainName>
              <Coverage>domestic</Coverage>
              <Sources>
                    <Source>
                          <Port>80</Port>
                          <Weight>10</Weight>
                          <Type>oss</Type>
                          <Content>xxx.oss-cn-hangzhou.aliyuncs.com</Content>
                          <Priority>20</Priority>
                    </Source>
              </Sources>
              <GmtModified>2019-07-10T13:19Z</GmtModified>
              <Sandbox></Sandbox>
              <GmtCreated>2019-07-10T03:07:14Z</GmtCreated>
        </PageData>
  </Domains>
</DescribeUserDomainsResponse>
```

`JSON` format

```
{
	"PageNumber": 1,
	"TotalCount": 5,
	"PageSize": 20,
	"RequestId": "BDA62CE4-3477-439A-B52E-D2D7C829D7C1",
	"Domains": {
		"PageData": [
			{
				"Cname": "xxx.alikunlun.com",
				"Description": "",
				"CdnType": "web",
				"ResourceGroupId": "xxxklq4a",
				"DomainStatus": "online",
				"SslProtocol": "off",
				"DomainName": "xxx.com",
				"Coverage":"domestic",
				"Sources": {
					"Source": [
						{
							"Port": 80,
							"Weight": "15",
							"Type": "oss",
							"Content": "xxx.oss-cn-hangzhou.aliyuncs.com",
							"Priority": "20"
						}
					]
				},
				"GmtModified": "2019-09-11T15:03Z",
				"Sandbox": "",
				"GmtCreated": "2019-09-10T06:11:11Z"
			},
			{
				"Cname": "xxxalikunlun.com",
				"Description": "xxx-19",
				"CdnType": "download",
				"ResourceGroupId": "xxxrjyolklq4a",
				"DomainStatus": "online",
				"SslProtocol": "off",
				"DomainName": "xxxujia.com",
				"Coverage":"domestic",
				"Sources": {
					"Source": [
						{
							"Port": 80,
							"Weight": "10",
							"Type": "oss",
							"Content": "xxx.oss-cn-hangzhou.aliyuncs.com",
							"Priority": "20"
						}
					]
				},
				"GmtModified": "2019-07-10T13:19Z",
				"Sandbox": "",
				"GmtCreated": "2019-07-10T03:07:14Z"
			}
		]
    }
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

