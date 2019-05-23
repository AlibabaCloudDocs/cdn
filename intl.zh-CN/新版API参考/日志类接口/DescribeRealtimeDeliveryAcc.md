# DescribeRealtimeDeliveryAcc {#reference_qn5_qly_dgb .reference}

实时日志投递次数查询。

## 请求参数 {#section_obx_rly_dgb .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeRealtimeDeliveryAcc。|
|StartTime|String|否|获取日志起始时间点。-   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。

|
|EndTime|String|否| -   结束时间需大于起始时间。
-   起止时间和结束时间，间隔不超过一年。
-   获取日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。

 |
|Interval|String|否| -   查询数据的时间粒度，支持300，3600，86400秒。
-   不传和传的值不支持时，时间跨度不超过3天，默认值300秒。
-   超过3天默认值3600秒。
-   超过30天默认值86400秒。

 |
|Project|String|否|实时日志投递的Project|
|Logstore|String|否|实时日志投递的Logstore|

## AccData {#section_ugs_cny_dgb .section}

|名称|类型|描述|
|:-|:-|:-|
|TimeStamp|String|时间片起始时刻|
|FailedNum|Integer|实时日志投递失败次数|
|SuccessNum|Integer|实时日志投递成功次数|

## 返回参数 {#section_vbx_rly_dgb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|RequestId|

## 示例 {#section_ybx_rly_dgb .section}

请求示例

```
http://cdn.aliyuncs.com?Action=DescribeRealtimeDeliveryAcc&StartTime=2015-12-10T20:00:00Z&EndTime=2015-12-10T21:05:00Z
&<公共请求参数>
```

返回示例

```
{
    "RequestId": "684306D2-2511-4977-991D-CE97E91FD7C0",
    "ReatTimeDeliveryAccData": {
        "AccData": [
            {
                "TimeStamp": "2018-09-03T06:00:00Z",
                "FailedNum": 0,
                "SuccessNum": 321321
            },
            {
                "TimeStamp": "2018-09-03T07:00:00Z",
                "FailedNum": 0,
                "SuccessNum": 32943
            }
            ...
        ]
    }
}
```

## 错误码 {#section_zbx_rly_dgb .section}

|错误码|错误信息|HTTP 状态码|描述|
|:--|:---|:-------|:-|
|InvalidStartTime.Malformed|Specified StartTime is malformed.|400|StartTime格式错误|
|InvalidEndTime.Malformed|Specified EndTime is malformed.|400|StartTime格式错误|
|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|400|EndTime和StartTime差值超过90天|
|InvalidEndTime.Mismatch|Specified EndTime does not math the specified StartTime.|400|EndTime小于StartTime|

