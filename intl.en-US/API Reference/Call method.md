# Call method

CDN API interfaces are called by sending an HTTP GET request to the CDN API server. Such requests are completed by adding the relevant request parameters in the request according to the interface instructions. Results will be returned based on the request’s processing status.

## Request Structure

Service Address

The CDN API service access address is: cdn.aliyuncs.com

Communication Protocol

The system supports request communication through HTTP or HTTPS channels. In order to ensure the security of the request, we recommend that you send requests through an HTTPS channel.

Request Methods

The system supports the sending of HTTP GET requests. For this method, the request parameters must be included in the request URL.

Request Parameters

For each request, the operation to be executed must be specified, namely the Action parameter \(e.g. OpenCdnService\), and each operation must contain the common request parameters and the specific request parameters of the specified operation.

Character encoding

Requests and returned results both use UTF-8 character set encoding.

## Common Parameters

Common Request Parameters

Common request parameters specify the request parameters that must be used by every interface.

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Format|String|No|Type of valuereturned, JSON and XML supported. The default value is XML.|
|Version|String|Yes|The API version, with the date format:YYYY-MMDD. The current version is 2014-11-11.|
|AccessKeyId|String|Yes|The secret key ID used to access services, issued to a user by Alibaba Cloud.|
|Signature|String|Yes|The signature result string. See the description of the signature mechanism for details on the signature calculation method.|
|SignatureMethod|String|Yes|The signature method, HMACSHA1 currently supported.|
|Timestamp|String|Yes|The request’s timestamp. The date format follows the ISO8601 standard and uses UTC time. Format: YYYY-MM-DDThh:mm:ssZ. E.g.:2014-11-11T12:00:00Z \(Equivalent to 11/11/2014 20:00:00 Beijing time\)|
|SignatureVersion|String|Yes|Signature algorithm version. The current version is 1.0.|
|SignatureNonce|String|Yes|A unique random number, used to prevent replay attacks. The user must use different random numbers for different requests.|

Request example:

```
https://cdn.aliyuncs.com/?Format=xml&Version=2014-11-11&Signature=Pc5WB8gokVn0xfeu%2FZV%2BiNM1dgI%3D&SignatureMethod=HMAC-SHA1&SignatureNonce=15215528852396&SignatureVersion=1.0&AccessKeyId=key-test&Timestamp=2012-06-01T12:00:00Z
```

Common return parameters

Each time the user sends a call request to an interface, no matter if it is successful or not, the system will return a unique identification code \(RequestId\) to the user.

Example of XML results returned:

```
<? xml version="1.0" encoding="UTF-8"? > 
<!--Result Root Node-->
<Interface Name+Response>
    <!--Return Request Tag-->
    <RequestId>4C467B38-3910-447D-87BC-AC049166F216</RequestId>
    <!--Return Result Data-->
</Interface Name+Response>
                
```

Example of XML results returned:

```

{
"RequestId": "4C467B38-3910-447D-87BC-AC049166F216",
/* Return Result Data */
}
```

Return result

After the API service is called, the returned data adopts a uniform format. A returned HTTP status code of 2xx indicates that the call was successful. A returned HTTP status code of 4xx or 5xx indicates that the call failed.

For successful calls, the primary formats of returned data are XML and JSON. When a request is sent, an external system can pass in parameters to specify the format of returned data. The default format is XML.

In this document, examples of results returned are formatted in a way that is easier for users to view. The actual results returned are not formatted with line breaks, indentation, etc.

Successful results

Example of XML results returned: \(XML results returned include a message stating if the request was successful and the specific service data.\)

```
<? xml version="1.0" encoding="UTF-8"? > 
<!--Result Root Node-->
<API name+Response>
    <!--Return Request Tag-->
    <RequestId>4C467B38-3910-447D-87BC-AC049166F216</RequestId>
    <!--Return Result Data-->
</Interface name+Response>
```

JSON example:

```
{
    "RequestId": "4C467B38-3910-447D-87BC-AC049166F216",
    /* Return result data */
}
```

Error results

After an error is encountered in an interface call, no result data will be returned. The caller can refer to the table in the appendix <Error Code Table\> to locate the cause of the error.

When an error occurs in a call, the HTTP request will return a HTTP status code of 4xx or 5xx. The returned message body includes the specific error code and error message. It also contains a globally unique request ID: RequestId and the ID of the site you accessed with this request: HostId. If the caller cannot find the cause of the error, he can contact Alibaba Cloud customer service and provide the HostId and RequestId to help us solve the problem as quickly as possible.

XML example:

```
<? xml version="1.0" encoding="UTF-8"? >
<Error>
<RequestId>8906582E-6722-409A-A6C4-0E7863B733A5</RequestId>
   <HostId>cdn.aliyuncs.com</HostId>
   <Code>UnsupportedOperation</Code>
   <Message>The specified action is not supported.</Message>
</Error>
```

JSON example:

```
{
    "RequestId": "8906582E-6722-409A-A6C4-0E7863B733A5",
    "HostId": "cdn.aliyuncs.com",
    "Code": "UnsupportedOperation",
    "Message": "The specified action is not supported."
}
```

## Signature Mechanism

Introduction

The CDN service will perform identity authentication for every access request. Therefore, you must contain the signature information in the request no matter whether you submit a request by the HTTP or HTTPS protocol. By using `Access Key ID` and `Access Key Secret`, the CDN performs symmetric encryption to authenticate the request sender. `Access Key ID` and `Access Key Secret` are officially issued to visitors by Alibaba Cloud \(visitors can apply for and manage them on the official Alibaba Cloud website\).

**Note:** `Access Key ID`*indicates the identity of the visitor.*`Access Key Secret` is the secret key used to encrypt the signature string and to verify the signature string on the server. It must be kept strictly confidential and should only be known to Alibaba Cloud and the user.

When a user calls a server, the following method is used to sign the request:

1.  The Canonicalized Query String is constructed using the request parameters
    1.  The request parameters are ordered alphabetically by the parameter names \(this includes the “common request parameters” and user-defined parameters for the given request interfaces described in this document, but not the Signature parameter mentioned in “Common Request Parameters”\).

        **Note:** When a request is submitted using the `GET` method, these parameters are the parameter section of the request URI \(i.e. the section in the URI following the “?” and connected by “&”\).

    2.  The name and value of each request parameter are encoded. The names and values must undergo URL encoding using the `UTF-8 character set`. The URL encoding rules are as follows:
        -   The characters A-Z, a-z, 0-9, and “-“, “\_”, “.”, “~” are not encoded.
        -   Other characters are encoded in “%XY” format, with XY representing the characters’ ASCII code in hexadecimal notation. For example, the English double quotes \(“\) are encoded as %22.
        -   Extended UTF-8 characters are encoded in “%XY%ZA…” format.
        -   It must be noted that the English space \( \) is encoded as %20, rather than the plus sign \(+\).

            **Note:** Generally, libraries that support URL encoding \(e.g. Java’s java.net.URLEncoder\) are all encoded according to the rules for the “application/x-www-form-urlencoded” MIME type. If this encoding method is used, replace the plus signs \(+\) in the encoded strings with %20, the asterisks \(\*\) with %2A, and change %7E back to the tilde \(~\) to conform to the encoding rules described above.

    3.  Connect the encoded parameter names and values with the English equals sign \(=\).
    4.  Then, order the parameter name and value pairs connected by equals signs in alphabetical order and connect them with the & symbol to produce the Canonicalized Query String.
2.  Follow the rules below to construct the string used for signature calculation by using the Canonicalized Query String constructed in the previous step:

    ```
    StringToSign=
    HTTPMethod + “&” +
    percentEncode(“/”) + ”&” +
    percentEncode(CanonicalizedQueryString)
    ```

    Here, HTTPMethod is the HTTP method used for request submission, e.g. `GET`.

    The percentEncode\(”/”\) is the encoded value \(”%2F”\) of the character “/”, which is obtained according to the URL encoding rules described in 1.b.

    percentEncode\(CanonicalizedQueryString\) is the encoded string of the Canonicalized Query String constructed in Step 1, produced by following the URL encoding rules described in 1.b.

3.  According to RFC2104 definitions, use the above signature sting to calculate the signature’s HMAC value.

    **Note:** When calculating the signature, the Key is the `Access Key Secret` held by the user with the “&” character \(ASCII:38\) added on the end. The SHA1 hashing algorithm is used.

4.  According to Base64 encoding rules, encode the above HMAC value into a string. This gives you the signature value.
5.  Add the obtained signature value to the request parameters as the Signature parameter. This completes the request signing process.

    **Note:** When the obtained signature value is submitted to the CDN server as the final request parameter value, it must undergo URL encoding like other parameters according to RFC3986 rules.

    Using DescribeCdnService as an example, the request URL prior to signing is as follows:

    ```
    http://cdn.aliyuncs.com/?SignatureVersion=1.0&Format=JSON&Timestamp=2015-08-06T02:19:46Z&AccessKeyId=testid&SignatureMethod=HMAC-SHA1&Version=2014-11-11&Action=DescribeCdnService&SignatureNonce=9b7a44b0-3be1-11e5-8c73-08002700c460
    ```

    Thus, the StringToSign is:

    ```
    GET&%2F&AccessKeyId%3Dtestid&Action%3DDescribeCdnService&Format%3DJSON&SignatureMethod%3DHMAC-SHA1&SignatureNonce%3D9b7a44b0-3be1-11e5-8c73-08002700c460&SignatureVersion%3D1.0&Timestamp%3D2015-08-06T02%253A19%253A46Z&Version%3D2014-11-11
    ```

    If we assume the `Access Key Id` is“testid”, `Access Key Secret` is “testsecret”, and theKey used for HMAC calculation is “testsecret&”, the calculated signature value is:

    ```
    KkkQOf0ymKf4yVZLggy6kYiwgFs=
    ```

    The signed request URL is \(note the added Signature parameter\):

    ```
    http://cdn.aliyuncs.com/?SignatureVersion=1.0&Format=JSON&Timestamp=2015-08-06T02%3A19%3A46Z&AccessKeyId=testid&SignatureMethod=HMAC-SHA1&Version=2014-11-11&Signature=KkkQOf0ymKf4yVZLggy6kYiwgFs%3D&Action=DescribeCdnService&SignatureNonce=9b7a44b0-3be1-11e5-8c73-08002700c460
    ```


## Sample code

Attachment: Signature Mechanism\_python\_sdk: [Click download](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/27149/cn_zh/1535445996600/callmethod_sdk_python.zip)

Signature Mechanism\_java\_sdk: [Click download](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/27149/cn_zh/1504765657536/SignatureUtils%281%29.java)

