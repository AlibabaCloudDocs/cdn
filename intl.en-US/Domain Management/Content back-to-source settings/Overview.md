# Overview {#concept_1236742 .concept}

When you send a resource access request from a client, if CDN cannot find the resource on the CDN node, it retrieves the resource from the origin and then loads the resource to the CDN node. You can configure back-to-origin functions to accelerate access to CDN resources.

CDN supports the following back-to-origin functions.

|Function|Description|
|--------|-----------|
|[Configure an origin host](reseller.en-US/Domain Management/Content back-to-source settings/Configure an origin host.md#)|Allows you to specify the domain type of the origin host for CDN nodes retrieving resources from the origin.|
|[Configure an origin protocol](reseller.en-US/Domain Management/Content back-to-source settings/Configure an origin protocol.md#)|Allows you to configure an origin protocol policy for retrieving resources from the origin to CDN nodes when CDN cannot find the resources on CDN nodes.|
|[EN-US\_TP\_5143.md\#](reseller.en-US/Domain Management/Content back-to-source settings/Enable private bucket back-to-origin authentication.md#)|Allows you to use private Object Storage Service \(OSS\) buckets as origins in order to prevent resource hotlinking.|
|[Disable private bucket back-to-origin authentication](reseller.en-US/Domain Management/Content back-to-source settings/Disable private bucket back-to-origin authentication.md#)|You can log on to the RAM console and remove authorization from a specified role to disable private bucket access.|
|[EN-US\_TP\_138897.md\#](reseller.en-US/Domain Management/Content back-to-source settings/Back-to-origin SNI.md#)|If CDN nodes access your origin over HTTPS and your origin IP address is bound to multiple domain names, then you must select a domain name for CDN by specifying the Server Name Indication \(SNI\) of the domain name.|
|[Customize an origin HTTP header](reseller.en-US/Domain Management/Content back-to-source settings/Customize an origin HTTP header.md#)|If you configure CDN to use HTTP to communicate with your origin, you can add or remove HTTP header fields.|
|[Set the origin request timeout period](reseller.en-US/Domain Management/Content back-to-source settings/Set the origin request timeout period.md#)|The default timeout period for a resource request sent from a CDN node to an origin is 30 seconds. You can customize the timeout period. If the CDN node does not receive any response before the timeout period expires, the CDN node disconnects from the origin.|

