# Features of EdgeRoutine

EdgeRoutine \(ER\) is a serverless computing environment provided by Alibaba Cloud Content Delivery Network \(CDN\). It can run custom JavaScript code on CDN nodes. After you use the EdgeRoutine command-line interface \(CLI\) to deploy code to the production environment, the system automatically runs the code on all CDN nodes. The CDN nodes process requests in different regions worldwide by following the logical rules of the code.

![Features of EdgeRoutine](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8427271161/p211835.png)

## Benefits

Traditional CDN services are used to only cache and distribute content, but cannot provide the computing feature for workloads. To process a large number of requests that are sent to CDN nodes, Alibaba Cloud CDN must redirect the requests to origin servers that support complex computing. This back-to-origin process consumes resources on origin servers and requires a complex origin architecture. ER enables CDN nodes to provide the computing feature. You can use ER to customize your Alibaba Cloud CDN service and process complex requests. This feature reduces the number of back-to-origin requests and accelerates content delivery. CDN nodes support high availability, high scalability, and global load balancing. These features allow CDN nodes to support computing in more scenarios. ER provides a computing environment on each CDN node and allows you to run custom JavaScript code on CDN nodes. You do not need to be concerned about the hardware configuration, region, scheduling, and auto scaling for code deployment.

## How it works

ER runs on CDN nodes and provides a serverless JavaScript runtime environment for you to deploy JavaScript code.

![How it works](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8427271161/p86758.png)

-   Scenarios where ER is not used

    Client requests are processed in the following steps: 1→8→9→4. After a client sends a request to the CDN gateway, Alibaba Cloud CDN searches for the requested resource in the CDN cache. If the requested resource is not cached on CDN nodes, the request is redirected to the origin server to retrieve the requested resource. If the requested resource is cached on CDN nodes, the requested resource is directly returned to the client.

-   Scenarios where ER is used
    -   ER runs JavaScrip code to compute and process requests and returns data to clients. Client requests are processed in the following steps: 1→2→3→4. This process is a typical scenario of Function as a Service \(FaaS\). ER functions as the server and directly processes and responds to requests. In this scenario, you do not need to deploy servers.
    -   ER initiates subrequests to retrieve data from other cloud services and processes the data. Client requests are processed in the following steps: 1→2→5→3→4.
    -   ER stores processed data to or reads processed data from the cache or key-value \(KV\) storage media. Client requests are processed in the following steps: 1→2→6→3→4.
    -   ER can automatically use a proxy to redirect requests to the standard CDN back-to-origin process. Client requests are processed in the following steps: 1→2→7→8→9→10→3→4. In this process, ER applies computing logic before it follows the standard CDN process. You can use ER to perform relevant computing tasks such as remote asynchronous authentication before Alibaba Cloud CDN follows the standard process to search for requested resources in the CDN cache or redirect requests to origin servers.

## Scenarios

ER provides a fully integrated JavaScript runtime environment that allows you to manage comprehensive logic of request processing. You can also use ER to enable CDN nodes to asynchronously retrieve content from origin servers over HTTP or HTTPS. ER can be used in a wide array of scenarios. The following table lists the scenarios that are supported by ER.

|Scenario|Feature|
|--------|-------|
|Authentication|Custom Alibaba Cloud CDN authentication and asynchronous authentication|
|Originless responses|Static content delivery|
|Network security|-   Anti-bot protection
-   Web Application Firewall \(WAF\) deployed on edges |
|Logs|-   Automatic logging on CDN nodes
-   Recording of back-to-origin time |
|DevOps|-   A/B testing
-   Webhooks for GitLab, GitHub, and Jenkins
-   Programming of instant messaging robots, such as Slack robots |
|API Gateway|-   Edge GraphQL
-   Edge gateway:
    -   Network traffic throttling
    -   API parameter validation |
|CDN|-   Prefetching content to CDN nodes
-   Caching content on CDN nodes
-   Redirecting requests from CDN nodes to multiple origin servers:
    -   Merging content returned from multiple origin servers
    -   Optimized redirection with the lowest latency |
|Web applications and applets|-   Edge rendering:
    -   Markdown rendering
    -   Edge Side Includes \(ESI\) rendering
    -   Nunjucks rendering
-   Edge server-side rendering \(SSR\):
    -   Vue.js
    -   React.js
-   Content prefetching and reduction of web page loading time
-   Diverse services on CDN nodes, such as QR code generation |
|Beacon|Capturing and analytics of edge tracking data|

## Work with ER

The first private preview of ER is completed. If you have activated ER during the preview, you can continue to use ER free of charge. The next private preview of ER is expected to begin in April 2021.

After ER is activated, you can use the [EdgeRoute CLI](/intl.en-US/EdgeRoutine/Work with EdgeRoutine CLI.md) to submit JavaScript code to CDN nodes. If you have questions, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).

**Note:** ER is free of charge during private preview. When you write JavaScript code, take note of the following limits:

-   The code file must be smaller than 1 MB.
-   The CPU time that is consumed to process an individual request must be less than 50 milliseconds.
-   The response time for an individual request must be less than 120 seconds.
-   The total amount of memory consumed on an individual CDN node must be less than 128 MB.

Alibaba Cloud will release the pricing policy and limits on JavaScript code upon the official release of ER. For more information, see the product updates.

