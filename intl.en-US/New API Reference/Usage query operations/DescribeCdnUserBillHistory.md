# DescribeCdnUserBillHistory

Queries the billing history under your Alibaba Cloud account.

The maximum number of times that each user can call this operation per second is 100.

You can query billing history up to the last one month.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeCdnUserBillHistory&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeCdnUserBillHistory|The operation that you want to perform. Set the value to **DescribeCdnUserBillHistory**. |
|StartTime|String|Yes|2018-09-30T16:00:00Z|The beginning of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 The minimum data collection interval is 5 minutes. |
|EndTime|String|Yes|2018-10-31T16:00:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

 The end of the time range to query. The end time must be later than the start time. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|BillHistoryData|Array of BillHistoryDataItem| |The billing history returned. |
|BillHistoryDataItem| | | |
|BillTime|String|2018-09-30T16:00:00Z|The beginning of the time range that was queried. |
|BillType|String|month\_4th\_day\_bandwidth|The billing method. |
|BillingData|Array of BillingDataItem| |The billable items. |
|BillingDataItem| | | |
|Bandwidth|Float|4041|The bandwidth. Unit: bit/s. |
|CdnRegion|String|AP1|The billable region. Valid values:

 -   **CN**: mainland China
-   **OverSeas**: regions outside mainland China
-   **AP1**: Asia Pacific 1
-   **AP2**: Asia Pacific 2
-   **AP3**: Asia Pacific 3
-   **NA**: North America
-   **SA**: South America
-   **EU**: Europe
-   **MEAA**: Middle East and Africa |
|ChargeType|String|DynamicHttp|The billable item. Valid values:

 -   **StaticHttp**: static HTTP requests
-   **DynamicHttp**: dynamic HTTP requests
-   **DynamicHttps**: dynamic HTTPS requests |
|Count|Float|203601|The number of requests. |
|Flow|Float|24567|The amount of network traffic. Unit: bytes. |
|Dimension|String|flow|The dimension. |
|RequestId|String|ED61C6C3-8241-4187-AAA7-5157AE175CEC|The ID of the request. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com?Action=DescribeCdnUserBillHistory
&StartTime=2018-09-30T16:00:00Z
&EndTime=2018-10-31T16:00:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeCdnUserBillHistoryResponse>
  <BillHistoryData>
        <BillHistoryDataItem>
              <BillType>month_4th_day_bandwidth</BillType>
              <BillingData>
                    <BillingDataItem>
                          <Bandwidth>4041</Bandwidth>
                          <CdnRegion>AP1</CdnRegion>
                          <FLOW>24567</FLOW>
                    </BillingDataItem>
                    <BillingDataItem>
                          <Bandwidth>3819</Bandwidth>
                          <CdnRegion>NA</CdnRegion>
                    </BillingDataItem>
                    <BillingDataItem>
                          <Bandwidth>272113</Bandwidth>
                          <CdnRegion>CN</CdnRegion>
                    </BillingDataItem>
              </BillingData>
              <Dimension>flow</Dimension>
              <BillTime>2018-09-30T16:00:00Z</BillTime>
        </BillHistoryDataItem>
        <BillHistoryDataItem>
              <BillType>month_avg_day_bandwidth</BillType>
              <BillingData>
                    <BillingDataItem>
                          <Bandwidth>4389</Bandwidth>
                          <CdnRegion>AP1</CdnRegion>
                    </BillingDataItem>
                    <BillingDataItem>
                          <Bandwidth>4302</Bandwidth>
                          <CdnRegion>NA</CdnRegion>
                    </BillingDataItem>
                    <BillingDataItem>
                          <Bandwidth>291641</Bandwidth>
                          <CdnRegion>CN</CdnRegion>
                    </BillingDataItem>
              </BillingData>
              <Dimension>flow</Dimension>
              <BillTime>2018-09-30T16:00:00Z</BillTime>
        </BillHistoryDataItem>
        <BillHistoryDataItem>
              <BillType>hour_vas</BillType>
              <BillingData>
                    <BillingDataItem>
                          <Count>205624</Count>
                          <ChargeType>DynamicHttp</ChargeType>
                    </BillingDataItem>
              </BillingData>
              <Dimension>vas</Dimension>
              <BillTime>2018-09-30T16:00:00Z</BillTime>
        </BillHistoryDataItem>
        <BillHistoryDataItem>
              <BillType>hour_vas</BillType>
              <BillingData>
                    <BillingDataItem>
                          <Count>203601</Count>
                          <ChargeType>DynamicHttp</ChargeType>
                    </BillingDataItem>
              </BillingData>
              <Dimension>vas</Dimension>
              <BillTime>2018-09-30T17:00:00Z</BillTime>
        </BillHistoryDataItem>
  </BillHistoryData>
  <RequestId>ED61C6C3-8241-4187-AAA7-5157AE175CEC</RequestId>
</DescribeCdnUserBillHistoryResponse>
```

`JSON` format

```
{
  "BillHistoryData": {
    "BillHistoryDataItem": [
      {
        "BillType": "month_4th_day_bandwidth",
        "BillingData": {
          "BillingDataItem": [
            {
              "Bandwidth": 4041,
              "CdnRegion": "AP1",
              "FLOW": "24567"
            },
            {
              "Bandwidth": 3819,
              "CdnRegion": "NA"
            },
            {
              "Bandwidth": 272113,
              "CdnRegion": "CN"
            }
          ]
        },
        "Dimension": "flow",
        "BillTime": "2018-09-30T16:00:00Z"
      },
      {
        "BillType": "month_avg_day_bandwidth",
        "BillingData": {
          "BillingDataItem": [
            {
              "Bandwidth": 4389,
              "CdnRegion": "AP1"
            },
            {
              "Bandwidth": 4302,
              "CdnRegion": "NA"
            },
            {
              "Bandwidth": 291641,
              "CdnRegion": "CN"
            }
          ]
        },
        "Dimension": "flow",
        "BillTime": "2018-09-30T16:00:00Z"
      },
      {
        "BillType": "hour_vas",
        "BillingData": {
          "BillingDataItem": [
            {
              "Count": 205624,
              "ChargeType": "DynamicHttp"
            }
          ]
        },
        "Dimension": "vas",
        "BillTime": "2018-09-30T16:00:00Z"
      },
      {
        "BillType": "hour_vas",
        "BillingData": {
          "BillingDataItem": [
            {
              "Count": 203601,
              "ChargeType": "DynamicHttp"
            }
          ]
        },
        "Dimension": "vas",
        "BillTime": "2018-09-30T17:00:00Z"
      }
    ]
  },
  "RequestId": "ED61C6C3-8241-4187-AAA7-5157AE175CEC"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

