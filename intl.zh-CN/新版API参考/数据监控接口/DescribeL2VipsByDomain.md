# DescribeL2VipsByDomain {#reference1049 .reference}

调用DescribeL2VipsByDomain按域名查询L2节点的回源IP。

**说明：** 

-   支持日峰值带宽为1Gbps以上的用户提工单申请该接口的调用权限，请单击[立即申请](https://workorder.console.aliyun.com/console.htm?lang=#/ticket/add?productCode=cdn)。
-   使用场景介绍，请参见[CDN的回源地址有哪些？](../../../../intl.zh-CN/.md)

## 调试 {#section_o7j_67t_u0f .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeL2VipsByDomain)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_wut_2zs_wk9 .section}

|参数|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeL2VipsByDomain。|
|DomainName|String|是|域名，取值范围： 只支持单个域名。|

## 返回参数 {#section_wg3_ic6_wgn .section}

|名称|类型|描述|
|--|--|--|
|DomainName|String|域名。|
|Vips|Vip\[\]|Vip列表。|

## 示例 {#section_3fm_gpn_noc .section}

请求示例

``` {#codeblock_ird_b8k_cxz}
https://cdn.aliyuncs.com?Action=DescribeL2VipsByDomain&DomainName=example.com&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_9np_kzn_zcc .language-json}
{
  "Vips": {
    "Vip": [
      "111.111.111.111/25",
      "112.112.112.112/25",
      "122.72.33.190/25",
      "119.14.96.109/25",
      "221.13.20.226/25",
      "124.95.19.140/25",
      "58.211.215.140/25"
    ]
  },
  "RequestId": "820E7900-5CA9-4AEF-B0DD-20ED5F64BE55",
  "DomainName": "example.com"
}
```

## 错误码 {#section_104_5ek_xm2 .section}

|错误代码|错误信息|HTTP 状态码|描述|
|----|----|--------|--|
|MissingParameter|The specified value of parameter "DomainName" can not be empty.|400|参数DomainName不能为空。|

