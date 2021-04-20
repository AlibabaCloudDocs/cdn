# Appendix

## Error code

**Client error**

|Error code|Error message|HTTP status code|
|:---------|:------------|:---------------|
|OperationDenied|Your account does not open CDN service yet.|403|
|InsufficientBalance|Your account does not have enough balance.|400|
|Forbidden.NotVerified|Your account is not verified yet.|403|
|UnsupportedOperation|The specified action is not supported.|400|
|NoSuchVersion|The specified version does not exist.|400|
|UnsupportedParameter|The parameter <parameter name\> is not supported|400|
|MissingParameter|The input parameter <parameter name\> that is required for processing this request is not supplied.|400|
|InvalidParameter|The specified parameter <Parameter Name\> is not valid. Or specified image does not support the specified instance type.|400|
|Throttling|Request was denied due to request throttling.|400|
|InvalidAccessKeyId.NotFound|The Access Key ID provided does not exist in our records.|404|
|Forbidden|User not authorized to operate on the specified resource.|403|
|Forbidden.RiskControl|This operation is forbidden by AlibabaCloud Risk Control system.|403|
|Forbidden.AccessTooManyOthersResource|This operator is forbidden because too many other one's resource to be accessed.|403|
|SignatureDoesNotMatch|The signature we calculated does not match the one you provided. Please refer to the API reference about authentication for details.|403|
|SignatureNonceUsed|The request signature nonce has been used.|400|
|IdempotentParameterMismatch|Request uses a client token in a previous request but is not Identical to that request.|400|
|ChargeTypeViolation|Operations on this kind of resources are not permitted.|403|
|InsufficientBalance|Your account does not have enough balance.|400|
|QuotaExceeded|Living instances quota exceeded.|400|
|OperationDenied|Specified operation is denied as your resource is locked for security reasons.|403|
|RiskControl.Refused|Your action was.refused by RiskControl.|400|
|QuotaExceeded.Snapshot|Snapshot quota exceeded.|400|
|QuotaExceeded.Image|Image quota exceeded.|400|

**Server error**

|Error code|Error message|HTTP status code|
|:---------|:------------|:---------------|
|InternalError|The request processing has failed due to some unknown error, Exception or failure.|500|
|ServiceUnAvailable|The request has failed due to a temporary failure of the server.|503|

## How to call an API

The CDN service interface is called by sending an HTTP request to the CDN server \(you can send it through HTTP or HTTPS channels\) and receiving the CDN server's response to this request. After the CDN server receives a user request, it must perform authentication and parameter verification on the request. After all verifications are successful, it submits or completes the associated operation based on the parameters specified for the request. Then, it returns the processing results to the caller in the form of HTTP response.

**Request structure**

Requests are composed of the following parts:

-   HTTP method: all CDN service interfaces only support GET method calls.
-   Request URL: the request’s service address, name of the operation to be executed, operation parameters, and public request parameters are included in the request URL.
-   Server address: the CDN service domain names are http://cdn.aliyuncs.com/ and https://cdn.aliyuncs.com/. In order to ensure the security of the request, we strongly recommend that you use an HTTPS channel. \(HTTPS has an added SSL layer for encrypted communications and can prevent communication interception leading to the leakage of sensitive information.\)
-   Operation name: each interface requires that the name of the operation to be executed be specified, i.e. the Action parameter.
-   Operation parameter: different operation parameters must be set for different operations to be executed. For details, see the instructions for each interface.
-   Public Request Parameters: parameters such as TimeStamp and Signature must be included in each request.

For the server to correctly verify the user’s authentication and authorize request execution, the request must be signed before submission for processing. For signature rules, refer to the signature mechanism section.

After the server finishes processing the request, it will return the response results. Response results are divided into successful results and error messages. For an illustration of the format, refer to the following example for JSON result returned:

```
{
    "RequestId": "4C467B38-3910-447D-87BC-AC049166F216",
    /* Return result data */
}
```

**Invocation example**

Take the chain interface as an example:

The corresponding Action is DescribeCdnService. After adding all the common request parameters \(except Signature\), the request URL will be \(for ease of reading, this is the URL before URL encoding\):

```
Http://cdn.aliyuncs.com /? Timestamp = MAID: 33: 56z & format = xml & accesskeyid = testid & Action = fig & Zadar uremethod = glas& signaturenonce = fig & version = 2013-01-10 & taberureversion = 1.0
```

According to the signing calculation rule, a normalized query string is constructed first, as follows:

```
Http://cdn.aliyuncs.com /? Timestamp = MAID: 33: 56z & format = xml & accesskeyid = testid & Action = fig & Zadar uremethod = glas& signaturenonce = fig & version = 2013-01-10 & taberureversion = 1.0
```

Then, StringToSign is constructed as a signature string with a value:

```
GET&%2F&AccessKeyId%3Dtestid%26Action% DescribeCdnService %26Format%3DXML%26SignatureMethod%3DHMAC-SHA1%26SignatureNonce%3DNwDAxvLU6tFE0DVb%26SignatureVersion%3D1.0%26TimeStamp%3D2012-12-26T10%253A33%253A56Z%26Version%3D2013-01-10
```

The following Java sample code demonstrates how to add public request parameters, how to construct the Canonicalized Query String from the request parameters, and how to construct the StringToSign. This example assumes that all request parameters are placed in a Map <String, String\> object and the Access Key ID is "testid".

```
final String HTTP_METHOD = "GET";
……………………………………
```

Here, you must note that the TimeStamp parameter must comply with [ISO8601](http://zh.wikipedia.org/wiki/ISO_8601). Use UTC time, or it will produce an error. The following sample code demonstrates how to generate a compliant TimeStamp string:

```
private static final String ISO8601_DATE_FORMAT = "yyyy-MM-dd'T'HH:mm:ss'Z'";

    private static String formatIso8601Date(Date date) {
        SimpleDateFormat df = new SimpleDateFormat(ISO8601_DATE_FORMAT);
        df.setTimeZone(new SimpleTimeZone(0, "GMT"));
        return df.format(date);
    }
```

When generating a Canonicalized Query String \(the canonicalizedQueryString variable in the example\) and StringToSign, both must be encoded. The encoding rules are described in detail in the signature mechanism section. The following sample code demonstrates how to use the java.net.URLEncoder class for encoding:

```
private static final String ENCODING = "UTF-8";

        private static String percentEncode(String value)
            throws UnsupportedEncodingException{
        return value ! = null ?
                URLEncoder.encode(value, ENCODING).replace("+", "%20")
                .replace("*", "%2A").replace("%7E", "~")
                : null;
    }
```

Assume the `Access Key Id` in use is "testid",`Access Key Secret` is "testsecret", and the Key used for HMAC calculation is "testsecret&", the calculated signature value is:

```
SDFQNvyH5rtkc9T5Fwo8DOjw5hc=
```

Sample code for signature calculation \(Java\):

```


// The following is a sample code for signature calculation
final String ALGORITHM = "HmacSHA1";
final String ENCODING = "UTF-8";
key = "testsecret&";


Mac mac = Mac.getInstance(ALGORITHM);
mac.init(new SecretKeySpec(
key.getBytes(ENCODING), ALGORITHM));
byte[] signData = mac.doFinal(
stringToSign.getBytes(ENCODING));


String signature =
new String(Base64.encodeBase64(signData));
```

After adding the Signature parameter, please perform URL encoding according to the RFC3986 rules and obtain

```
http://cdn.aliyuncs.com/?TimeStamp=2012-12-26T10%3A33%3A56Z&Format=XML&AccessKeyId=testid&Action= DescribeCdnService &SignatureMethod=HMAC-SHA1&RegionId=region1&SignatureNonce=NwDAxvLU6tFE0DVb&Version=2012-09-13&SignatureVersion=1.0&Signature=SDFQNvyH5rtkc9T5Fwo8DOjw5hc%3d
```

Next, send an HTTP request to the above URL for a response to the request from the CDN server, as shown below:

`none`

By parsing this XML output, you can obtain an ID and LocalName list for all available regions. If, when submitting a request, the specified Format parameter is JSON, then the result will also be returned in the JSON format

## How to ensure idempotence

If a request timeout or internal server error is encountered when calling the CreateInstance interface to create an ECS in the CDN, the client may try to resend the request. At this time, the client can prevent the server from creating more instances than expected by providing the optional `ClientToken` parameter. Providing this `ClientToken` parameter will also ensure the idempotence of the request. `ClientToken` is a unique, case sensitive string generated by the client that cannot exceed 64 ASCII characters.

If a user uses the same `ClientToken` value to call the CreateInstance interface, the server will return identical request results, including the same InstanceId. Therefore, when the user encounters an error and tries again, by providing the same ClientToken value, he can ensure the CDN only creates one instance and that he obtains this InstanceId.

If the user provides a ClientToken that has already been used, but with different request parameters, the CDN will return the *IdempotentParameterMismatch* error code. However, you must note that the SignatureNonce, TimeStamp, and Signature parameters must be changed when trying to submit the request again. Because the CDN uses SignatureNonce to prevent replay attacks and TimeStamp to mark the time of each request, the duplicate request must provide different SignatureNonce and TimeStamp parameter values. This will also produce a different Signature value.

Generally, clients will only need to retry an operation if they encounter a 500 \(InternetError\) or 503 \(ServiceUnAvailable\) error or cannot receive a response. When 200 is returned, retrying the operation will give you the same results as the last time, but will not have any effect on the server status. When a 4xx error code is returned, unless the message explicitly says "try it later", retrying the operation will usually not be successful.

## API behavior for accounts in outstanding payment

In the following list, "-" indicates no relation and "Normal Logic" indicates that the interface is executed and result returned based on the interface's normal logic.

**Accounts in outstanding payment**

|Interface|Behavior|Description|
|:--------|:-------|:----------|
|OpenCdnService|Normal| |
|DescribeCdnService|Normal|OperationLocks will show a Financial lock.|
|ModifyCdnService|Exception|Displays InsufficientBalance error code|
|RefreshObjectCaches|Exception|Displays InsufficientBalance error code|
|DescribeRefreshTask|Normal| |
|DescribeCdnMonitorData|Normal| |

