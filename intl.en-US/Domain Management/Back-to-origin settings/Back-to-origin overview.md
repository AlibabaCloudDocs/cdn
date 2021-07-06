# Back-to-origin overview

If a client requests content that is not cached on Alibaba Cloud Content Delivery Network \(CDN\) nodes, the nodes retrieve the requested content from the origin server. After a CDN node returns the retrieved content to the client, the CDN node also caches the content on the node. You can configure back-to-origin features based on your business requirements to accelerate content delivery.

Alibaba Cloud CDN supports the following back-to-origin features.

|Feature|Description|
|-------|-----------|
|[Configure an origin host](/intl.en-US/Domain Management/Back-to-origin settings/Configure an origin host.md)|Allows you to specify the domain type of the origin host for CDN nodes to retrieve resources from the origin server.|
|[Configure the origin protocol policy](/intl.en-US/Domain Management/Back-to-origin settings/Configure the origin protocol policy.md)|Allows you to configure an origin protocol policy for CDN nodes to retrieve resources from the origin server if the requested resources are not cached on CDN nodes, and cache the retrieved resources on CDN nodes|
|[Grant Alibaba Cloud CDN access permissions on a private OSS bucket](/intl.en-US/Domain Management/Back-to-origin settings/Grant Alibaba Cloud CDN access permissions on a private OSS bucket.md)|Allows you to use private Object Storage Service \(OSS\) buckets as origin servers to prevent hotlink issues.|
|[Disable access to private OSS buckets](/intl.en-US/Domain Management/Back-to-origin settings/Disable access to private OSS buckets.md)|Allows you to log on to the Resource Access Management \(RAM\) console and revoke permissions that are granted to a specified role to disable access to private OSS buckets.|
|[Configure SNI](/intl.en-US/Domain Management/Back-to-origin settings/Configure SNI.md)|If CDN nodes access your origin over HTTPS and the IP address of the origin server is associated with multiple domain names, you must configure Server Name Indication \(SNI\) to specify the domain name that CDN nodes can access.|
|[Configure an HTTP header for back-to-origin requests](/intl.en-US/Domain Management/Back-to-origin settings/Configure an HTTP header for back-to-origin requests.md)|Allows you to add HTTP headers to or delete HTTP headers from back-to-origin requests when Alibaba Cloud CDN communicates with origin servers over HTTP.|
|[Set a timeout period for back-to-origin requests](/intl.en-US/Domain Management/Back-to-origin settings/Set a timeout period for back-to-origin requests.md)|Allows you to set a timeout period for back-to-origin requests. The timeout period specifies the amount of time that a CDN node waits for a response after a request is redirected to the origin server. The default timeout period is 30 seconds. If the CDN node does not receive a response within the specified timeout period, the CDN node disconnects from the origin server.|
|[Rewrite URIs in back-to-origin requests](/intl.en-US/Domain Management/Back-to-origin settings/Rewrite URIs in back-to-origin requests.md)|Allows you to create rules to rewrite Uniform Resource Identifiers \(URIs\) of requests before they are redirected to origin servers.|
|[Rewrite URL parameters in back-to-origin requests](/intl.en-US/Domain Management/Back-to-origin settings/Rewrite URL parameters in back-to-origin requests.md)|Allows you to create rules to rewrite URL parameters of requests before they are redirected to origin servers.|
|[Rewrite HTTP headers in back-to-origin requests](/intl.en-US/Domain Management/Back-to-origin settings/Rewrite HTTP headers in back-to-origin requests.md)|Allows you to rewrite HTTP headers of requests before they are redirected to origin servers.|
|[Rewrite HTTP headers in responses from an origin server](/intl.en-US/Domain Management/Back-to-origin settings/Rewrite HTTP headers in responses from an origin server.md)|Allows you to rewrite HTTP header of responses from origin servers.|

