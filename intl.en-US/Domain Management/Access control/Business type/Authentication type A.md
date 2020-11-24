---
keyword: [Alibaba Cloud CDN authentication, CDN authentication]
---

# Authentication type A

The URL authentication feature can help you protect resources on your origin server from unauthorized downloads and access. CDN supports three types of URL authentication. This topic describes the principle of URL authentication type A and provides an example.

## How it works

A URL is signed in the following format:

```
http://DomainName/Filename?auth_key=timestamp-rand-uid-md5hash
```

The following table describes the fields in a signed URL.

|Parameter|Description|
|:--------|:----------|
|DomainName|The domain name of the CDN node.|
|Filename|The actual URL that points to the requested resource on the origin server. The FileName field must start with a forward slash \(`/`\).|
|auth\_key|The cryptographic key that you have set.|
|timestamp|The expiration date of the cryptographic key. The value is a 10-digit positive integer. It specifies the number of seconds that have elapsed since 00:00:00 Thursday, 1 January 1970 plus the time-to-live \(TTL\) value of the cryptographic key. The TTL of the cryptographic key is set on the client. If it is set to 1,800 seconds, the cryptographic key expires 1,800 seconds after you connect to the CDN node. For example, if you set the connection time to 2020-08-15 15:00:00, the cryptographic key expires at 2020-08-15 15:30:00. |
|rand|The random number. The number must not contain hyphens `(-)`. Example: 477b3bbc253f467b8def6711128c7bec. We recommend that you use a UUID.|
|uid|The user ID. Set this field to 0.|
|md5hash|The string calculated by using the MD5 algorithm. It must be 32 characters in length and can contain digits and lowercase letters.|

When a CDN node receives a request, it determines whether the sum of the `timestamp` plus the `TTL of the cryptographic key` in the request is earlier than the current time.

-   If the sum of the `timestamp` plus the `TTL of the cryptographic key` is earlier than the current time, the CDN node determines that the cryptographic key expires and returns a 403 error.
-   If the sum of the `timestamp` plus the `TTL of the cryptographic key` is later than the current time, the CDN node generates a string in the same format as the `sstring` string. It then uses the MD5 algorithm to calculate the `HashValue`, and compares it with the `md5hash` in the request.

    -   If they are the same, the authentication succeeds. The CDN node returns the requested resource.
    -   If they are different, the authentication fails. The CDN node returns a 403 error.
    The `HashValue` is calculated based on the following string:

    ```
    sstring = "URI-Timestamp-rand-uid-PrivateKey". The URI specifies the address that points to the requested resource. It does not contain parameters such as /Filename.
    HashValue = md5sum(sstring)
    ```


## Example

The following example shows how to implement type-A authentication.

1.  Request the resource through `req_auth`.

    ```
    http:// cdn.example.com/video/standard/1K.html
    ```

2.  Set the cryptographic key to aliyuncdnexp1234.
3.  Set the expiration date of the authentication configuration file to 2015-10-10 00:00:00. Then, the validity period is 1,444,435,200 seconds.
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


If the `HashValue` calculated by the CDN node is the same as the `md5hash` contained in the request \(both are 80cd3862d699b7118eed99103f2a3a4f\), the request passes the authentication. Otherwise, the authentication fails.

