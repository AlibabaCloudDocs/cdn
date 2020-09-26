---
keyword: [common request parameters, CDN]
---

# Common request parameters

Common parameters include common request parameters and common response parameters. To send an Alibaba Cloud Content Delivery Network \(CDN\) API request, you must send an HTTP GET request to the Alibaba Cloud CDN endpoint. You must add the request parameters that correspond to the API operation being called. After you call the API, the system returns a response.

## Common request parameters

**Note:** The following code has been formatted to improve readability.

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Format|String|No|The format in which to return the response. Valid values: JSON and XML. Default value: XML.|
|Version|String|Yes|The version number of the API. Specify the version number in the YYYY-MM-DD format. Set the value to 2018-05-10.|
|AccessKeyId|String|Yes|The AccessKey ID provided to you by Alibaba Cloud.|
|Signature|String|Yes|The signature string of the current request. For more information, see [Signature method](/intl.en-US/New API Reference/Signature method.md).|
|SignatureMethod|String|Yes|The encryption method of the signature string. Set the value to HMAC-SHA1.|
|Timestamp|String|Yes|The timestamp of the request. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. Example: 2018-05-10T12:00:00Z, which represents 20:00:00 on Thursday, May 10, 2018 \(UTC+8\). |
|SignatureVersion|String|Yes|The version of the signature encryption algorithm. Set the value to 1.0.|
|SignatureNonce|String|Yes|A unique, random number used to prevent replay attacks. You must use different numbers for different requests.|

Sample requests

```
https://cdn.aliyuncs.com/?Format=xml
&Version=2018-05-10
&Signature=Pc5WB8gokVn0xfeu%2FZV%2BiNM1dgI%3D
&SignatureMethod=HMAC-SHA1
&SignatureNonce=15215528852396&SignatureVersion=1.0
&AccessKeyId=key-test
&Timestamp=2018-05-10T12:00:00Z    
```

## Common response parameters

API responses use the HTTP response format where a 2XX status code indicates a successful call and a 4XX or 5XX status code indicates a failed call. Responses can be returned in either the JSON or XML format. You can specify the response format in the request. The default response format is XML.

Every response returns a unique RequestID regardless of whether the call is successful.

Sample responses in XML format

```
<? xml version="1.0" encoding="utf-8"? > 
    <!—Result Root Node-->
    <Operation Name+Response>
        <!—Request ID-->
        <RequestId>4C467B38-3910-447D-87BC-AC049166F216</RequestId>
        <!-Response Data-->
    </Operation Name+Response>
```

Sample responses in JSON format

```
{
    "RequestId":"4C467B38-3910-447D-87BC-AC049166F216",
    /*Response Data*/
    }
```

A 4xx or 5xx status code indicates a failed call. The request ID, host ID, error code, and error message are returned to you.

You can troubleshoot the error based on the error code. For more information, see [Error codes](https://error-center.alibabacloud.com). Alternatively, you can [submit a ticket](https://workorder-intl.console.aliyun.com/#/ticket/createIndex) and provide additional inputs such as the host ID and request ID to request technical support from Alibaba Cloud.

Sample responses in XML format

```
<? xml version=”1.0” encoding=”UTF-8”? >
<Error><RequestId>8906582E-6722-409A-A6C4-0E7863B733A5</RequestId>   
<HostId>cdn.aliyuncs.com</HostId>   
<Code>OperationDenied</Code>   
<Message>The specified action is not supported. </Message></Error>
```

Sample responses in JSON format

```
{    
“RequestId”: “8906582E-6722-409A-A6C4-0E7863B733A5”,    
“HostId”: “cdn.aliyuncs.com”,    
“Code”: “OperationDenied”,    
“Message”: “The specified action is not supported.”
}
```

