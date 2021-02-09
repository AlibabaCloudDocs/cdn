# DescribeRefreshQuota

Queries the maximum and remaining numbers of URLs and directories that can be refreshed, the maximum and remaining numbers of times that you can prefetch content, and the maximum and remaining numbers of URLs and directories that can be blocked on the current day.

**Note:**

-   You can call the RefreshObjectCaches operation to refresh content and call the PushObjectCache operation to prefetch content.
-   The maximum number of times that each user can call this operation per second is 20.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer automatically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeRefreshQuota&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeRefreshQuota|The operation that you want to perform. Set this parameter to **DescribeRefreshQuota**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|42E0554B-80F4-4921-AED6-ACFB22CAAAD0|The ID of the request |
|UrlQuota|String|2000|The maximum number of URLs that can be refreshed on the current day. |
|DirQuota|String|100|The maximum number of directories that can be refreshed on the current day. |
|UrlRemain|String|1996|The remaining number of URLs that can be refreshed on the current day. |
|DirRemain|String|99|The remaining number of directories that can be refreshed on the current day. |
|PreloadQuota|String|500|The maximum number of times that you can prefetch content to L2 nodes on the current day. |
|PreloadRemain|String|400|The remaining number of times that you can prefetch content to L2 nodes on the current day. |
|BlockQuota|String|300|The maximum number of URLs and directories that can be blocked on the current day. |
|BlockRemain|String|100|The remaining number of URLs and directories that can be blocked on the current day. |
|PreloadEdgeQuota|String|20|The maximum number of times that you can prefetch content to L1 nodes on the current day. |
|PreloadEdgeRemain|String|20|The remaining number of times that you can prefetch content to L1 nodes on the current day. |
|RegexQuota|String|20|The maximum number of times that you can use regular expressions to refresh directories or URLs on the current day. |
|RegexRemain|String|10|The remaining number of times that you can use regular expressions to refresh directories or URLs on the current day. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=DescribeRefreshQuota
&<Common request parameters>
```

Sample responses

`XML` format

```
<DescribeRefreshQuotaResponse>
      <RequestId>42E0554B-80F4-4921-AED6-ACFB22CAAAD0</RequestId>
	  <UrlQuota>2000</UrlQuota>
      <DirQuota>100</DirQuota>
      <UrlRemain>1996</UrlRemain>
	  <DirRemain>99</DirRemain>
	  <PreloadQuota>500</PreloadQuota>
	  <PreloadRemain>400</PreloadRemain>
      <BlockQuota>300</BlockQuota>
      <RegexQuota>20</RegexQuota>
      <RegexRemain>10</RegexRemain>
      <blockRemain>200</blockRemain>
</DescribeRefreshQuotaResponse>
```

`JSON` format

```
{
    "RequestId": "42E0554B-80F4-4921-AED6-ACFB22CAAAD0",
    "UrlQuota": 2000,
    "DirQuota": 100,
    "UrlRemain": 1996,
    "DirRemain": 99,
    "PreloadQuota": 500,
    "PreloadRemain": 400,
    "BlockQuota": 300,
    "RegexQuota": 20,
    "RegexRemain": 10,
    "blockRemain": 200
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

