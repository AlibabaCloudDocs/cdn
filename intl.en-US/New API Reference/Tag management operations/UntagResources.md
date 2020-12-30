# UntagResources

Removes tags from a resource.

**Note:** The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer automatically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=UntagResources&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|UntagResources|The operation that you want to perform. Set the value to **UntagResources**. |
|ResourceId.N|RepeatList|Yes|example.com|The ID of the resource. Valid values of N: **1** to **50**. |
|ResourceType|String|Yes|DOMAIN|The type of resource. The resource type. Set the value to **DOMAIN**. |
|TagKey.N|RepeatList|No|env|The key of the tag. Valid values of N: **1** to **20**. |
|All|Boolean|No|false|Specifies whether to delete all tags. Valid values:

-   **true**: yes.
-   **false**: no.

Default value: **false**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|97C68796-EB7F-4D41-9D5B-12B909D76508|The ID of the request. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=UntagResources
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

