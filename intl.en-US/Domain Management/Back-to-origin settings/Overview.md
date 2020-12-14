# Overview

If a client requests content that is not cached on the Alibaba Cloud Content Delivery Network \(CDN\) node, the node retrieves the content from the origin server. When the CDN node returns the retrieved content to the client, it also caches the content on the node. You can configure back-to-origin features based on your business requirements to improve the acceleration of content delivery.

Alibaba Cloud CDN supports the following back-to-origin features.

|Feature|Description|
|-------|-----------|
|[Configure an origin host](/intl.en-US/Domain Management/Back-to-origin settings/Configure an origin host.md)|You can specify the domain name type of the origin host to which back-to-origin requests are redirected.|
|[Configure the origin protocol policy](/intl.en-US/Domain Management/Back-to-origin settings/Configure the origin protocol policy.md)|If a client requests content that is not cached on the CDN node, the node retrieves the content from the origin server. The origin protocol policy applies to the retrieval. When the CDN node returns the retrieved content to the client, it also caches the content on the node.|
|[Enable private bucket back-to-origin authorization](/intl.en-US/Domain Management/Back-to-origin settings/Enable private bucket back-to-origin authorization.md)|If Alibaba Cloud Object Storage Service \(OSS\) is used to serve origin content, you can grant permissions to Alibaba Cloud CDN to access an OSS private bucket through an accelerated domain name. This prevents resource hotlinking.|
|[Disable private bucket back-to-origin authorization](/intl.en-US/Domain Management/Back-to-origin settings/Disable private bucket back-to-origin authorization.md)|You can log on to the Resource Access Management \(RAM\) console and revoke permissions of the RAM role for Alibaba Cloud CDN. This allows you to disable access to OSS private buckets.|
|[Configure an origin SNI](/intl.en-US/Domain Management/Back-to-origin settings/Configure an origin SNI.md)|If an origin IP address is associated with multiple domain names, you must set a Server Name Indication \(SNI\) value. This allows CDN nodes to access the origin server over HTTPS.|
|[Customize an HTTP header](/intl.en-US/Domain Management/Back-to-origin settings/Customize an HTTP header.md)|When you configure Alibaba Cloud CDN to communicate with origin servers over HTTP, you can add or remove HTTP headers.|
|[Set the origin request timeout period](/intl.en-US/Domain Management/Back-to-origin settings/Set the origin request timeout.md)|You can set the back-to-origin request timeout. The back-to-origin request timeout value specifies the amount of time that a CDN node waits for a response after a request is redirected to an origin server. The default back-to-origin request timeout value is 30 seconds. If the CDN node does not receive a response within the specified timeout period, the CDN node disconnects from the origin server.|

