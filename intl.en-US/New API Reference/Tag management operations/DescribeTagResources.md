# DescribeTagResources

Queries the tags of resources.

The maximum number of times that each user can call this operation per second is 10.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeTagResources&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeTagResources|The operation that you want to perform. Set the value to **DescribeTagResources**. |
|ResourceId.N|RepeatList|Yes|example.com|The ID of the resource that you want to query. Specify an accelerated domain name as the resource ID. Valid values of N: **1** to **50**. |
|ResourceType|String|Yes|DOMAIN|The resource type. Set the value to **DOMAIN**. |
|Tag.N.Key|String|No|key|The key of the tag. Valid values of N: **1** to **20**. |
|Tag.N.Value|String| No|value|The value of the tag. Valid values of N: **1** to **20**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|34AB41F1-04A5-496F-8C8D-634BDBE6A9FB|The ID of the request. |
|TagResources|Array| |The tags that are attached to the specified resource. |
|ResourceId|String|example.com|The ID of the resource. |
|Tag|Array| |The key-value pair of the tag. |
|Key|String|env|The key of the tag. |
|Value|String|product|The value of the tag. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com/?Action=DescribeTagResources
&ResourceId.1=example.com
&ResourceType=DOMAIN
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeTagResourcesResponse>
	  <TagResources>
		    <ResourceId>example.com</ResourceId>
		    <Tag>
			      <Value>product</Value>
			      <Key>env</Key>
		    </Tag>
	  </TagResources>
	  <RequestId>34AB41F1-04A5-496F-8C8D-634BDBE6A9FB</RequestId>
</DescribeTagResourcesResponse>
```

`JSON` format

```
{
  "TagResources": [
    {
      "ResourceId": "example.com",
      "Tag": [
        {
          "Value": "product",
          "Key": "env"
        }
      ]
    }
  ],
  "RequestId": "34AB41F1-04A5-496F-8C8D-634BDBE6A9FB"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

