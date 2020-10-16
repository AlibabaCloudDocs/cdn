# DescribeCdnUserQuota

Queries the quotas and usage of Alibaba Cloud Content Delivery Network \(CDN\) resources under your Alibaba Cloud account.

The maximum number of times that each user can call this operation per second is 30.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeCdnUserQuota&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCdnUserQuota|The operation that you want to perform. Set the value to **DescribeCdnUserQuota**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|BlockQuota|Integer|100|The maximum number of URLs and directories that can be blocked. |
|BlockRemain|Integer|100|The remaining number of URLs and directories that can be blocked. |
|DomainQuota|Integer|50|The maximum number of accelerated domain names that can be added to Alibaba Cloud CDN. |
|PreloadQuota|Integer|500|The maximum number of URLs that can be prefetched. |
|PreloadRemain|Integer|100|The remaining number of URLs that can be prefetched. |
|RefreshDirQuota|Integer|100|The maximum number of directories that can be refreshed. |
|RefreshDirRemain|Integer|500|The remaining number of directories that can be refreshed. |
|RefreshUrlQuota|Integer|2000|The maximum number of URLs that can be refreshed. |
|RefreshUrlRemain|Integer|2000|The remaining number of URLs that can be refreshed. |
|RequestId|String|BFFCDFAD-DACC-484E-9BE6-0AF3B3A0DD23|The ID of the request. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com?&Action=DescribeCdnUserQuota
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeCdnUserQuotaResponse>
    <PreloadRemain>500</PreloadRemain>
    <RefreshUrlRemain>2000</RefreshUrlRemain>
    <DomainQuota>50</DomainQuota>
    <RefreshDirRemain>100</RefreshDirRemain>
    <RequestId>EF4F084A-2F49-4E1C-9CA0-DC85BCE7F391</RequestId>
    <BlockRemain>100</BlockRemain>
    <RefreshUrlQuota>2000</RefreshUrlQuota>
    <BlockQuota>100</BlockQuota>
    <PreloadQuota>500</PreloadQuota>
    <RefreshDirQuota>100</RefreshDirQuota>
</DescribeCdnUserQuotaResponse>
```

`JSON` format

```
{
	"PreloadRemain": 500,
	"RefreshUrlRemain": 2000,
	"DomainQuota": 50,
	"RefreshDirRemain": 100,
	"RequestId": "EF4F084A-2F49-4E1C-9CA0-DC85BCE7F391",
	"BlockRemain": 100,
	"RefreshUrlQuota": 2000,
	"BlockQuota": 100,
	"PreloadQuota": 500,
	"RefreshDirQuota": 100
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

