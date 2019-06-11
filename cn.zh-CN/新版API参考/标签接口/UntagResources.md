# UntagResources {#reference_227196 .reference}

调用UntagResources删除资源标签接口。

## 请求参数 {#section_2xo_paw_3b3 .section}

|参数|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数，取值：UntagResources。|
|ResourceId.N|String|是|资源ID，CDN为域名，N的取值范围为\[1, 50\]。|
|ResourceType|String|是|固定值：DOMAIN。|
|TagKey.N|String|是|标签键。N的取值范围为\[1, 20\]。|

## 示例 {#section_8x0_3ze_91y .section}

请求示例

``` {#codeblock_ejv_757_6k7}
https://cdn.aliyuncs.com/?Action=UntagResoruces
&ResourceId.1=example.com
&ResourceType=DOMAIN
&TagKey.1=env
&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_q9j_i35_z7n}
{
"RequestId":"97C68796-EB7F-4D41-9D5B-12B909D76508"
}
```

