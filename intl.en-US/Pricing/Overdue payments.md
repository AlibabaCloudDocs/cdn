---
keyword: [service suspension, overdue payments, low balance alerts, CDN service]
---

# Overdue payments

This topic explains the causes of low balance alerts and the suspension of Alibaba Cloud Content Delivery Network \(CDN\).

## Service suspension

**Note:** Alibaba Cloud CDN sends you a notification when you have an overdue payment. You must complete overdue payments at the earliest opportunity to ensure service continuity.

When an overdue payment occurs, the system sends notifications to you through SMS messages or emails.

-   If you complete the payment within 24 hours after it becomes overdue, your CDN service will not be suspended.
-   If an overdue payment is not completed within 24 hours, your CDN service will be suspended. The status of domain names accelerated by Alibaba Cloud CDN will change to offline. In this case, Alibaba Cloud CDN directly resolves the accelerated domain names to the origin servers. The resources cached on CDN nodes will be released. The configuration information about the accelerated domain names will be retained for one month.

## Low balance alerts

Low balance alerts are sent to you in the following scenarios:

-   Pay-by-data-transfer: The system determines whether you have a sufficient balance in your account to pay for the next three billing cycles based on the average payable amount during the last seven hours. If you do not have a sufficient balance in your account, the system sends a notification to you through an SMS message or an email.
-   Pay-by-bandwidth: The system determines whether you have a sufficient balance in your account to pay for the next billing cycle \(day\) based on the payable amount during the most recent billing cycle \(day\). If you do not have a sufficient balance in your account, the system sends a notification to you through an SMS message or an email.

