# Basic security features

This topic describes the basic security features provided by Alibaba Cloud Content Delivery Network \(CDN\).

Alibaba Cloud CDN provides the following basic security features:

-   Hotlink protection

    The referer header field in a HTTP request can be used to trace and identify the source of the HTTP request. You can configure hotlink protection based on the referer field to filter requests. In the Alibaba Cloud CDN console, you can configure a referer whitelist or blacklist to specify whether requests that contain empty referer header fields are allowed. Hotlink protection filters source host addresses by URL. You can specify source addresses in the referer whitelist or blacklist. The referer whitelist and blacklist are mutually exclusive. You can use them to implement access control. For more information, see [Configure hotlink protection](/intl.en-US/Domain Management/Access control/Configure hotlink protection.md).

-   IP address blacklist.

    You can configure an IP address blacklist to restrict requests from the specified IP addresses. For more information, see [Configure an IP address blacklist or whitelist](/intl.en-US/Domain Management/Access control/Configure an IP blacklist or whitelist.md).

-   URL signing

    The URL signing feature protects origin servers from unauthorized access. You can configure a rule for signing specific URLs with the key information provided in the specified signing type. This feature can be used to authenticate requests that attempt to access classified files. Clients have to calculate a temporary signature for each request. We recommend that you do not enable this feature for the delivery of unclassified files. Compared with the use of unsigned URLs, it takes more time to retrieve resources from origin servers. For more information, see [Configure URL signing](/intl.en-US/Domain Management/Access control/URL signing/Configure URL signing.md).


