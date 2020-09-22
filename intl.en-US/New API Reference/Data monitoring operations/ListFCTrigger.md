# ListFCTrigger

Queries the Function Compute trigger set for an Alibaba Cloud Content Delivery Network \(CDN\) event.

The maximum number of times that each user can call this operation per second is 100.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=ListFCTrigger&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|ListFCTrigger|The operation that you want to perform. Set the value to **ListFCTrigger**. |
|EventMetaName|String|Yes|LogFileCreated|The name of the event for which the Function Compute trigger is set. You can specify only one name. |
|EventMetaVersion|String|Yes|1.0.0|The version number of the event. You can specify only one version number. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|FCTriggers|Array| |The information about the Function Compute trigger. |
|EventMetaName|String|LogFileCreated|The name of the event. |
|EventMetaVersion|String|1.0.0|The version of the event. |
|Notes|String|Test|The remarks. |
|RoleARN|String|acs:cdn:\*:1234567890:domain/example.com|The Resource Access Management \(RAM\) role. |
|SourceArn|String|acs:ram:: 1234567890:role/aliyuncdneventnotificationrole|The resources and filters for event listening. |
|TriggerARN|String|acs:fc:cn-beijing: 1234567890:services/FCTestService/functions/printEvent/triggers/testtrigger|The Function Compute trigger. |
|RequestId|String|EC046C5D-8CB4-4B6B-B7F8-B335E51EF90E|The ID of the request. |

The format of the **SourceARN** parameter is:

```
acs:cdn:{RegionID}:{AccountID}:{Filter}
```

where **Filter** indicates the resource and filter in the format of **\{FilterName\}/\{FilterValue\}**. If multiple values are returned for **FilterValue**, the values are enclosed with braces **\{\}** and separated with commas \(,\).

For example, the LogFileCreated event supports a filter of which **FilterName** is set to **domain**. Function Compute can be triggered only by **example.com** if **Filter** is set to **domain/example.com**. Function Compute can be triggered by multiple domains if **Filter** is set to:

```
domain/{example1.com,example2.com}
```

Separate multiple filters with forward slashes \(/\) and set the logical operator between the filters to **AND**. In this case, the format of SourceARN is:

```
acs:cdn:{RegionID}:{AccountID}:{Filter1}/{Filter2}...
```

## Examples

Sample requests

```
https://cdn.aliyuncs.com/?Action=ListFCTrigger
&EventMetaName=LogFileCreated
&EventMetaVersion=1.0.0
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ListFCTriggerResponse>
      <FCTriggers>
            <Notes>Test</Notes>
            <SourceArn>acs:cdn:*:1234567890:domain/example.com</SourceArn>
            <EventMetaVersion>1.0.0</EventMetaVersion>
            <EventMetaName>LogFileCreated</EventMetaName>
            <RoleARN>acs:ram:: 1234567890:role/aliyuncdneventnotificationrole</RoleARN>
            <TriggerARN>acs:fc:cn-beijing: 1234567890:services/FCTestService/functions/printEvent/triggers/testtrigger</TriggerARN>
      </FCTriggers>
      <RequestId>EC046C5D-8CB4-4B6B-B7F8-B335E51EF90E</RequestId>
</ListFCTriggerResponse>
```

`JSON` format

```
{
  "FCTriggers": [
    {
      "Notes":"Test",
      "SourceArn": "acs:cdn:*:1234567890:domain/example.com",
      "EventMetaVersion": "1.0.0",
      "EventMetaName": "LogFileCreated",
      "RoleARN": "acs:ram:: 1234567890:role/aliyuncdneventnotificationrole",
      "TriggerARN": "acs:fc:cn-beijing: 1234567890:services/FCTestService/functions/printEvent/triggers/testtrigger"
    }
  ],
  "RequestId": "EC046C5D-8CB4-4B6B-B7F8-B335E51EF90E"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

