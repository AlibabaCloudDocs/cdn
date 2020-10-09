# Terms

This topic introduces the common terms of Alibaba Cloud Content Delivery Network \(CDN\) to help you understand and use features of Alibaba Cloud CDN.

## Accelerated domain name

An accelerated domain name is a domain name that uses Alibaba Cloud CDN to accelerate content delivery. A domain name is the address of a group of servers, such as web servers, email servers, and FTP servers.

## CNAME record

A canonical name \(CNAME\) record is an alias record used to map a domain name to another domain name that provides an IP address. Example:

1.  The domain name `docs.example.com` can be used to access the data stored on your server. However, you also want the data to be accessible through the domain name `documents.example.com`.
2.  You can add a CNAME record to the Domain Name System \(DNS\) server to map `documents.example.com` to `docs.example.com`.
3.  After you add the CNAME record, all requests sent to `documents.example.com` are redirected to `docs.example.com`.

## CNAME

After you add a domain name to Alibaba Cloud CDN, the domain name is assigned a CNAME. The CNAME is in the format of `*.*kunlun*.com`. You must add a CNAME record to the DNS server to map the accelerated domain name to `*.*kunlun*.com`. After the CNAME record takes effect, all requests sent to the accelerated domain name are redirected to a CDN node. This enables Alibaba Cloud CDN to accelerate content delivery.

## DNS

Domain Name System \(DNS\) is a service used to resolve domain names to the corresponding IP addresses that can be recognized by machines. One domain name is mapped to one IP address. The process to map a domain name to the corresponding IP address is called DNS resolution. A dedicated DNS server is used to automatically resolve domain names to the corresponding IP addresses. For example, if you enter `www.baidu.com` into the address bar of your browser, the DNS server automatically resolves the domain name to `220.181.112.143`.

## SSL/TLS

Secure Sockets Layer \(SSL\) is a TCP-based secure communication protocol. It helps to ensure the integrity and security of data transmitted over the Internet. After SSL is standardized, its name is changed to Transport Layer Security \(TLS\). Therefore, SSL and TLS are collectively known as SSL/TLS.

## Edge node

In the documentation of Alibaba Cloud CDN, an Alibaba Cloud edge node is also referred as a CDN node, cache node, acceleration node, Alibaba Cloud node, or node. The purpose of edge nodes is to simplify the complex network structure. Edge nodes are located closer to users on the network and are more efficient compared with origin servers. Alibaba Cloud CDN caches frequently accessed content to edge nodes to improve user experience.

## Origin server

An origin server is the server where your actual workloads are running. When you add a domain name to Alibaba Cloud CDN, you can specify the origin server by using the domain name of an Object Storage Service \(OSS\) bucket, the IP address or domain name of a web server that is accessible to the Internet, or a Function Compute domain name.

## Back-to-origin

If a CDN node has not cached a resource that a client requests or the cached resource has expired, a back-to-origin process is triggered. The CDN node retrieves the resource from the corresponding origin server and then returns the resource to the client.

For example, when a user requests a resource through a URL, if the optimal CDN node whose geographic location is closest to the user has not cached the resource, the CDN node retrieves the resource directly from the origin server and then returns the resource to the user.

## Origin host

An origin host refers to the website domain name on the origin server accessed by a CDN node during a back-to-origin process.

Example 1: The origin server uses a domain name.

If the origin server is set to `www.a.com` and the origin host is set to `www.b.com`, Alibaba Cloud CDN requests content from the website `www.b.com` that is hosted on the origin server `www.a.com`.

Example 2: The origin server uses an IP address.

If the origin is set to 1.1.1.1 and the origin host is set to `www.b.com`, Alibaba Cloud CDN requests content from the website `www.b.com` that is hosted on the origin server 1.1.1.1.

## Origin protocol policy

The protocol policy that you want Alibaba Cloud CDN to use when it retrieves content from the origin server. If you set the origin protocol policy to Follow in the Alibaba Cloud CDN console, Alibaba Cloud CDN communicates with the origin server based on the protocol of the request. For example, if a client sends an HTTP request, Alibaba Cloud CDN communicates with the origin server also over HTTP.

## Parameter filtering

Parameter filtering is a feature provided by Alibaba Cloud CDN. You can enable or disable this feature to determine whether to ignore the parameters that follow the question mark \(`?`\) in the URL of each request when Alibaba Cloud CDN caches content from the origin server.

-   After parameter filtering is enabled, CDN nodes ignore the parameters following the question mark \(?\) in the URL to request content from the origin server when the requested content is accessed for the first time. Then, CDN nodes cache one version of the retrieved content and serve all subsequent requests with the cached version.
-   After parameter filtering is disabled, CDN nodes cache a version of the requested content for each request with a unique URL that includes parameters.

If URLs with different parameters point to the same resource, we recommend that you enable this feature to increase the cache hit ratio.

