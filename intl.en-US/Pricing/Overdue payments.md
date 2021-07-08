---
keyword: [service suspension, overdue payments, low balance alerts, CDN service]
---

# Overdue payments

This topic explains the causes of low balance alerts and the suspension of Alibaba Cloud Content Delivery Network \(CDN\).

## Service suspension

**Note:** Alibaba Cloud CDN sends you a notification if you have an overdue payment. You must complete overdue payments at the earliest opportunity to ensure service continuity.

When an overdue payment occurs, the system notifies you by text messages or emails.

-   If you complete the payment within 24 hours after it becomes overdue, Alibaba Cloud CDN will not be suspended.
-   If the overdue payment is not completed within 24 hours, Alibaba Cloud CDN will be suspended. The status of domain names accelerated by Alibaba Cloud CDN will change to offline. In this case, Alibaba Cloud CDN directly redirects requests that are destined for the accelerated domain names to the origin servers. The resources cached on CDN nodes will be released. The configuration information about the accelerated domain names will be retained for one month.

## Low balance alerts

Low balance alerts are sent to you in the following scenarios:

-   Pay-by-data-transfer: The system determines whether you have a sufficient balance in your Alibaba Cloud account to pay for the next three billing cycles based on the average payable amount during the last 7 hours. If you do not have a sufficient balance in your Alibaba Cloud account, the system notifies you by text messages or emails.
-   Pay-by-bandwidth: The system determines whether you have a sufficient balance in your Alibaba Cloud account to pay for the next billing cycle \(day\) based on the payable amount during the most recent billing cycle \(day\). If you do not have a sufficient balance in your Alibaba Cloud account, the system notifies you by text messages or emails.

