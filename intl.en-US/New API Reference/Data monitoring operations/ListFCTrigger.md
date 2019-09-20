# ListFCTrigger {#doc_api_Cdn_ListFCTrigger .reference}

You can call this operation to query the Function Compute triggers for an event.

## Debugging {#api_explorer .section}

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=ListFCTrigger&type=RPC&version=2018-05-10)

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|EventMetaName|String|Yes|LogFileCreated| The name of the event to query Function Compute triggers for.

 |
|EventMetaVersion|String|Yes|1.0.0| The version of the event to query Function Compute triggers for.

 |
|Action|String|No|ListFCTrigger| The operation that you want to perform. Set the value to **ListFCTrigger**.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|FCTriggers|N/A|N/A| The Function Compute triggers returned.

 |
|EventMetaName|String|LogFileCreated| The name of the event for which the Function Compute triggers were queried.

 |
|EventMetaVersion|String|1.0.0| The version of the event for which the Function Compute triggers were queried.

 |
|Notes|String|Test| The additional information.

 |
|RoleARN|String|acs:cdn:\*:1234567890:domain/example.com| The assigned RAM role.

 |
|SourceArn|String|acs:ram:: 1234567890:role/aliyuncdneventnotificationrole| The resources and filters for event listening.

 |
|TriggerARN|String|acs:fc:cn-beijing: 1234567890:services/FCTestService/functions/printEvent/triggers/testtrigger| The triggers corresponding to the Function Compute service.

 |
|RequestId|String|EC046C5D-8CB4-4B6B-B7F8-B335E51EF90E| The ID of the request.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}
https://cdn.aliyuncs.com?Action=ListFCTrigger
&EventMetaName=LogFileCreated
&EventMetaVersion=1.0.0
&<Common request parameters>
```

Sample success responses

`XML` format

``` {#xml_return_success_demo}
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

``` {#json_return_success_demo}
{
	"FCTriggers":[
		{
			"Notes":"Test",
			"SourceArn":"acs:cdn:*:1234567890:domain/example.com",
			"EventMetaName":"LogFileCreated",
			"EventMetaVersion":"1.0.0",
			"RoleARN":"acs:ram:: 1234567890:role/aliyuncdneventnotificationrole",
			"TriggerARN":"acs:fc:cn-beijing: 1234567890:services/FCTestService/functions/printEvent/triggers/testtrigger"
		}
	],
	"RequestId":"EC046C5D-8CB4-4B6B-B7F8-B335E51EF90E"
}
```

**SourceArn**format: **acs:cdn:\{RegionID\}:\{AccountID\}:\{Filter\}**

where, **Filter** indicates the resource and filter in the format of **\{FilterName\}/\{FilterValue\}**. If multiple values are returned for **FilterValue**, the values are enclosed with braces **\{\}** and are separated with commas \(,\).

In this example, the LogFileCreated event supports a filter of which **FilterName** is set to **domain**. Function Compute can only be triggered by **example.com** if **Filter** is **domain/example.com**. Function Compute can be triggered by multiple domains if **Filter** is **domain/\{example1.com,example2.com\}**.

If multiple filters are returned, they are separated with forward slashes \(/\) and have **logical AND** relations. In this case, the SourceArn parameter is displayed in the format of **acs:cdn:\{RegionID\}:\{AccountID\}:\{Filter1\}/\{Filter2\}...**.

## Error codes {#section_bv0_4c6_k0j .section}

For more information about error codes, visit [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

