---
keyword: [Alibaba Cloud CDN bandwidth, bandwidth cap]
---

# Set a bandwidth cap

A bandwidth cap specifies the maximum bandwidth value of a domain name. Alibaba Cloud Content Delivery Network \(CDN\) issues a bill only after a billing cycle ends. The fee is calculated on a pay-as-you-go basis. Alibaba Cloud CDN does not limit the amount of resources that can be consumed within a billing cycle. Therefore, you can set a bandwidth cap to prevent unexpected high bills caused by traffic spikes.

After you set a bandwidth cap for a domain name, the domain name is automatically disabled if the average bandwidth value measured during a statistical cycle \(one minute\) exceeds the specified bandwidth cap. In this case, CDN services are suspended for the domain name and all requests that are destined for the domain name are directly sent to the origin server.

-   If the average bandwidth value measured during a statistical cycle is lower than the specified bandwidth cap, the domain name can use CDN services as expected.
-   If the average bandwidth value measured during a statistical cycle reaches the specified bandwidth cap, the domain name is automatically disabled. All requests that are destined for the domain name are directly sent to the origin server.
-   Alibaba Cloud CDN does not automatically restore the suspended services even if the average bandwidth value drops below the specified bandwidth cap and no traffic spikes are detected. To restore the suspended services, you must log on to the Alibaba Cloud CDN console and enable the domain name.

## Usage notes

-   After you set a bandwidth cap for a domain name, the domain name is disabled if the average bandwidth value measured during a statistical cycle exceeds the specified bandwidth cap. We recommend that you estimate the maximum bandwidth value required by your workloads before you set a bandwidth cap for your domain name. This ensures service availability. Proceed with caution.

    **Note:** If a domain name is disabled because the specified bandwidth cap is reached, you can log on to the[Alibaba Cloud CDN console](https://cdn.console.aliyun.com) and navigate to the **Domain Names** page. Then, select the domain name that you want to manage, and click **Enable** in the Actions column to enable the domain name.

-   The monitoring data of bandwidth values may be delayed for a short period of time. A domain name is disabled about 10 minutes after the bandwidth cap set for the domain name is reached. A domain name cannot be disabled more than once within an hour.
-   To allow a Resource Access Management \(RAM\) user to set bandwidth caps, you must grant the RAM user the required permissions.

    To grant permissions to a RAM user, you can log on to the [RAM console](https://ram.console.aliyun.com/permissions), create the **AliyunCDNFullAccess** permission policy, and then attach this policy to the RAM user.

-   You cannot set a bandwidth cap for a wildcard domain name. If you set a bandwidth cap for a wildcard domain name, the bandwidth cap does not take effect.
-   A bandwidth cap does not throttle bandwidth. If the average bandwidth value measured during a statistical cycle reaches the specified bandwidth cap, the domain name is automatically disabled. However, the bandwidth throttling feature throttles bandwidth for a domain name if its bandwidth value reaches the specified upper limit.

## Caution

The monitoring data of bandwidth values may be delayed for a short period of time. A domain name is disabled about 10 minutes after the bandwidth cap set for the domain name is reached. During this period of time, the actual bandwidth value is higher than the specified cap. CDN services remain available for the domain name. You are charged for the bandwidth resources that are consumed by your CDN service before the domain name is disabled. The following examples show how bandwidth resource are billed during this period of time:

**Example 1**:

Customer A chooses the pay-by-peak-bandwidth metering method for Alibaba Cloud CDN and adds only the domain name example.com to Alibaba Cloud CDN. The bandwidth cap of the domain name is set to 10 Gbit/s. From 21:00:00 \(UTC+8\) on February 1, 2021 to 21:01:00 \(UTC+8\) on February 1, 2021, the traffic spikes and the actual bandwidth value reaches 10 Gbit/s. The domain name is disabled at 21:11:00 \(UTC+8\) on February 1, 2021 because the monitoring data of bandwidth values is delayed for a short period of time. Before the domain name is disabled, the actual bandwidth value reaches 25 Gbit/s. In this case, the bandwidth fees that are included in the bill generated on February 1, 2021 are calculated based on the actual bandwidth value, which is 25 Gbit/s.

**Example 2**:

Customer B chooses the pay-by-data-transfer metering method for Alibaba Cloud CDN and adds only the domain name example.com to Alibaba Cloud CDN. The bandwidth cap of the domain name is set to 10 Gbit/s. From 21:00:00 \(UTC+8\) on February 1, 2021 to 21:01:00 \(UTC+8\) on February 1, 2021, the traffic spikes and the actual bandwidth value reaches 10 Gbit/s. During this period of time, 30 GB of data transfer is generated. The domain name is disabled at 21:11:00 \(UTC+8\) on February 1, 2021 because the monitoring data of bandwidth values is delayed for a short period of time. Before the domain name is disabled, 400 GB of data transfer is generated. In this case, the data transfer fees are included in the bill of the billing cycle, which is from 21:00:00 \(UTC+8\) on February 1, 2021 to 22:00:00 \(UTC+8\) on February 1, 2021.

## Procedure

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Advanced**.

5.  Authorize CloudMonitor to manage your CDN resources.

    1.  Click **Authorize** next to **Role Authorization**.

    2.  On the **Cloud Resource Access Authorization** page, click **Confirm Authorization Policy**.

6.  In the **Bandwidth Cap** section, click **Modify**.

7.  In the **Bandwidth Cap** dialog box, turn on **Bandwidth Cap** and set a bandwidth cap.

    **Note:**

    -   The conversion between each two neighboring data units is 1,000. For example, 1 Tbit/s is equal to 1,000 Gbit/s, and 1 Gbit/s is equal to 1,000 Mbit/s.
    -   You can choose to enable or disable this feature based on your business requirements.
8.  Click **OK**.


