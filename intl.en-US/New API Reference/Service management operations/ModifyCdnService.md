# ModifyCdnService {#reference_llj_4bt_vdb .reference}

You can call the ModifyCdnService operation to change the billing method of the CDN service.

CDN supports the following billing methods:

-   Pay by peak bandwidth
-   Pay by data transfer

**Note:** 

-   To call this operation, make sure that the CDN service is activated.
-   The new billing method takes effect at 00:00 the following day. If you change the billing method multiple times, the most recent change takes effect.

## Debugging {#section_3t7_wdr_tyf .section}

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#/?product=Cdn&api=ModifyCdnService) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#section_udw_bqn_cgb .section}

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Action|String |Yes|The operation that you want to perform. Set this parameter to ModifyCdnService.|
|InternetChargeType|String |Yes|The new billing method. Valid values: PayByTraffic and PayByBandwidth.|

## Response parameters {#section_zp9_g9h_5rw .section}

|Parameter|Type|Description|
|:--------|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_sz4_ctt_vdb .section}

Sample request

``` {#codeblock_jt2_kxs_skt}
https://cdn.aliyuncs.com?&Action=ModifyCdnService&InternetChargeType=PayByTraffic&<Common request parameters>
```

Sample success response

`JSON` format

``` {#codeblock_1si_5fc_4nc}
{
"RequestId":"97C68796-EB7F-4D41-9D5B-12B909D76508"
}
```

## Error codes {#section_rr2_nqn_cgb .section}

|Error code|Error message|HTTP status code|Description|
|:---------|:------------|:---------------|:----------|
|OperationDenied|Your account does not open CDN service yet.|403|The error message returned because CDN has not been activated for your account.|
|InvalidParameter|The specified value of parameter parameter name is not valid.|400|The error message returned because the specified parameters are invalid.|
|InsufficientBalance|Your account does not have enough balance.|400|The error message returned because your account balance is insufficient.|
|Forbidden.NotVerified|Your account is not verified yet.|403|The error message returned because your account is not verified.|

