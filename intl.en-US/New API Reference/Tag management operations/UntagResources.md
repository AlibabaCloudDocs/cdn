# UntagResources

Removes tags from a resource.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=UntagResources&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|UntagResources|The operation that you want to perform. Set the value to **UntagResources**. |
|ResourceId.N|RepeatList|Yes|example.com|The ID of the resource from which the specified tags are removed. Specify an accelerated domain name as the resource ID. Valid values of N: **1** to **50**. |
|ResourceType|String|Yes|DOMAIN|The resource type. Set the value to **DOMAIN**. |
|TagKey.N|RepeatList|Yes|2|The key of the tag. Valid values of N: **1** to **20**. |
|RegionId|String|No|ch-shanghai|The ID of the region where your CDN service is deployed. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|97C68796-EB7F-4D41-9D5B-12B909D76508|The ID of the request. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com/?Action=UntagResoruces
&ResourceId.1=example.com
&ResourceType=DOMAIN
&TagKey.1=env
&<Common request parameters>
```

Sample success responses

`XML` format

```
<UntagResourcesResponse>	
      <RequestId>97C68796-EB7F-4D41-9D5B-12B909D76508</RequestId>
</UntagResourcesResponse>
```

`JSON` format

```
{
"RequestId":"97C68796-EB7F-4D41-9D5B-12B909D76508"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

