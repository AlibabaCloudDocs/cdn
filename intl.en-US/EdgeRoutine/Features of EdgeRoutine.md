# Features of EdgeRoutine

EdgeRoutine \(ER\) is a lightweight and serverless computing environment. It can run custom JavaScript code on CDN nodes. You do not need to manage the underlying infrastructure, such as hardware configurations, region settings, scheduling, and elastic scaling. After you use the EdgeRoutine CLI to deploy code to the production environment, the system automatically runs the code on all CDN nodes. The CDN nodes process requests in different regions worldwide by following the logical rules of the code.

## Benefits

Traditional CDN services are used to only cache and distribute content, but cannot provide the computing feature for workloads. To process a large number of requests sent to CDN nodes, Alibaba Cloud CDN must redirect the requests to origin servers that support complex computing. This back-to-origin process consumes resources on origin servers and requires a complex origin architecture. ER enables CDN nodes to provide the computing feature. You can use ER to customize your CDN service and process complex requests. This feature reduces the number of back-to-origin requests and accelerates content delivery. CDN nodes support high availability, high scalability, and global load balancing. These features allow CDN nodes to support computing in more scenarios. ER provides a computing environment on each CDN node and allows you to run custom JavaScript code on CDN nodes.

## How ER works

ER runs on CDN nodes and provides a serverless JavaScript runtime environment for you to deploy JavaScript code.

![How ER works](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2337372061/p86758.png)

## Scenarios

ER provides a fully integrated JavaScript runtime environment that allows you to manage comprehensive logic of request processing. You can also use ER to enable CDN nodes to asynchronously retrieve content from origin servers over HTTP or HTTPS. ER can be used in a wide array of scenarios. The following table lists the scenarios supported by ER.

|Scenario|Feature|
|--------|-------|
|Authentication|Custom CDN authentication and asynchronous authentication|
|Originless responses|Static content delivery|
|Network security|-   Anti-bot protection
-   Web Application Firewall \(WAF\) deployed on CDN nodes |
|Logs|-   Automatic logging on CDN nodes
-   Records of back-to-origin time |
|DevOps|-   A/B testing
-   Webhooks for GitLab, GitHub, and Jenkins
-   Programming of instant messaging robots, such as Slack robots |
|API Gateway|-   Edge GraphQL
-   Edge gateway:
    -   Network traffic throttling
    -   API parameter validation |
|CDN|-   Prefetching content to CDN nodes
-   Caching content on CDN nodes
-   Redirecting requests from CDN nodes to multiple origin servers
    -   Merging content from multiple origin servers
    -   Optimized redirection with the lowest latency
-   Retrieval of content from different origin servers based on custom back-to-origin algorithms |
|Web applications and applets|-   Edge rendering
    -   Markdown rendering
    -   Edge Side Includes \(ESI\) rendering
    -   Nunjucks rendering
-   Edge server-side rendering \(SSR\)
    -   Vue.js
    -   React.js
-   Content prefetching and reduction of web page loading time
-   Diverse services on CDN nodes, such as QR code generation |
|Beacon|Capturing and analytics of edge tracking data|

## Use ER

The first private preview of ER was completed in September 2020. You cannot activate ER after the private preview is completed. If you have already activated ER, you can continue using ER free of charge. The next private preview of ER is expected to begin in January 2021.

After ER is activated, you can use the [EdgeRoutine CLI](/intl.en-US/EdgeRoutine/Work with EdgeRoutine CLI.md) to submit JavaScript code to CDN nodes where the JavaScript code will be automatically deployed.

**Note:** ER is free of charge in private preview. When you write JavaScript code, take note of the following rules:

-   The code file must be smaller than 1 MB.
-   The CPU time for processing an individual request must be less than 50 milliseconds.
-   The response time for an individual request must be less than 120 seconds.
-   The total amount of consumed memory on an individual CDN node must be less than 128 MB.

Alibaba Cloud will release the pricing policy and limits on JavaScript code upon the official release of ER. For more information, see the product updates.

