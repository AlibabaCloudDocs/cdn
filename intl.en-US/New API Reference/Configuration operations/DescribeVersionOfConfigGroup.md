# DescribeVersionOfConfigGroup

Queries the version of a configuration group.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeVersionOfConfigGroup&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeVersionOfConfigGroup|The operation that you want to perform.

 Set the value to **DescribeVersionOfConfigGroup**. |
|ConfigGroupId|String|No|12345\*\*\*|The ID of the configuration group.

 **Note:** You must set at least one of the following parameters: **ConfigGroupId** and **ConfigGroupName**. |
|ConfigGroupName|String|No|testConfigGroupName|The name of the configuration group.

 **Note:** You must set at least one of the following parameters: **ConfigGroupId** and **ConfigGroupName**. |
|PageIndex|Integer|No|1|The number of the page to return. Default value: **1**. |
|PageSize|Integer|No|20|The number of entries to return on each page. Default value: **20**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Contents|Array of Content| |The content of the configuration group. |
|BaseSeqId|Long|123456|The number of the basic version. |
|BaseVersionId|String|654\*\*\*|The ID of the basic version. |
|ConfigGroupId|String|789\*\*\*|The ID of the configuration group. |
|CreateTime|String|2019-09-26T10:25:02+08:00|The time when the configuration group was created. |
|Description|String|test|The description of the version. |
|Operator|String|Tom|The user who performed the operation. |
|Production|String|active|The status of the production environment. |
|SeqId|Long|123|The number of the version. |
|Staging|String|active|The status of the staging environment. |
|Status|String|deactive|The status of the configuration group. |
|UpdateTime|String|2019-09-26T10:25:02+08:00|The last time when the configuration group was updated. |
|VersionId|String|123\*\*\*|The ID of the version. |
|PageIndex|Integer|1|The number of the returned page. |
|PageSize|Integer|500|The number of entries returned per page. |
|RequestId|String|15C66C7B-671A-4297-9137-2C4477247B78|The ID of the request. |
|TotalCount|Integer|1|The total number of pages returned. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=DescribeVersionOfConfigGroup
&ConfigGroupId=12345***
&ConfigGroupName=testConfigGroupName
&PageIndex=1
&PageSize=20
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeVersionOfConfigGroupResponse>
  <RequestId>15C66C7B-671A-4297-9137-2C4477247B78</RequestId>
  <Contents>
        <VersionId>xxId</VersionId>
        <ConfigGroupId>123</ConfigGroupId>
        <BaseVersionId>123</BaseVersionId>
        <seqId>xxIdx</seqId>
        <BaseSeqId>xxId</BaseSeqId>
        <Description>test</Description>
        <Status>deactive</Status>
        <Operator>Tom</Operator>
        <CreateTime>2019-09-26T10:25:02+08:00</CreateTime>
        <UpdateTime>2019-09-26T10:25:02+08:00</UpdateTime>
  </Contents>
  <PageIndex>1</PageIndex>
  <PageSize>500</PageSize>
  <TotalCount>1</TotalCount>
</DescribeVersionOfConfigGroupResponse>
```

`JSON` format

```
{
      "RequestId":"15C66C7B-671A-4297-9137-2C4477247B78",
       "Contents":  [
              {
                  "VersionId": "123***",
                  "ConfigGroupId": "789***",
                  "BaseVersionId": "654***",
                  "seqId": 123,
                  "BaseSeqId": 123456,
                  "Description": "test",
                  "Status": "deactive",
                  "Operator": "Tom",
                  "CreateTime": "2019-09-26T10:25:02+08:00",
                  "UpdateTime": "2019-09-26T10:25:02+08:00"
              }
           ],
          "PageIndex": 1,
          "PageSize": 500,
          "TotalCount": 1
       }
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

