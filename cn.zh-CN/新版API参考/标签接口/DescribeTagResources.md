# DescribeTagResources {#reference_226964 .reference}

调用DescribeTagResources查询资源对应的标签。

## 请求参数 {#section_6j6_jy9_tjg .section}

|参数|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeTagResources。|
|ResourceId.N|String|是|资源ID，CDN为域名，N的取值范围为\[1, 50\]。|
|ResourceType|String|是|固定值：DOMAIN。|

## 示例 {#section_xr1_ch1_q5u .section}

请求示例

``` {#codeblock_9er_pet_ij2}
https://cdn.aliyuncs.com/?Action=DescribeTagResources
&ResourceId.1=example.com
&ResourceType=DOMAIN
&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_gu6_skx_8b0}
{
  "TagResources": [
    {
      "ResourceId": "example.com",
      "Tag": [
        {
          "Value": "product",
          "Key": "env"
        }
      ]
    }
  ],
  "RequestId": "34AB41F1-04A5-496F-8C8D-634BDBE6A9FB"
}
```

