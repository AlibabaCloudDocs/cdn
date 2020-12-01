---
keyword: [Alibaba Cloud CDN authentication, CDN authentication]
---

# Type A signing

Alibaba Cloud Content Delivery Network \(CDN\) provides the URL signing feature to protect origin servers from unauthorized downloads and access. The URL signing feature supports three signing types. This topic describes how type A signing works.

## How it works

URLs are signed in the following format:

```
http://DomainName/Filename?auth_key=timestamp-rand-uid-md5hash
```

The following table describes the fields in a signed URL.

|Parameter|Description|
|:--------|:----------|
|DomainName|The accelerated domain name.|
|Filename|The actual URL that points to the requested resource on the origin server. The FileName field must start with a forward slash \(`/`\).|
|auth\_key|The cryptographic key that you have set.|
|timestamp|The time when a URL expires. The value is a 10-digit positive integer. It specifies the number of seconds that have elapsed since 00:00:00 \(UTC+8\) on January 1, 1970 and the time-to-live \(TTL\) value of the cryptographic key. The TTL value of the cryptographic key is set on user clients. If the TTL value is set to 1,800 seconds by a user when they initiate a request, the URL of the request expires 1,800 seconds after the client connects to the CDN node. For example, if a user sets the connection time to 15:00:00 \(UTC+8\) on August 15, 2020 \(2020-08-15 15:00:00\), the URL of the request expires at 15:30:00 \(UTC+8\) on August 15 \(2020-08-15 15:30:00\). |
|rand|A random number. The number must not contain hyphens \(`-`\). Example: 477b3bbc253f467b8def6711128c7bec. We recommend that you advise you uses to use a UUID.|
|uid|The user ID. Set this field to 0.|
|md5hash|The string that is calculated by using the MD5 algorithm. It must be 32 characters in length, and can contain digits and lowercase letters.|

When a CDN node receives a request, the CDN node determines whether the time calculated by adding the `timestamp` and the `TTL value of the cryptographic key` in the request is earlier than the current time.

-   If the time calculated by adding the `timestamp` and the `TTL value of the cryptographic key` is earlier than the current time, the CDN node determines that the URL of the request expires and returns a 403 error.
-   If the time calculated by adding the `timestamp` and the `TTL of the cryptographic key` is later than the current time, the CDN node generates a string in the same format as the `sstring` string. It then uses the MD5 algorithm to calculate the `HashValue`, and compares it with the `md5hash` value in the request.

    -   If they are the same, the request passes the authentication. The CDN node returns the requested resource.
    -   If they are different, the request fails the authentication. The CDN node returns a 403 error.
    The `HashValue` is calculated based on the following string:

    ```
    sstring = "URI-Timestamp-rand-uid-PrivateKey". The URI specifies the address that points to the requested resource. It does not contain parameters such as /Filename.
    HashValue = md5sum(sstring)
    ```


## Example

The following example shows how to implement type A signing.

1.  Request resources through `req_auth`.

    ```
    http:// cdn.example.com/video/standard/1K.html
    ```

2.  Set the cryptographic key to aliyuncdnexp1234.
3.  Set the expiration time of the authentication configuration file to 00:00:00 \(UTC+8\) on October 10, 2015 \(2015-10-10 00:00:00\). Therefore, the validity period is 1,444,435,200 seconds.
4.  The CDN node generates a signature string to calculate the `HashValue`.

    ```
    /video/standard/1K.html-1444435200-0-0-aliyuncdnexp1234
    ```

5.  The CDN node calculates the `HashValue` based on the signature string.

    ```
    HashValue = md5sum("/video/standard/1K.html-1444435200-0-0-aliyuncdnexp1234") = 80cd3862d699b7118eed99103f2a3a4f
    ```

6.  Sign the request URL.

    ```
    http://cdn.example.com/video/standard/1K.html?auth_key=1444435200-0-0-80cd3862d699b7118eed99103f2a3a4f
    ```


If the `HashValue` calculated by the CDN node is the same as the `md5hash` value contained in the request \(both are 80cd3862d699b7118eed99103f2a3a4f in this example\), the request passes the authentication. Otherwise, the request fails the authentication.

