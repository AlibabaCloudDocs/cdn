# Introduction to sandboxes

This topic introduces sandboxes and their features and describes impacts on domain names that are in a sandbox.

## What is a sandbox?

Alibaba Cloud Content Delivery Network \(CDN\) provides content acceleration service to thousands of accelerated domain names. If an accelerated domain name is under attack, Alibaba Cloud CDN automatically adds the attacked domain name to a sandbox. This ensures that the CDN service of other users can work as expected. If the accelerated domain name is under severe attack, other accelerated domain names under the same account are also added to the sandbox. After an accelerated domain name is added to a sandbox, the domain name may be unavailable for a period of time.

## How do I check whether a domain name is added to a sandbox?

After an accelerated domain name is added to a sandbox, notifications will be sent to you through SMS. You can also log on to the Alibaba Cloud CDN console and check the status of the domain names.

## Can I remove domain names from sandboxes?

To ensure that other users can use their CDN service as expected, you are not allowed to remove domain names from sandboxes.

## What can I do if my accelerated domain name is added to a sandbox?

By default, Alibaba Cloud CDN does not provide protection against attacks. After an accelerated domain is added to a sandbox, the CDN service is not guaranteed and the domain name cannot be removed from the sandbox.

**Note:**

-   Alibaba Cloud CDN reserves the right to disable the acceleration service for domain names that are frequently attacked and for domain names that are attacked due to violations of the Alibaba Cloud CDN limits. If your domain name is under attack due to violations of the Alibaba Cloud CDN limits, Alibaba Cloud CDN does not bear any responsibility and all fees incurred are borne by you.
-   After an accelerated domain name is added to a sandbox, visits to the accelerated domain name continue to incur data transfer fees.
-   If the accelerated region of a domain name is outside mainland China and the domain name does not have an Internet Content Provider \(ICP\) number, the domain name becomes unavailable after it is added to a sandbox.

