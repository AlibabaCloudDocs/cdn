# ListRealtimeLogDeliveryDomains

Queries all domain names that are associated with a specific real-time log delivery feature.

You can call this operation up to 100 times per second with each account.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=ListRealtimeLogDeliveryDomains&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ListRealtimeLogDeliveryDomains|The operation that you want to perform. Set the value to **ListRealtimeLogDeliveryDomains**. |
|Logstore|String|Yes|LogstoreName|The name of the Logstore that collects log data from Alibaba Cloud Content Delivery Network \(CDN\) in real time. You can specify multiple Logstore names and separate them with commas \(,\). |
|Project|String|Yes|ProjectName|The name of the Log Service project that is used for real-time log delivery. You can specify multiple project names and separate them with commas \(,\). |
|Region|String|Yes|ch-shanghai|The ID of the region where the Log Service project is deployed. You can specify multiple region IDs and separate them with commas \(,\).

 For more information about regions, see [Regions that support real-time log delivery](~~144883~~). |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Content|Array| |The information about the accelerated domain name that was returned. |
|Domains| | | |
|DomainName|String|example.com|The accelerated domain name that was returned. |
|Status|String|online|The status of the feature. Valid values:

 -   **online**: The feature is enabled.
-   **offline**: The feature is disabled. |
|RequestId|String|95D5B69F-8AEC-419B-8F3A-612B35032B0D|The ID of the request. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com/?Action=ListRealtimeLogDeliveryDomains
&Project=testProject
&Logstore=testLogstore
&Region=ch-shanghai
```

Sample success responses

`XML` format

```
<ListRealtimeLogDeliveryDomainsResponse>
	  <Content>
		    <Domains>
			      <DomainName>a.xxx.com</DomainName>
			      <Status>online</Status>
		    </Domains>
		    <Domains>
			      <DomainName>b.xxx.com</DomainName>
			      <Status>offline</Status>
		    </Domains>
	  </Content>
	  <RequestId>95D5B69F-8AEC-419B-8F3A-612B35032B0D</RequestId>
</ListRealtimeLogDeliveryDomainsResponse>
```

`JSON` format

```
{
    "Content":{
        "Domains":[
            {   
                "DomainName":"a.xxx.com",
                "Status":"online"
            },
            {   
                "DomainName":"b.xxx.com",
                "Status":"offline"
            }
        ]
    },
    "RequestId":"95D5B69F-8AEC-419B-8F3A-612B35032B0D"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

