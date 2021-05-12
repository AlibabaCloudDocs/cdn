---
keyword: [CDN, API]
---

# Make API requests

To send an Alibaba Cloud Content Delivery Network \(CDN\) API request, you must send an HTTP GET request to the Alibaba Cloud CDN endpoint. You must add the request parameters that correspond to the API operation that you want to call. After you call the API, the system returns a response.

## Request syntax

Alibaba Cloud CDN API operations use the RPC protocol. You can call Alibaba Cloud CDN API operations by sending HTTP GET requests. Alibaba Cloud CDN supports both HTTP and HTTPS requests. For data security, we recommend that you send HTTPS requests. The request and response are encoded in UTF-8. Request syntax:

```
https://Endpoint/?Action=xx&Version=xx&Parameters
```

-   Endpoint: the endpoint of the Alibaba Cloud CDN API is cdn.aliyuncs.com.
-   Action: the name of the operation that you want to perform. For example, to add a domain name to Alibaba Cloud CDN, you must set the Action parameter to AddCdnDomain.
-   Version: the version of the Alibaba Cloud CDN API. Set the value to 2018-05-10.
-   Parameters: the request parameters for the operation. Separate multiple parameters with ampersands \(`&`\). Request parameters include both common request parameters and operation-specific parameters. Common request parameters include the API version number, authentication information, and other information. For more information, see [Common request parameters](/intl.en-US/New API Reference/Common request parameters.md).

The following example demonstrates how to call the StartCdnDomain operation in Alibaba Cloud CDN.

**Note:** The following code has been formatted to improve readability.

```
http://cdn.aliyuncs.com?Action=StartCdnDomain
&DomainName=example.com
&Format=XML
&AccessKeyId=xxx
&SignatureMethod=HMAC-SHA1
&SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf
&Version=2018-05-10
&SignatureVersion=1.0
...
```

## Request signatures

Alibaba Cloud CDN uses the request signature to verify the identity of the API caller. You must sign all API requests whether they are sent over HTTP or HTTPS. For more information about how signatures are calculated, see [Signature method](/intl.en-US/New API Reference/Signature method.md).

Alibaba Cloud CDN implements symmetric encryption with an AccessKey pair to verify the identity of the request sender. An AccessKey pair consists of an `AccessKey ID` and an `AccessKey secret`. An AccessKey pair is an identity credential issued to Alibaba Cloud accounts and Resource Access Management \(RAM\) users that is similar to a pair of logon username and password.

**Note:**

-   The `AccessKey ID` is used to verify the identity of the user.
-   The `AccessKey secret` is used to encrypt and verify the signature string. You must keep your AccessKey secret strictly confidential.

You can create an AccessKey pair for an Alibaba Cloud account or a RAM user. When you call the Alibaba Cloud CDN API, you must use your AccessKey pair to complete identity verification. If the AccessKey pair of your Alibaba Cloud account is leaked, all your resources may be compromised. We recommend that you call API operations as a RAM user to minimize the risk of leaking your AccessKey pair. For more information, see [Create an AccessKey pair]().

The following example demonstrates how to call the StartCdnDomain operation. The `AccessKeyId` parameter is set to `testid` and the `AccessKeySecret` parameter is set to `testsecret`. The request URL to be signed is:

```
http://cdn.aliyuncs.com?Action=StartCdnDomain&DomainName=example.com
&Format=XML
&AccessKeyId=testid
&SignatureMethod=HMAC-SHA1
&SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf
&SignatureVersion=1.0
```

The signature string calculated by using `testsecret&`:

```
YGOjauEr2WSn6scXDxc9X0DKwsM=
```

Add the Signature parameter to the request and set the value to the calculated signature string. The URL of the signed request is:

```
http://cdn.aliyuncs.com?Action=StartCdnDomain&DomainName=example.com
&Format=XML
&AccessKeyId=testid
&SignatureMethod=HMAC-SHA1
&SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf
&SignatureVersion=1.0
&Signature=YGOjauEr2WSn6scXDxc9X0DKwsM=
```

Alibaba Cloud CDN provides the following sample code for signature calculation:

-   [Python](https://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/109895/cn_zh/1561514315115/cdn-api.zip)
-   [Java](https://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/109895/cn_zh/1561514338764/SignatureUtils.java)

