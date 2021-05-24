# Configure remote authentication

Alibaba Cloud Content Delivery Network \(CDN\) supports the remote authentication feature. This feature redirects client requests to a specified authentication server to check whether the requests are authorized. If a request passes the authentication, the request is redirected to CDN nodes. If a request fails the authentication, the request is rejected or requests from the client are throttled. This protects resources on CDN nodes from unauthorized access.

## How it works

Remote authentication is used to regulate access control. This feature checks the authenticity of requests that are destined for CDN nodes and processes the requests based on the authentication results.

Remote authentication is similar to URL signing. Both are used to protect resources from unauthorized access. Only authorized requests can retrieve resources from Alibaba Cloud CDN. The differences between remote authentication and URL signing are:

-   URL signing: After you apply authentication rules that are created for a domain name to CDN nodes, the CDN nodes handle the entire authentication process.
-   Remote authentication: You can specify a self-managed authentication server. After CDN nodes receive client requests, the requests are redirected to the specified authentication server.

The following figure shows how remote authentication works.

![How remote authentication works](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8549355161/p245797.png)

|No.|Description|
|---|-----------|
|①|A client sends a request to a CDN node. The request carries parameters that are used for authentication.|
|②|After the CDN node receives the request, it redirects the request to the authentication server.|
|③|The authentication server checks the parameters carried in the request and returns the authentication result to the CDN node.|
|④|The CDN node performs the specified action based on the authentication result and returns data to the client. Examples:

-   Example 1: The request passes the authentication. The CDN node returns the requested resources to the client.
-   Example 2: The request fails the authentication. The CDN node returns the 404 HTTP status code to the client.
-   Example 3: The request fails the authentication. The CDN node throttles requests sent from the client.
-   Example 4: The authentication process times out. The CDN node performs the specified action, for example, the allow action. |

## Procedure

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Access Control**.

5.  Click the **Remote Authentication** tab.

6.  Turn on **Remote Authentication** and follow the instructions to set the parameters.

    **Note:** After remote authentication is enabled, the authentication server checks each received request. If you estimate a large number of requests to be sent to CDN nodes, make sure that the authentication server can handle traffic spikes without compromising performance.

    |Parameter|Description|
    |---------|-----------|
    |**Authentication Server Address**|Enter the address of the authentication server. This address must allow the authentication server to access the Internet. Alibaba Cloud CDN checks the specified server address and its format.     -   Supported formats

Enter the server address in one of the following formats:

        -   http://example.com/auth
        -   https://example.com/auth
        -   http://192.0.2.1/auth
        -   https://192.0.2.1/auth
    -   Address requirements

The server address cannot contain the string 127.0.0.1 or localhost. Otherwise, the server address is invalid. |
    |**Request Method**|Select a request method that is supported by the authentication server. GET, HEAD, and POST are supported. The default request method is GET.|
    |**File Types**|    -   **All**: All file types are checked by the authentication server.
    -   **Specified**: Only the specified file types are checked by the authentication server.
        -   You can specify one or more file types. Separate multiple file types with vertical bars \(\|\). Example: mp4\|flv.
        -   File types are case-sensitive. jpg and JPG are considered different file types. |
    |**Parameters to Retain**|This parameter specifies the URL parameters to be checked by the authentication server. You can select one of the following options: Retain All Parameters, Retain Specified Parameters, and Delete All URL Parameters.     -   When you specify parameters to be retained, separate multiple parameters with vertical bars \(\|\). Example: user\|token.
    -   Parameters are case-sensitive. key and KEY are considered different parameters. |
    |**Custom Parameters**|You can require CDN nodes to add custom parameters to the URLs of requests before they are redirected to the authentication server. You can specify key-values pairs or select variables provided by Alibaba Cloud CDN.     -   When you specify key-value pairs, take note of the following rules:
        -   Separate multiple values with vertical bars \(\|\). Example: token=$arg\_token\|vendor=ali\_cdn.
        -   Values are case-sensitive. key and KEY are considered different values.
    -   If you select variables provided by Alibaba Cloud CDN, the values of the selected variables are added to client requests before they are redirected to the authentication server.

For example, if you select the value $http\_host, host=$http\_host is added to the URLs of requests before they are redirected to the authentication server. In this case, host indicates the Host field in the request header. For more information about the variables, see [Variables](#section_hn0_h9w_g6l). |
    |**Request Headers to Retain**|This parameter specifies the request headers to be checked by the authentication server. You can select one of the following options: Retain All Request Headers, Retain Specified Request Headers, and Delete All Request Headers.     -   When you specify request headers to be retained, separate multiple request headers with vertical bars \(\|\). Example: user\_agent\|reffer\|cookies.
    -   Request headers are not case-sensitive. http\_remote\_addr and HTTP\_Remote\_Addr are considered the same request header.
**Note:** If you select Retain All Request Headers, CDN nodes delete the Host header from requests. If you want to retain the Host header in requests, you can select Retain Specified Request Header or set the Custom Parameters parameter. CDN nodes delete the Host header from requests by default because the Host header carried in requests that are redirected to the authentication server specifies the accelerated domain name. The authentication server may fail to identify these requests and cause errors such as the HTTP 404 status code and authentication failures. |
    |**Custom Parameters**|You can require CDN nodes to add custom request headers to requests before they are redirected to the authentication server. You can specify key-value pairs or select variables provided by Alibaba Cloud CDN.     -   When you specify key-value pairs, take note of the following rules:
        -   Separate multiple values with vertical bars \(\|\). Example: User-Agent=$http\_user\_agent\|vendor=ali\_cdn.
        -   Request headers are not case-sensitive. http\_remote\_addr and HTTP\_Remote\_Addr are considered the same request header.
    -   If you select variables provided by Alibaba Cloud CDN, the values of the selected variables are added to client requests before they are redirected to the authentication server.

For example, if you select the value $http\_host, host=$http\_host is added to the URLs of requests before they are redirected to the authentication server. In this case, host indicates the Host field in the request header. For more information about the variables, see [Variables](#section_hn0_h9w_g6l). |
    |**Passes Authentication**|This parameter specifies the HTTP status code returned by the authentication server if a request passes the authentication. The HTTP status code indicates the authentication result. If you set the HTTP status code to 200, the authentication server returns the HTTP 200 status code to CDN nodes for client requests that pass the authentication. If the HTTP status code returned by the authentication server does not indicate whether the request passes or fails the authentication, the authentication on the request times out. |
    |**Fails Authentication**|This parameter specifies the HTTP status code returned by the authentication server if a request fails the authentication. The HTTP status code indicates the authentication result. If you set the HTTP status code to 403, the authentication server returns the HTTP 403 status code to CDN nodes for client requests that fail the authentication. If the HTTP status code returned by the authentication server does not indicate whether the request passes or fails the authentication, the authentication on the request times out. |
    |**Custom HTTP Status Code**|This parameter specifies the HTTP status code returned from the CDN node to the client after the CDN node receives an HTTP status code, which indicates that the request fails the authentication, from the authentication server. If you set the HTTP status code to 403, the CDN node returns the HTTP 403 status code to clients for requests that fail the authentication. |
    |**Timeout**|The timeout period starts when the CDN node redirects a request to the authentication server and ends when the CDN node receives the authentication result from the authentication server. The timeout period is measured in milliseconds. You can set the timeout period to at most 3,000 milliseconds.|
    |**Action After Timeout**|This parameter specifies the action that the CDN node performs on a request if the authentication on the request times out. **Allow** and **Reject** are supported:    -   **Allow**: If the authentication on the request times out, the CDN node returns the requested resources to the client.
    -   **Reject**: If the authentication on the request times out, the CDN node rejects the request and returns the HTTP status code specified in the **Custom HTTP Status Code** field to the client. |

7.  Click **OK**.

    After remote authentication is configured, you can modify the settings or disable remote authentication on the **Remote Authentication** tab.


## Variables

When you add custom parameters, you can select variables provided by Alibaba Cloud CDN. The following table describes the variables.

|Variable|Description|
|--------|-----------|
|$http\_host|Indicates the value of the Host header field.|
|$http\_user\_agent|Indicates the value of the User-Agent header field.|
|$http\_referer|Indicates the value of the Referfer header field.|
|$http\_content\_type|Indicates the value of the Content-Type header field.|
|$http\_x\_forward\_for|Indicates the value of the X-Forward-For header field.|
|$remote\_addr|Indicates the client IP address.|
|$scheme|Indicates the protocol of the request.|
|$server\_protocol|Indicates the protocol version of the request.|
|$uri|Indicates the original URI of the request.|
|$args|Indicates the query string of the request URL. The query string does not include the question mark \(?\).|
|$request\_method|Indicates the request method.|
|$request\_uri|Indicates the content of uri+'?'+args.|

## Related API operations

[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md)

