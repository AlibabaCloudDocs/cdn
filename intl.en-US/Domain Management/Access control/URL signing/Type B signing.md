---
keyword: [Alibaba Cloud CDN authentication, CDN authentication]
---

# Type B signing

Alibaba Cloud Content Delivery Network \(CDN\) provides the URL signing feature to protect origin servers from unauthorized downloads or access. The URL signing feature supports three signing types. This topic describes how type B signing works.

## How it works

Format of signed URLs:

```
http://DomainName/timestamp/md5hash/FileName
```

Format of actual URLs that point to the requested resources:

```
http://DomainName/FileName
```

The following table describes the fields in a signed URL.

|Parameter|Description|
|:--------|:----------|
|DomainName|The accelerated domain name.|
|timestamp|The time when the URL expires. The time is included in the URL and is used to calculate the `md5hash`. The time follows the YYYYMMDDHHMM format. The time-to-live \(TTL\) value of a URL is 1,800 seconds. For example, if you set the access time to 15:00:00 \(UTC+8\) on August 15, 2020 \(2020-08-15 15:00:00\), the request URL expires at 15:30:00 \(UTC+8\) on August 15, 2020 \(2020-08-15 15:30:00\). |
|md5hash|The string that is calculated by using the MD5 algorithm. The string must be 32 characters in length, and can contain digits and lowercase letters.|
|Filename|The actual URL that points to the requested resource on the origin server. The FileName field must start with a forward slash \(`/`\).|

## Example

The following example shows how to implement type B signing.

1.  Retrieve the following object from the origin server.

    ```
    http://cdn.example.com/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3
    ```

2.  Set the key to aliyuncdnexp1234.
3.  Set the time when the origin server is accessed to 201508150800.
4.  The CDN node constructs a signature string to calculate the `Hashvalue`.

    ```
    aliyuncdnexp1234201508150800/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3
    ```

5.  Alibaba Cloud CDN calculates the `md5hash` value based on the signature string `Hashvalue`.

    ```
    md5hash = md5sum("aliyuncdnexp1234201508150800/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3") = 9044548ef1527deadafa49a890a377f0
    ```

6.  Sign the URL.

    ```
    http://cdn.example.com/201508150800/9044548ef1527deadafa49a890a377f0/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3
    ```


If the `md5hash` value calculated by Alibaba Cloud CDN is the same as the `md5hash` contained in the request \(both are 9044548ef1527deadafa49a890a377f0 in this example\), the request passes the authentication. Otherwise, the request fails the authentication.

