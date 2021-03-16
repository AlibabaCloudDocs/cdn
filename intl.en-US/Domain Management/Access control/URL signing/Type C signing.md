---
keyword: [Alibaba Cloud CDN authentication, CDN authentication]
---

# Type C signing

The URL signing feature protects resources on origin servers from unauthorized access and downloads. The URL signing feature supports three signing types. This topic describes how type C signing works.

## How it works

URLs are signed in one of the following formats:

-   Format 1

    ```
    http://DomainName/{<md5hash>/<timestamp>}/FileName
    ```

-   Format 2

    ```
    http://DomainName/FileName{&KEY1=<md5hash>&KEY2=<timestamp>}
    ```


**Note:** The content enclosed by braces \(`{}`\) indicates the encrypted information that is added based on the standard URL format.

The following table describes the fields in a signed URL.

|Parameter|Description|
|:--------|:----------|
|DomainName|The accelerated domain name.|
|FileName|The actual URL that points to the requested resource on the origin server. The FileName field must start with a forward slash \(`/`\).|
|timestamp|The time when the origin server is accessed. The time must be in the UNIX format. It is an unencrypted plaintext string that is 10 digits in length. The string indicates the number of seconds that have elapsed since January 1, 1970. The number is a hexadecimal value.|
|md5hash|The string that is calculated by using the MD5 algorithm. The string must be 32 characters in length, and can contain digits and lowercase letters.|

## Example

The following example shows how to implement type C signing.

-   Set the value of the PrivateKey field to `aliyuncdnexp1234`.
-   Set the value of the FileName field to `/test.flv`.
-   Set the value of the timestamp field to `55CE8100`.
-   Calculate the MD5 hash value. The result is:

    ```
    md5hash = md5sum(aliyuncdnexp1234/test.flv55CE8100) = a37fa50a5fb8f71214b1e7c95ec7a1bd
    ```

-   A signed URL is generated in one of the following formats:
    -   Format 1:

        ```
        http://cdn.example.com/a37fa50a5fb8f71214b1e7c95ec7a1bd/55CE8100/test.flv
        ```

    -   Format 2:

        ```
        http://cdn.example.com/test.flv?KEY1=a37fa50a5fb8f71214b1e7c95ec7a1bd&KEY2=55CE8100
        ```


When you use a signed URL to access a CDN node, the CDN node extracts encrypted String 1 and obtains the `FileName` and access time of the unsigned URL. The CDN node performs the following steps to authenticate the request based on the defined business logic:

1.  The CDN node uses the `Filename`, access time, and `PrivateKey` of the unsigned URL to perform MD5 encryption. Encrypted String 2 is generated.
2.  The CDN node compares String 1 with String 2. If the two strings are different, the request is rejected.
3.  The CDN node checks whether the difference between the current time and the time in the unsigned URL has exceeded the validity period specified by t. The default value of t is 1,800 seconds.

    -   If the time difference is less than the specified validity period, the CDN node responds to the request.
    -   If the time difference is greater than the specified validity period, the CDN node rejects the request and returns a 403 error.
    **Note:** The TTL value of 1,800 seconds indicates that a request fails authentication if the difference between the time the request accesses the origin server and the preset access time in the URL is greater than 1,800 seconds. For example, if you set the access time to 15:00:00 \(UTC+8\) on August 15, 2020 \(2020-08-15 15:00:00\), the URL expires at 15:30:00 \(UTC+8\) on August 15, 2020 \(2020-08-15 15:30:00\).


