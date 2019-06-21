# DescribeUserVipsByDomain {#reference_778236 .reference}

调用DescribeUserVipsByDomain按域名查询vip列表。

## 请求参数 {#section_7f3_45h_gmc .section}

|参数|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeUserVipsByDomain。|
|DomainName|String|是|域名，取值范围： 只支持单个域名。|
|Available|String|是|取值：on或者off。 -   on：健康vip。
-   off：全部vip。

 |

## 返回参数 {#section_lkz_pni_jbo .section}

|名称|类型|描述|
|--|--|--|
|DomainName|String|域名。|
|Vips|Vip\[\]|Vip列表。|
|RequestID|String|请求ID。|

## 示例 {#section_p5j_gws_6rh .section}

请求示例

正常返回示例

``` {#codeblock_hp7_zzb_du4}
https://cdn.aliyuncs.com?Action=DescribeUserVipsByDomain&Available=on&DomainName=example.com&<公共请求参数>
```

`JSON`格式

``` {#codeblock_ta5_cto_6qy}
{
  "Vips": {
    "Vip": [
      "122.72.xxx.xxx",
      "119.14.xxx.xxx",
      "221.13.xxx.xxx",
      "124.95.xxx.xxx",
      "58.211.xxx.xxx"
    ]
  },
  "RequestId": "820E7900-5CA9-4AEF-B0DD-20ED5F64BE55",
  "DomainName": "example.com"
}
```

## 特定错误码 {#section_b04_m9l_ija .section}

|ErrorCode 错误码|Message 错误信息|HTTP 返回码|语义|
|-------------|------------|--------|--|
|MissingParameter|The specified value of parameter "DomainName" can not be empty.|400|参数DomainName不能为空。|

CDN所有API错误码，详情请参见[CDN错误码](https://error-center.aliyun.com/status/product/Cdn)。

