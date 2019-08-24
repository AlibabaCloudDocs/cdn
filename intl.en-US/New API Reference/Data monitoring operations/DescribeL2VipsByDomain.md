# DescribeL2VipsByDomain {#reference1049 .reference}

You can call the DescribeL2VipsByDomain operation to query the origin IP addresses of L2 nodes by domain name.

## Debugging {#section_o7j_67t_u0f .section}

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeL2VipsByDomain) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#section_wut_2zs_wk9 .section}

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Action|String|Yes|The operation that you want to perform. Set this parameter to DescribeL2VipsByDomain.|
|DomainName|String|Yes|The domain name you want to query. You can specify only one domain name.|

## Response parameters {#section_wg3_ic6_wgn .section}

|Parameter|Type|Description|
|---------|----|-----------|
|DomainName|String|The domain name information.|
|Vips|Vip\[\]|The list of origin IP addresses.|

## Examples {#section_3fm_gpn_noc .section}

Sample request

``` {#codeblock_ird_b8k_cxz}
https://cdn.aliyuncs.com?Action=DescribeL2VipsByDomain&DomainName=example.com&<Common request parameters>
```

Sample success response

`JSON` format

``` {#codeblock_9np_kzn_zcc .language-json}
{
  "Vips": {
    "Vip": [
      "111.111.111.xxx/25",
      "112.112.112.xxx/25",
      "122.72.33.xxx/25",
      "119.14.96.xxx/25",
      "221.13.20.xxx/25",
      "124.95.19.xxx/25",
      "58.211.215.xxx/25"
    ]
  },
  "RequestId": "820E7900-5CA9-4AEF-B0DD-20ED5F64BE55",
  "DomainName": "example.com"
}
```

## Error codes {#section_104_5ek_xm2 .section}

|Error code|Error message|HTTP status code|Description|
|----------|-------------|----------------|-----------|
|MissingParameter|The specified value of parameter "DomainName" can not be empty.|400|The error message returned because the DomainName parameter cannot be blank.|

