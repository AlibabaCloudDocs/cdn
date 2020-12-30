# TagResources

Adds tags to a resource.

**Note:** The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer automatically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=TagResources&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|TagResources|The operation that you want to perform. Set the value to **TagResources**. |
|ResourceId.N|RepeatList|Yes|example.com|The ID of the resource. Valid values of N: **1** to **50**. |
|ResourceType|String|Yes|DOMAIN|The type of resource. The resource type. Set the value to **DOMAIN**. |
|Tag.N.Key|String|Yes|env|The key of the tag. Valid values of N: **1** to **20**. |
|Tag.N.Value|String|No|value|The value of the tag. Valid values of N: **1** to **20**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|97C68796-EB7F-4D41-9D5B-12B909D76508|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=TagResources
&ResourceId.1=example.com
&ResourceType=DOMAIN
&Tag.1.Key=env
&Tag.1.Value=''
&<Common request parameters>
```

Sample success responses

`XML` format

```
<TagResourcesResponse>
	  <RequestId>97C68796-EB7F-4D41-9D5B-12B909D76508</RequestId>
</TagResourcesResponse>
```

`JSON` format

```
{
"RequestId":"97C68796-EB7F-4D41-9D5B-12B909D76508"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

