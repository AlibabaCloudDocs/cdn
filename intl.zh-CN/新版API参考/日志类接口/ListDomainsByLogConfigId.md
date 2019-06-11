# ListDomainsByLogConfigId {#reference3345 .reference}

调用ListDomainsByLogConfigId查询应用某自定义日志格式的所有域名列表。

## 调试 {#section_ry9_u94_x6i .section}

前往【[API Explorer](https://api.aliyun.com/#/?product=Cdn&api=ListDomainsByLogConfigId)】在线调试，API Explorer提供在线调用API、动态生成SDK Example代码和快速检索接口等能力，能显著降低使用云API的难度，强烈推荐使用。

## 请求参数 {#section_ubn_32b_mgb .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：ListDomainsByLogConfigId。|
|ConfigId|String|是|自定义配置ID。|

## 返回参数 {#section_fcn_32b_mgb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|Domains|List|域名。|

## 示例 {#section_zcn_32b_mgb .section}

请求示例

``` {#codeblock_yfk_0ob_lbf}
https://cdn.aliyuncs.com?Action=ListDomainsByLogConfigId&ConfigId=9732E117-8A37-49FD-A36F-ABBB87556CA7&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_8jt_yuo_agk}
{
    "RequestId": "9732E117-8A37-49FD-A36F-ABBB87556CA7",
    "Domains": {
        "Domain": [
            "example1.com",
            "example.com",
             ...
        ]
    }
}
```

## 错误码 {#section_sqb_hfb_mgb .section}

|错误码|错误信息|HTTP 状态码|描述|
|:--|:---|:-------|:-|
|Domains.NotFound|No domain used in this log config or the configId provided does not belong to you.|404|没有域名应用于此配置。|
|InvalidConfigId|Illegal ConfigId|403|非法的ConfigId。|

