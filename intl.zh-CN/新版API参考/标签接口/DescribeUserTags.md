# DescribeUserTags {#reference_226979 .reference}

调用DescribeUserTags查询用户标签。

## 请求参数 {#section_6j6_jy9_t .section}

|参数|类型|必要|描述|
|--|--|--|--|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeUserTags。|

## 示例 {#section_xr1_ch1_q .section}

请求示例

``` {#codeblock_9er_pet_ij2}
https://cdn.aliyuncs.com/?Action=DescribeUserTags
&<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_gu6_skx_8b0}
{
  "Tags": [
    {
      "Key": "env",
      "Value": [
        "product",
        "pre",
        "daily"
      ]
    },
    {
      "Key": "region",
      "Value": [
        "hangzhou"
      ]
    }
  ],
  "RequestId": "34AB41F1-04A5-496F-8C8D-634BDBE6A9FB"
}
```

