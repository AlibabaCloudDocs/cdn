# DescribeCdnRegionAndIsp

Queries Internet service providers \(ISPs\) and regions that are supported by Alibaba Cloud Content Delivery Network \(CDN\).

**When you call this operation, take note of the following information:**

-   The lists of ISPs and regions that are supported by Alibaba Cloud CDN are updated and published on the Alibaba Cloud International site.
-   The maximum number of times that each user can call this operation per second is 30.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer automatically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeCdnRegionAndIsp&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCdnRegionAndIsp|The operation that you want to perform. Set the value to **DescribeCdnRegionAndIsp**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|Isps|Array of Isp| |The list of ISPs. |
|Isp| | | |
|NameEn|String|unicom|The English name of the region. |
|NameZh|String|联通|The Chinese name of the ISP. |
|Regions|Array of Region| |The list of regions. |
|Region| | | |
|NameEn|String|liaoning|The English name of the region. |
|NameZh|String|辽宁省|The Chinese name of the region. |
|RequestId|String|2387C335-932C-4E1E-862C-1C4363B6DE72|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com?Action=DescribeCdnRegionAndIsp
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeCdnRegionAndIspResponse>
  <Isps>
        <Isp>
              <NameZh>电信</NameZh>
              <NameEn>telecom</NameEn>
        </Isp>
        <Isp>
              <NameZh>移动</NameZh>
              <NameEn>mobile</NameEn>
        </Isp>
        <Isp>
              <NameZh>教育网</NameZh>
              <NameEn>cernet</NameEn>
        </Isp>
        <Isp>
              <NameZh>铁通</NameZh>
              <NameEn>tietong</NameEn>
        </Isp>
        <Isp>
              <NameZh>其他</NameZh>
              <NameEn>other</NameEn>
        </Isp>
        <Isp>
              <NameZh>鹏博士</NameZh>
              <NameEn>drpeng</NameEn>
        </Isp>
        <Isp>
              <NameZh>联通</NameZh>
              <NameEn>unicom</NameEn>
        </Isp>
        <Isp>
              <NameZh>阿里巴巴</NameZh>
              <NameEn>alibaba</NameEn>
        </Isp>
        <Isp>
              <NameZh>中信网络</NameZh>
              <NameEn>citic</NameEn>
        </Isp>
        <Isp>
              <NameZh>方正宽带</NameZh>
              <NameEn>dounder</NameEn>
        </Isp>
        <Isp>
              <NameZh>海外ISP</NameZh>
              <NameEn>overseas</NameEn>
        </Isp>
        <Isp>
              <NameZh>有线通</NameZh>
              <NameEn>ocn</NameEn>
        </Isp>
        <Isp>
              <NameZh>华数</NameZh>
              <NameEn>wasu</NameEn>
        </Isp>
        <Isp>
              <NameZh>湖北广电</NameZh>
              <NameEn>hrtn</NameEn>
        </Isp>
        <Isp>
              <NameZh>重庆有线</NameZh>
              <NameEn>cqccn</NameEn>
        </Isp>
        <Isp>
              <NameZh>歌华有线</NameZh>
              <NameEn>bjctv</NameEn>
        </Isp>
        <Isp>
              <NameZh>天威视讯</NameZh>
              <NameEn>topway</NameEn>
        </Isp>
        <Isp>
              <NameZh>中国香港宽频</NameZh>
              <NameEn>hkbn</NameEn>
        </Isp>
        <Isp>
              <NameZh>澳大利亚电信</NameZh>
              <NameEn>telstra</NameEn>
        </Isp>
        <Isp>
              <NameZh>江西广电</NameZh>
              <NameEn>jxsarft</NameEn>
        </Isp>
        <Isp>
              <NameZh>湖南广电</NameZh>
              <NameEn>gbs</NameEn>
        </Isp>
        <Isp>
              <NameZh>中国澳门电讯</NameZh>
              <NameEn>ctm</NameEn>
        </Isp>
        <Isp>
              <NameZh>黑龙江广电</NameZh>
              <NameEn>ljwl</NameEn>
        </Isp>
        <Isp>
              <NameZh>中华电信</NameZh>
              <NameEn>cht</NameEn>
        </Isp>
        <Isp>
              <NameZh>陕西广电</NameZh>
              <NameEn>sxbctv</NameEn>
        </Isp>
        <Isp>
              <NameZh>广电</NameZh>
              <NameEn>ccn</NameEn>
        </Isp>
        <Isp>
              <NameZh>长城宽带</NameZh>
              <NameEn>gwbn</NameEn>
        </Isp>
        <Isp>
              <NameZh>华数传媒</NameZh>
              <NameEn>wasumedia</NameEn>
        </Isp>
        <Isp>
              <NameZh>广东广电</NameZh>
              <NameEn>gcable</NameEn>
        </Isp>
        <Isp>
              <NameZh>辽宁广电</NameZh>
              <NameEn>lnsarft</NameEn>
        </Isp>
        <Isp>
              <NameZh>河南广电</NameZh>
              <NameEn>hensarft</NameEn>
        </Isp>
        <Isp>
              <NameZh>山东广电</NameZh>
              <NameEn>sdsarft</NameEn>
        </Isp>
        <Isp>
              <NameZh>江苏广电</NameZh>
              <NameEn>jssarft</NameEn>
        </Isp>
        <Isp>
              <NameZh>四川艾普</NameZh>
              <NameEn>aipu</NameEn>
        </Isp>
        <Isp>
              <NameZh>吉视传媒</NameZh>
              <NameEn>jilincatv</NameEn>
        </Isp>
        <Isp>
              <NameZh>四川广电</NameZh>
              <NameEn>sicsarft</NameEn>
        </Isp>
        <Isp>
              <NameZh>安徽广电</NameZh>
              <NameEn>anhuicatv</NameEn>
        </Isp>
        <Isp>
              <NameZh>福建广电</NameZh>
              <NameEn>fujiancatv</NameEn>
        </Isp>
        <Isp>
              <NameZh>新疆广电</NameZh>
              <NameEn>xjsarft</NameEn>
        </Isp>
        <Isp>
              <NameZh>贵州广电</NameZh>
              <NameEn>guizhoucatv</NameEn>
        </Isp>
        <Isp>
              <NameZh>局域网</NameZh>
              <NameEn>local area network</NameEn>
        </Isp>
        <Isp>
              <NameZh>湖南巨亚</NameZh>
              <NameEn>hunanjy</NameEn>
        </Isp>
        <Isp>
              <NameZh>珠江数码</NameZh>
              <NameEn>zhujiangsm</NameEn>
        </Isp>
        <Isp>
              <NameZh>北京宝联之星</NameZh>
              <NameEn>baolian</NameEn>
        </Isp>
        <Isp>
              <NameZh>印尼Telin</NameZh>
              <NameEn>telin</NameEn>
        </Isp>
        <Isp>
              <NameZh>印尼Indosat</NameZh>
              <NameEn>indosat</NameEn>
        </Isp>
        <Isp>
              <NameZh>上海驰联</NameZh>
              <NameEn>shchilian</NameEn>
        </Isp>
        <Isp>
              <NameZh>上海企舜</NameZh>
              <NameEn>shqishun</NameEn>
        </Isp>
        <Isp>
              <NameZh>皓宽网络</NameZh>
              <NameEn>cnix</NameEn>
        </Isp>
        <Isp>
              <NameZh>印度Sify</NameZh>
              <NameEn>sify</NameEn>
        </Isp>
        <Isp>
              <NameZh>印尼Zenlayer</NameZh>
              <NameEn>zenlayer</NameEn>
        </Isp>
        <Isp>
              <NameZh>印度TATA</NameZh>
              <NameEn>tata</NameEn>
        </Isp>
        <Isp>
              <NameZh>印度Airtel</NameZh>
              <NameEn>airtel</NameEn>
        </Isp>
        <Isp>
              <NameZh>Telstra Global</NameZh>
              <NameEn>telstraglobal</NameEn>
        </Isp>
        <Isp>
              <NameZh>Maxis</NameZh>
              <NameEn>maxis</NameEn>
        </Isp>
        <Isp>
              <NameZh>内蒙古广电</NameZh>
              <NameEn>nmgcatv</NameEn>
        </Isp>
        <Isp>
              <NameZh>JasTel</NameZh>
              <NameEn>jastel</NameEn>
        </Isp>
        <Isp>
              <NameZh>Taiwan Fixed Network</NameZh>
              <NameEn>taiwanfixednetwork</NameEn>
        </Isp>
        <Isp>
              <NameZh>Digital United</NameZh>
              <NameEn>digitalunited</NameEn>
        </Isp>
        <Isp>
              <NameZh>NTT</NameZh>
              <NameEn>ntt</NameEn>
        </Isp>
        <Isp>
              <NameZh>KDDI</NameZh>
              <NameEn>kddi</NameEn>
        </Isp>
        <Isp>
              <NameZh>Korea Telecom</NameZh>
              <NameEn>koreatelecom</NameEn>
        </Isp>
        <Isp>
              <NameZh>TM Net</NameZh>
              <NameEn>tmnet</NameEn>
        </Isp>
        <Isp>
              <NameZh>True Internet</NameZh>
              <NameEn>trueinternet</NameEn>
        </Isp>
        <Isp>
              <NameZh>PT Aplikanusa Lintasarta</NameZh>
              <NameEn>ptaplikanusalintasarta</NameEn>
        </Isp>
        <Isp>
              <NameZh>VNPT</NameZh>
              <NameEn>vnpt</NameEn>
        </Isp>
        <Isp>
              <NameZh>EITC-DU</NameZh>
              <NameEn>eitcdu</NameEn>
        </Isp>
        <Isp>
              <NameZh>Rostelecom</NameZh>
              <NameEn>rostelecom</NameEn>
        </Isp>
        <Isp>
              <NameZh>GLOBALNET</NameZh>
              <NameEn>globalnet</NameEn>
        </Isp>
        <Isp>
              <NameZh>ER-Telecom Holding</NameZh>
              <NameEn>ertelecomholding</NameEn>
        </Isp>
        <Isp>
              <NameZh>Business Network Ltd</NameZh>
              <NameEn>businessnetworkltd</NameEn>
        </Isp>
        <Isp>
              <NameZh>Vodafone</NameZh>
              <NameEn>vodafone</NameEn>
        </Isp>
        <Isp>
              <NameZh>Level</NameZh>
              <NameEn>level</NameEn>
        </Isp>
        <Isp>
              <NameZh>TATA Communications(America)</NameZh>
              <NameEn>tatacommunications</NameEn>
        </Isp>
        <Isp>
              <NameZh>ENTER S.r.l. </NameZh>
              <NameEn>entersrl</NameEn>
        </Isp>
        <Isp>
              <NameZh>Vodacom ENS</NameZh>
              <NameEn>vodacomens</NameEn>
        </Isp>
        <Isp>
              <NameZh>Hurricane Electric</NameZh>
              <NameEn>hurricaneelectric</NameEn>
        </Isp>
        <Isp>
              <NameZh>CTA</NameZh>
              <NameEn>cta</NameEn>
        </Isp>
        <Isp>
              <NameZh>Telefonica USA</NameZh>
              <NameEn>telefonicausa</NameEn>
        </Isp>
        <Isp>
              <NameZh>Verizon Business</NameZh>
              <NameEn>verizonbusiness</NameEn>
        </Isp>
        <Isp>
              <NameZh>Telefonica Data S.A.</NameZh>
              <NameEn>telefonicadatasa</NameEn>
        </Isp>
        <Isp>
              <NameZh>PLDT</NameZh>
              <NameEn>pldt</NameEn>
        </Isp>
        <Isp>
              <NameZh>Viettel</NameZh>
              <NameEn>viettel</NameEn>
        </Isp>
        <Isp>
              <NameZh>RETN</NameZh>
              <NameEn>retn</NameEn>
        </Isp>
        <Isp>
              <NameZh>AIMS</NameZh>
              <NameEn>aims</NameEn>
        </Isp>
        <Isp>
              <NameZh>广西广电</NameZh>
              <NameEn>guangxsarft</NameEn>
        </Isp>
        <Isp>
              <NameZh>河北广电</NameZh>
              <NameEn>hebsarft</NameEn>
        </Isp>
        <Isp>
              <NameZh>湖南有线</NameZh>
              <NameEn>hunsarft</NameEn>
        </Isp>
        <Isp>
              <NameZh>山东青岛广电</NameZh>
              <NameEn>sdqdsarft</NameEn>
        </Isp>
        <Isp>
              <NameZh>Level3</NameZh>
              <NameEn>level3</NameEn>
        </Isp>
        <Isp>
              <NameZh>宁夏广电</NameZh>
              <NameEn>nxsarft</NameEn>
        </Isp>
        <Isp>
              <NameZh>Zain</NameZh>
              <NameEn>zain</NameEn>
        </Isp>
        <Isp>
              <NameZh>Singtel</NameZh>
              <NameEn>singtel</NameEn>
        </Isp>
        <Isp>
              <NameZh>BBIX</NameZh>
              <NameEn>bbix</NameEn>
        </Isp>
        <Isp>
              <NameZh>MSK-IX</NameZh>
              <NameEn>mskix</NameEn>
        </Isp>
        <Isp>
              <NameZh>TPIX</NameZh>
              <NameEn>tpix</NameEn>
        </Isp>
        <Isp>
              <NameZh>Equinix</NameZh>
              <NameEn>equinix</NameEn>
        </Isp>
        <Isp>
              <NameZh>中国台湾之星</NameZh>
              <NameEn>taiwanstar</NameEn>
        </Isp>
        <Isp>
              <NameZh>阿里云</NameZh>
              <NameEn>aliyun</NameEn>
        </Isp>
        <Isp>
              <NameZh>TelekomMalaysia</NameZh>
              <NameEn>telekommalaysia</NameEn>
        </Isp>
        <Isp>
              <NameZh>KINX</NameZh>
              <NameEn>kinx</NameEn>
        </Isp>
        <Isp>
              <NameZh>SKBB</NameZh>
              <NameEn>skbb</NameEn>
        </Isp>
        <Isp>
              <NameZh>CAT</NameZh>
              <NameEn>cat</NameEn>
        </Isp>
        <Isp>
              <NameZh>Ooredoo</NameZh>
              <NameEn>ooredoo</NameEn>
        </Isp>
        <Isp>
              <NameZh>Fareastone</NameZh>
              <NameEn>fareastone telecom</NameEn>
        </Isp>
        <Isp>
              <NameZh>全部</NameZh>
              <NameEn>all</NameEn>
        </Isp>
        <Isp>
              <NameZh>JIO</NameZh>
              <NameEn>jio</NameEn>
        </Isp>
        <Isp>
              <NameZh>甘肃广电</NameZh>
              <NameEn>gssarft</NameEn>
        </Isp>
        <Isp>
              <NameZh>天津广电</NameZh>
              <NameEn>tjsarft</NameEn>
        </Isp>
        <Isp>
              <NameZh>大连理工大学</NameZh>
              <NameEn>dlut</NameEn>
        </Isp>
  </Isps>
  <RequestId>9CEF1678-CAE9-4173-88C9-31DA0931BBAF</RequestId>
  <Regions>
        <Region>
              <NameZh>河北省</NameZh>
              <NameEn>hebei</NameEn>
        </Region>
        <Region>
              <NameZh>宁夏回族自治区</NameZh>
              <NameEn>ningxia</NameEn>
        </Region>
        <Region>
              <NameZh>贵州省</NameZh>
              <NameEn>guizhou</NameEn>
        </Region>
        <Region>
              <NameZh>新疆维吾尔自治区</NameZh>
              <NameEn>xinjiang</NameEn>
        </Region>
        <Region>
              <NameZh>北京市</NameZh>
              <NameEn>beijing</NameEn>
        </Region>
        <Region>
              <NameZh>福建省</NameZh>
              <NameEn>fujian</NameEn>
        </Region>
        <Region>
              <NameZh>海南省</NameZh>
              <NameEn>hainan</NameEn>
        </Region>
        <Region>
              <NameZh>黑龙江省</NameZh>
              <NameEn>heilongjiang</NameEn>
        </Region>
        <Region>
              <NameZh>广东省</NameZh>
              <NameEn>guangdong</NameEn>
        </Region>
        <Region>
              <NameZh>广西壮族自治区</NameZh>
              <NameEn>guangxi</NameEn>
        </Region>
        <Region>
              <NameZh>浙江省</NameZh>
              <NameEn>zhejiang</NameEn>
        </Region>
        <Region>
              <NameZh>青海省</NameZh>
              <NameEn>qinghai</NameEn>
        </Region>
        <Region>
              <NameZh>江苏省</NameZh>
              <NameEn>jiangsu</NameEn>
        </Region>
        <Region>
              <NameZh>山西省</NameZh>
              <NameEn>shanxi</NameEn>
        </Region>
        <Region>
              <NameZh>河南省</NameZh>
              <NameEn>henan</NameEn>
        </Region>
        <Region>
              <NameZh>云南省</NameZh>
              <NameEn>yunnan</NameEn>
        </Region>
        <Region>
              <NameZh>西藏自治区</NameZh>
              <NameEn>xizang</NameEn>
        </Region>
        <Region>
              <NameZh>辽宁省</NameZh>
              <NameEn>liaoning</NameEn>
        </Region>
        <Region>
              <NameZh>湖南省</NameZh>
              <NameEn>hunan</NameEn>
        </Region>
        <Region>
              <NameZh>中国香港特别行政区</NameZh>
              <NameEn>xianggang</NameEn>
        </Region>
        <Region>
              <NameZh>陕西省</NameZh>
              <NameEn>shaanxi</NameEn>
        </Region>
        <Region>
              <NameZh>中国澳门特别行政区</NameZh>
              <NameEn>aomen</NameEn>
        </Region>
        <Region>
              <NameZh>安徽省</NameZh>
              <NameEn>anhui</NameEn>
        </Region>
        <Region>
              <NameZh>天津市</NameZh>
              <NameEn>tianjin</NameEn>
        </Region>
        <Region>
              <NameZh>江西省</NameZh>
              <NameEn>jiangxi</NameEn>
        </Region>
        <Region>
              <NameZh>湖北省</NameZh>
              <NameEn>hubei</NameEn>
        </Region>
        <Region>
              <NameZh>重庆市</NameZh>
              <NameEn>chongqing</NameEn>
        </Region>
        <Region>
              <NameZh>甘肃省</NameZh>
              <NameEn>gansu</NameEn>
        </Region>
        <Region>
              <NameZh>中国台湾省</NameZh>
              <NameEn>taiwan</NameEn>
        </Region>
        <Region>
              <NameZh>山东省</NameZh>
              <NameEn>shandong</NameEn>
        </Region>
        <Region>
              <NameZh>吉林省</NameZh>
              <NameEn>jilin</NameEn>
        </Region>
        <Region>
              <NameZh>上海市</NameZh>
              <NameEn>shanghai</NameEn>
        </Region>
        <Region>
              <NameZh>四川省</NameZh>
              <NameEn>sichuan</NameEn>
        </Region>
        <Region>
              <NameZh>内蒙古自治区</NameZh>
              <NameEn>neimenggu</NameEn>
        </Region>
  </Regions>
</DescribeCdnRegionAndIspResponse>
```

`JSON` format

```
{
        "Isps": {
            "Isp": [
                {
                    "NameZh": "电信",
                    "NameEn": "telecom"
                },
                {
                    "NameZh": "移动",
                    "NameEn": "mobile"
                },
                {
                    "NameZh": "教育网",
                    "NameEn": "cernet"
                },
                {
                    "NameZh": "铁通",
                    "NameEn": "tietong"
                },
                {
                    "NameZh": "其他",
                    "NameEn": "other"
                },
                {
                    "NameZh": "鹏博士",
                    "NameEn": "drpeng"
                },
                {
                    "NameZh": "联通",
                    "NameEn": "unicom"
                },
                {
                    "NameZh": "阿里巴巴",
                    "NameEn": "alibaba"
                },
                {
                    "NameZh": "中信网络",
                    "NameEn": "citic"
                },
                {
                    "NameZh": "方正宽带",
                    "NameEn": "dounder"
                },
                {
                    "NameZh": "海外ISP",
                    "NameEn": "overseas"
                },
                {
                    "NameZh": "有线通",
                    "NameEn": "ocn"
                },
                {
                    "NameZh": "华数",
                    "NameEn": "wasu"
                },
                {
                    "NameZh": "湖北广电",
                    "NameEn": "hrtn"
                },
                {
                    "NameZh": "重庆有线",
                    "NameEn": "cqccn"
                },
                {
                    "NameZh": "歌华有线",
                    "NameEn": "bjctv"
                },
                {
                    "NameZh": "天威视讯",
                    "NameEn": "topway"
                },
                {
                    "NameZh": "中国香港宽频",
                    "NameEn": "hkbn"
                },
                {
                    "NameZh": "澳大利亚电信",
                    "NameEn": "telstra"
                },
                {
                    "NameZh": "江西广电",
                    "NameEn": "jxsarft"
                },
                {
                    "NameZh": "湖南广电",
                    "NameEn": "gbs"
                },
                {
                    "NameZh": "中国澳门电讯",
                    "NameEn": "ctm"
                },
                {
                    "NameZh": "黑龙江广电",
                    "NameEn": "ljwl"
                },
                {
                    "NameZh": "中华电信",
                    "NameEn": "cht"
                },
                {
                    "NameZh": "陕西广电",
                    "NameEn": "sxbctv"
                },
                {
                    "NameZh": "广电",
                    "NameEn": "ccn"
                },
                {
                    "NameZh": "长城宽带",
                    "NameEn": "gwbn"
                },
                {
                    "NameZh": "华数传媒",
                    "NameEn": "wasumedia"
                },
                {
                    "NameZh": "广东广电",
                    "NameEn": "gcable"
                },
                {
                    "NameZh": "辽宁广电",
                    "NameEn": "lnsarft"
                },
                {
                    "NameZh": "河南广电",
                    "NameEn": "hensarft"
                },
                {
                    "NameZh": "山东广电",
                    "NameEn": "sdsarft"
                },
                {
                    "NameZh": "江苏广电",
                    "NameEn": "jssarft"
                },
                {
                    "NameZh": "四川艾普",
                    "NameEn": "aipu"
                },
                {
                    "NameZh": "吉视传媒",
                    "NameEn": "jilincatv"
                },
                {
                    "NameZh": "四川广电",
                    "NameEn": "sicsarft"
                },
                {
                    "NameZh": "安徽广电",
                    "NameEn": "anhuicatv"
                },
                {
                    "NameZh": "福建广电",
                    "NameEn": "fujiancatv"
                },
                {
                    "NameZh": "新疆广电",
                    "NameEn": "xjsarft"
                },
                {
                    "NameZh": "贵州广电",
                    "NameEn": "guizhoucatv"
                },
                {
                    "NameZh": "局域网",
                    "NameEn": "local area network"
                },
                {
                    "NameZh": "湖南巨亚",
                    "NameEn": "hunanjy"
                },
                {
                    "NameZh": "珠江数码",
                    "NameEn": "zhujiangsm"
                },
                {
                    "NameZh": "北京宝联之星",
                    "NameEn": "baolian"
                },
                {
                    "NameZh": "印尼Telin",
                    "NameEn": "telin"
                },
                {
                    "NameZh": "印尼Indosat",
                    "NameEn": "indosat"
                },
                {
                    "NameZh": "上海驰联",
                    "NameEn": "shchilian"
                },
                {
                    "NameZh": "上海企舜",
                    "NameEn": "shqishun"
                },
                {
                    "NameZh": "皓宽网络",
                    "NameEn": "cnix"
                },
                {
                    "NameZh": "印度Sify",
                    "NameEn": "sify"
                },
                {
                    "NameZh": "印尼Zenlayer",
                    "NameEn": "zenlayer"
                },
                {
                    "NameZh": "印度TATA",
                    "NameEn": "tata"
                },
                {
                    "NameZh": "印度AirTel",
                    "NameEn": "airtel"
                },
                {
                    "NameZh": "Telstra Global",
                    "NameEn": "telstraglobal"
                },
                {
                    "NameZh": "Maxis",
                    "NameEn": "maxis"
                },
                {
                    "NameZh": "内蒙古广电",
                    "NameEn": "nmgcatv"
                },
                {
                    "NameZh": "JasTel",
                    "NameEn": "jastel"
                },
                {
                    "NameZh": "Taiwan Fixed Network",
                    "NameEn": "taiwanfixednetwork"
                },
                {
                    "NameZh": "Digital United",
                    "NameEn": "digitalunited"
                },
                {
                    "NameZh": "NTT",
                    "NameEn": "ntt"
                },
                {
                    "NameZh": "KDDI",
                    "NameEn": "kddi"
                },
                {
                    "NameZh": "Korea Telecom",
                    "NameEn": "koreatelecom"
                },
                {
                    "NameZh": "TM Net",
                    "NameEn": "tmnet"
                },
                {
                    "NameZh": "True Internet",
                    "NameEn": "trueinternet"
                },
                {
                    "NameZh": "PT Aplikanusa Lintasarta",
                    "NameEn": "ptaplikanusalintasarta"
                },
                {
                    "NameZh": "VNPT",
                    "NameEn": "vnpt"
                },
                {
                    "NameZh": "EITC-DU",
                    "NameEn": "eitcdu"
                },
                {
                    "NameZh": "Rostelecom",
                    "NameEn": "rostelecom"
                },
                {
                    "NameZh": "GLOBALNET",
                    "NameEn": "globalnet"
                },
                {
                    "NameZh": "ER-Telecom Holding",
                    "NameEn": "ertelecomholding"
                },
                {
                    "NameZh": "Business Network Ltd",
                    "NameEn": "businessnetworkltd"
                },
                {
                    "NameZh": "Vodafone",
                    "NameEn": "vodafone"
                },
                {
                    "NameZh": "Level",
                    "NameEn": "level"
                },
                {
                    "NameZh": "TATA Communications(America)",
                    "NameEn": "tatacommunications"
                },
                {
                    "NameZh": "ENTER S.r.l.",
                    "NameEn": "entersrl"
                },
                {
                    "NameZh": "Vodacom ENS",
                    "NameEn": "vodacomens"
                },
                {
                    "NameZh": "Hurricane Electric",
                    "NameEn": "hurricaneelectric"
                },
                {
                    "NameZh": "CTA",
                    "NameEn": "cta"
                },
                {
                    "NameZh": "Telefonica USA",
                    "NameEn": "telefonicausa"
                },
                {
                    "NameZh": "Verizon Business",
                    "NameEn": "verizonbusiness"
                },
                {
                    "NameZh": "Telefonica Data S.A.",
                    "NameEn": "telefonicadatasa"
                },
                {
                    "NameZh": "PLDT",
                    "NameEn": "pldt"
                },
                {
                    "NameZh": "Viettel",
                    "NameEn": "viettel"
                },
                {
                    "NameZh": "RETN",
                    "NameEn": "retn"
                },
                {
                    "NameZh": "AIMS",
                    "NameEn": "aims"
                },
                {
                    "NameZh": "广西广电",
                    "NameEn": "guangxsarft"
                },
                {
                    "NameZh": "河北广电",
                    "NameEn": "hebsarft"
                },
                {
                    "NameZh": "湖南有线",
                    "NameEn": "hunsarft"
                },
                {
                    "NameZh": "山东青岛广电",
                    "NameEn": "sdqdsarft"
                },
                {
                    "NameZh": "Level3",
                    "NameEn": "level3"
                },
                {
                    "NameZh": "宁夏广电",
                    "NameEn": "nxsarft"
                },
                {
                    "NameZh": "Zain",
                    "NameEn": "zain"
                },
                {
                    "NameZh": "Singtel",
                    "NameEn": "singtel"
                },
                {
                    "NameZh": "BBIX",
                    "NameEn": "bbix"
                },
                {
                    "NameZh": "MSK-IX",
                    "NameEn": "mskix"
                },
                {
                    "NameZh": "TPIX",
                    "NameEn": "tpix"
                },
                {
                    "NameZh": "Equinix",
                    "NameEn": "equinix"
                },
                {
                    "NameZh": "中国台湾之星",
                    "NameEn": "taiwanstar"
                },
                {
                    "NameZh": "阿里云",
                    "NameEn": "aliyun"
                },
                {
                    "NameZh": "TelekomMalaysia",
                    "NameEn": "telekommalaysia"
                },
                {
                    "NameZh": "KINX",
                    "NameEn": "kinx"
                },
                {
                    "NameZh": "SKBB",
                    "NameEn": "skbb"
                },
                {
                    "NameZh": "CAT",
                    "NameEn": "cat"
                },
                {
                    "NameZh": "Ooredoo",
                    "NameEn": "ooredoo"
                },
                {
                    "NameZh": "Fareastone",
                    "NameEn": "fareastone telecom"
                },
                {
                    "NameZh": "全部",
                    "NameEn": "all"
                },
                {
                    "NameZh": "JIO",
                    "NameEn": "jio"
                },
                {
                    "NameZh": "甘肃广电",
                    "NameEn": "gssarft"
                },
                {
                    "NameZh": "天津广电",
                    "NameEn": "tjsarft"
                },
                {
                    "NameZh": "大连理工大学",
                    "NameEn": "dlut"
                }
            ]
        },
        "RequestId": "9CEF1678-CAE9-4173-88C9-31DA0931BBAF",
        "Regions": {
            "Region": [
                {
                    "NameZh": "河北省",
                    "NameEn": "hebei"
                },
                {
                    "NameZh": "宁夏回族自治区",
                    "NameEn": "ningxia"
                },
                {
                    "NameZh": "贵州省",
                    "NameEn": "guizhou"
                },
                {
                    "NameZh": "新疆维吾尔自治区",
                    "NameEn": "xinjiang"
                },
                {
                    "NameZh": "北京市",
                    "NameEn": "beijing"
                },
                {
                    "NameZh": "福建省",
                    "NameEn": "fujian"
                },
                {
                    "NameZh": "海南省",
                    "NameEn": "hainan"
                },
                {
                    "NameZh": "黑龙江省",
                    "NameEn": "heilongjiang"
                },
                {
                    "NameZh": "广东省",
                    "NameEn": "guangdong"
                },
                {
                    "NameZh": "广西壮族自治区",
                    "NameEn": "guangxi"
                },
                {
                    "NameZh": "浙江省",
                    "NameEn": "zhejiang"
                },
                {
                    "NameZh": "青海省",
                    "NameEn": "qinghai"
                },
                {
                    "NameZh": "江苏省",
                    "NameEn": "jiangsu"
                },
                {
                    "NameZh": "山西省",
                    "NameEn": "shanxi"
                },
                {
                    "NameZh": "河南省",
                    "NameEn": "henan"
                },
                {
                    "NameZh": "云南省",
                    "NameEn": "yunnan"
                },
                {
                    "NameZh": "西藏自治区",
                    "NameEn": "xizang"
                },
                {
                    "NameZh": "辽宁省",
                    "NameEn": "liaoning"
                },
                {
                    "NameZh": "湖南省",
                    "NameEn": "hunan"
                },
                {
                    "NameZh": "中国香港特别行政区",
                    "NameEn": "xianggang"
                },
                {
                    "NameZh": "陕西省",
                    "NameEn": "shaanxi"
                },
                {
                    "NameZh": "中国澳门特别行政区",
                    "NameEn": "aomen"
                },
                {
                    "NameZh": "安徽省",
                    "NameEn": "anhui"
                },
                {
                    "NameZh": "天津市",
                    "NameEn": "tianjin"
                },
                {
                    "NameZh": "江西省",
                    "NameEn": "jiangxi"
                },
                {
                    "NameZh": "湖北省",
                    "NameEn": "hubei"
                },
                {
                    "NameZh": "重庆市",
                    "NameEn": "chongqing"
                },
                {
                    "NameZh": "甘肃省",
                    "NameEn": "gansu"
                },
                {
                    "NameZh": "中国台湾省",
                    "NameEn": "taiwan"
                },
                {
                    "NameZh": "山东省",
                    "NameEn": "shandong"
                },
                {
                    "NameZh": "吉林省",
                    "NameEn": "jilin"
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
                    "NameZh": "内蒙古自治区",
                    "NameEn": "neimenggu"
                }
            ]
        }
    }
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

