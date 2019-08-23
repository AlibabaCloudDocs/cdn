# DescribeCdnRegionAndIsp {#reference_jzn_5lp_yfb .reference}

You can call the DescribeCdnRegionAndIsp operation to query the list of regions and Internet Service Providers \(ISPs\).

## Debugging {#section_ll5_ct2_es8 .section}

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#/?product=Cdn&api=DescribeCdnRegionAndIsp) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#section_yhw_dvx_dgb .section}

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Action|String |Yes|The operation that you want to perform. Set this parameter to DescribeCdnRegionAndIsp.|

## Response parameters {#section_esl_fvx_dgb .section}

|Parameter|Type|Description|
|---------|----|-----------|
|NameZh|String |The Chinese name of the region or ISP.|
|NameEn|String|The English name of the region or ISP.|

## Examples {#section_r1b_hvx_dgb .section}

Sample request

``` {#codeblock_cip_ens_0si}
http://cdn.aliyuncs.com?Action=DescribeCdnRegionAndIsp&<Common request parameters>
```

Sample success response

`JSON` format

``` {#codeblock_o96_74o_g13}
{
  "Isps": {
    "Isp": [
      {
        "NameZh": "联通",
        "NameEn": "unicom"
      },
      {
        "NameZh": "铁通",
        "NameEn": "tietong"
      },
      {
        "NameZh": "电信",
        "NameEn": "telecom"
      },
      {
        "NameZh": "教育网",
        "NameEn": "cernet"
      },
      {
        "NameZh": "鹏博士",
        "NameEn": "drpeng"
      },
      {
        "NameZh": "移动",
        "NameEn": "mobile"
      }
    ]
  },
  "RequestId": "2387C335-932C-4E1E-862C-1C4363B6DE72",
  "Regions": {
    "Region": [
      {
        "NameZh": "辽宁省",
        "NameEn": "liaoning"
      },
      {
        "NameZh": "广西壮族自治区",
        "NameEn": "guangxi"
      },
      {
        "NameZh": "安徽省",
        "NameEn": "anhui"
      },
      {
        "NameZh": "宁夏回族自治区",
        "NameEn": "ningxia"
      },
      {
        "NameZh": "江西省",
        "NameEn": "jiangxi"
      },
      {
        "NameZh": "广东省",
        "NameEn": "guangdong"
      },
      {
        "NameZh": "内蒙古自治区",
        "NameEn": "neimenggu"
      },
      {
        "NameZh": "澳门特别行政区",
        "NameEn": "aomen"
      },
      {
        "NameZh": "江苏省",
        "NameEn": "jiangsu"
      },
      {
        "NameZh": "天津市",
        "NameEn": "tianjin"
      },
      {
        "NameZh": "重庆市",
        "NameEn": "chongqing"
      },
      {
        "NameZh": "吉林省",
        "NameEn": "jilin"
      },
      {
        "NameZh": "陕西省",
        "NameEn": "shaanxi"
      },
      {
        "NameZh": "上海市",
        "NameEn": "shanghai"
      },
      {
        "NameZh": "四川省",
        "NameEn": "sichuan"
      },
      {
        "NameZh": "云南省",
        "NameEn": "yunnan"
      },
      {
        "NameZh": "香港特别行政区",
        "NameEn": "xianggang"
      },
      {
        "NameZh": "台湾省",
        "NameEn": "taiwan"
      },
      {
        "NameZh": "山东省",
        "NameEn": "shandong"
      },
      {
        "NameZh": "西藏自治区",
        "NameEn": "xizang"
      },
      {
        "NameZh": "河北省",
        "NameEn": "hebei"
      },
      {
        "NameZh": "青海省",
        "NameEn": "qinghai"
      },
      {
        "NameZh": "甘肃省",
        "NameEn": "gansu"
      },
      {
        "NameZh": "新疆维吾尔自治区",
        "NameEn": "xinjiang"
      },
      {
        "NameZh": "黑龙江省",
        "NameEn": "heilongjiang"
      },
      {
        "NameZh": "山西省",
        "NameEn": "shanxi"
      },
      {
        "NameZh": "海南省",
        "NameEn": "hainan"
      },
      {
        "NameZh": "浙江省",
        "NameEn": "zhejiang"
      },
      {
        "NameZh": "河南省",
        "NameEn": "henan"
      },
      {
        "NameZh": "福建省",
        "NameEn": "fujian"
      },
      {
        "NameZh": "贵州省",
        "NameEn": "guizhou"
      },
      {
        "NameZh": "湖北省",
        "NameEn": "hubei"
      },
      {
        "NameZh": "湖南省",
        "NameEn": "hunan"
      },
      {
        "NameZh": "北京市",
        "NameEn": "beijing"
      }
    ]
  }
}
```

