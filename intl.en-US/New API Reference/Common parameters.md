# Common parameters {#concept_ak3_cyz_xfb .concept}

Common parameters include common request parameters and common response parameters. You can call a CDN API operation by sending an HTTP GET request to the endpoint of the CDN API. When you call an operation, you need to set the request parameters according to the corresponding parameter descriptions. The system then returns a response after processing the request.

## Common request parameters {#section_k11_njj_pgb .section}

**Note:** The sample requests are presented in an easy-to-read form in this document.

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Format|String|No|The format of the returned value. Valid values: JSON and XML. Default value: XML.|
|Version|String|Yes|The API version in a date format of YYYY-MM-DD. The current version is 2018-05-10.|
|AccessKeyId|String|Yes|The AccessKey ID provided to you by Alibaba Cloud.|
|Signature|String|Yes|The signature string. For more information about the signature calculation method, see [Sign RPC APIs](../../../../intl.en-US/Alibaba Cloud API/Signature/Sign RPC APIs.md#).|
|SignatureMethod|String |Yes|The algorithm that is used to calculate the request signature. Only HMAC-SHA1 is supported.|
|Timestamp|String|Yes|The timestamp of the request. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. Example: 2018-05-10T12:00:00Z \(for 12:00:00 on Thursday, May 10, 2018 Beijing Time\).|
|SignatureVersion|String |Yes|The version of the signature algorithm. The current version is 1.0.|
|SignatureNonce|String|Yes|A unique number that is randomly generated to prevent network replay attacks. A different random number is required for each request.|

Sample request

``` {#codeblock_3tm_ks6_vll}
https://cdn.aliyuncs.com/?Format=xml
&Version=2018-05-10
&Signature=Pc5WB8gokVn0xfeu%2FZV%2BiNM1dgI%3D
&SignatureMethod=HMAC-SHA1
&SignatureNonce=15215528852396&SignatureVersion=1.0
&AccessKeyId=key-test
&Timestamp=2018-05-10T12:00:00Z    
```

## Common response parameters {#section_6f0_82x_zcl .section}

All API responses use the same format. If a 2XX HTTP status code is returned, the call is successful. If a 4xx or 5xx HTTP status code is returned, the call is failed. The result can be returned in JSON or XML format. You can specify the format of the returned data when sending an API request. The result is returned in XML format by default.

Each time you send a request to call an operation, the system returns a unique identifier RequestId, regardless of whether the request is successful or not.

Sample response in XML format

``` {#codeblock_xvr_srd_gjr}
<? xml version="1.0" encoding="utf-8"? > 
    <!-Response root node-->
    <Operation + Response>
        <!-The request ID-->
        <RequestId>4C467B38-3910-447D-87BC-AC049166F216</RequestId>
        <!-The response data-->
    </Operation + Response>
```

Sample response in JSON format

``` {#codeblock_gn7_pz5_wc1}
{
    "RequestId":"4C467B38-3910-447D-87BC-AC049166F216",
    /*The response data*/
    }
```

If a 4xx or 5xx HTTP status code is returned, the call has failed. The request ID, host ID, error code, and error message are returned to you.

You can troubleshoot the error according to the error code. For more information, see [Error codes](https://error-center.aliyun.com/status/product/Cdn). Alternatively, you can [submit a ticket](https://workorder-intl.console.aliyun.com/#/ticket/createIndex) and provide additional inputs such as the host ID and request ID to get technical support from us.

Sample response in XML format

``` {#codeblock_tvv_22r_w54}
<? xml version="1.0" encoding="UTF-8"? >
<Error><RequestId>8906582E-6722-409A-A6C4-0E7863B733A5</RequestId>   
<HostId>cdn.aliyuncs.com</HostId>   
<Code>OperationDenied</Code>   
<Message>The specified action is not supported. </Message></Error>
```

Sample response in JSON format

``` {#codeblock_3t5_lb5_oll}
{    
"RequestId": "8906582E-6722-409A-A6C4-0E7863B733A5",    
"HostId": "cdn.aliyuncs.com",    
“Code”: “OperationDenied”,    
"Message": "The specified action is not supported."
}
```

