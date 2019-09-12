# Monitor data {#task_261642 .task}

The Data Monitoring module includes resource monitoring and real-time monitoring. You can use the data monitoring function to learn about the running status of CDN.

1.  Log on to the [Alibaba Cloud CDN console](https://partners-intl.aliyun.com/login-required#cdn).
2.  In the left-side navigation pane, choose **Monitoring** \> **Resource Monitoring** or **Real-time Monitoring**.
3.  On the Resource Monitoring or Real-time Monitoring page, select monitoring items and metrics as needed and click **Search**. 
    -   Resource monitoring

        You can view and download the details about the following metrics by domain name, region, provider, time granularity \(1 minute, 5 minutes, or 1 hour\), and time range \(today, yesterday, last seven days, last 30 days, or a custom period\).

        |Item|Metric|
        |:---|:-----|
        |Traffic/Bandwidth|Bandwidth and traffic|
        |Back-to-origin Statistics|Back-to-origin bandwidth and back-to-origin traffic|
        |Visits|Requests and QPS|
        |Hit Rate|None|
        |HTTPCODE|5xx, 4xx, 3xx, and 2xx status codes|

        ![Resource monitoring](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15915/156826969952270_en-US.png)

        The data shown in the resource monitoring line chart differs slightly from the billing data. For example, a 30-day resource statistics line chart is plotted at 14,400s intervals, while the billing data is plotted at 300s intervals. The line chart does not take into account certain points and is mainly used to show the bandwidth trend. The billing data has finer granularity to help you calculate the actual bandwidth usage.

    -   Real-time monitoring

        You can view the details about the following metrics by domain name, region, provider, and time range \(last hour, last 6 hours, last 12 hours, or a custom period\).

        |Item|Metric|
        |:---|:-----|
        |Basic Data|Bandwidth, traffic, requests, and QPS|
        |Back-to-origin Statistics|Back-to-origin bandwidth and back-to-origin traffic|
        |Quality Monitoring|Request hit rate, byte hit rate, 5xx, 4xx, 3xx, and 2xx status codes|

        ![User interface](images/8909_en-US_source.png)


