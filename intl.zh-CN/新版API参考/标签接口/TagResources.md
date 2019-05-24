# TagResources {#reference_226991 .reference}

资源打标接口。

## 请求参数 {#section_6j6_jy9 .section}

|参数|类型|必要|描述|
|--|--|--|--|
|Action|String|是|操作接口名，系统规定参数，取值：TagResources。|
|ResourceId.N|String|是|资源ID，CDN为域名，N的取值范围为\[1, 50\]。|
|ResourceType|String|是|固定值：DOMAIN。|
|Tag.N.Key|String|是|标签键。N的取值范围为\[1, 20\]。|
|Tag.N.Value|String|否|标签键。N的取值范围为\[1, 20\]。|

## 示例 {#section_xr1_ch1 .section}

请求示例

``` {#codeblock_9er_pet_ij2}
https://cdn.aliyuncs.com/?Action=TagResoruces
&ResourceId.1=example.com
&ResourceType=DOMAIN
&Tag.1.Key=env
&Tag.1.Value=''
&<公共请求参数>
```

返回示例

JSON格式：

``` {#codeblock_gu6_skx_8b0}
{
"RequestId":"97C68796-EB7F-4D41-9D5B-12B909D76508"
}
```

