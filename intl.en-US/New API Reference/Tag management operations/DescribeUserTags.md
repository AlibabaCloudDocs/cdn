# DescribeUserTags

Queries user tags.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeUserTags&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeUserTags|The operation that you want to perform. Set the value to **DescribeUserTags**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|34AB41F1-04A5-496F-8C8D-634BDBE6A9FB|The ID of the request. |
|Tags|Array of Tag| |The list of tags returned. |
|Key|String|env|The key of the tag. |
|Value|List|product|The value of the tag. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com/?Action=DescribeUserTags
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeUserTagsResponse>
	  <Tags>
		    <Key>env</Key>
		    <Value>product</Value>
		    <Value>pre</Value>
		    <Value>daily</Value>
	  </Tags>
	  <Tags>
		    <Key>region</Key>
		    <Value>hangzhou</Value>
	  </Tags>
	  <RequestId>34AB41F1-04A5-496F-8C8D-634BDBE6A9FB</RequestId>
</DescribeUserTagsResponse>
```

`JSON` format

```
{
  "Tags": [
    {
      "Key": "env",
      "Value": [
        "product",
        "pre",
        "daily"
      ]
    },
    {
      "Key": "region",
      "Value": [
        "hangzhou"
      ]
    }
  ],
  "RequestId": "34AB41F1-04A5-496F-8C8D-634BDBE6A9FB"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

