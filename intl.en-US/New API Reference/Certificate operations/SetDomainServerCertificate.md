# SetDomainServerCertificate

You can call the SetDomainServerCertificate operation to configure an SSL certificate for a CDN domain.

## Debugging

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/#/?product=Cdn&api=SetDomainServerCertificate) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Action|String|Yes|The operation that you want to perform. Set this parameter to SetDomainServerCertificate.|
|DomainName|String|Yes|The name of the CDN domain for which the certificate is enabled. The specified CDN domain must be of the HTTPS acceleration type.|
|ServerCertificateStatus|String|Yes|Specifies whether to enable the SSL certificate. Valid values: -   on: enables the SSL certificate.
-   off: disables the SSL certificate.

 Default value: off. |
|ServerCertificate|String|No|The content of the certificate. Specify the content of the certificate only if you enable the SSL certificate.|
|PrivateKey|String|No|The private key. Specify the private key only if you enable the SSL certificate.|
|CertType|String|No|-   upload: specifies a local certificate.
-   cas: specifies a certificate issued by SSL Certificates Service.
-   free: specifies a free certificate. |
|CertName|String|No|The name of the certificate.|
|ForceSet|String|No|If you set the value to 1, the system does not check the certificate name for duplicates and overwrites the information of the existing certificate with the same name.|

## Response parameters

|Parameter|Type|Description|
|:--------|:---|:----------|
|RequestID|String|The ID of the request.|

## Examples

Sample request

```
http://cdn.aliyuncs.com?Action=SetDomainServerCertificate&DomainName=test.com&CertName=myCert1&ServerCertificateStatus=on&ServerCertificate=xxx&PrivateKey=yyy&<Common request parameters>
```

Sample success response

`JSON` format

```
{
  "RequestId": "0AEDAF20-4DDF-4165-8750-47FF9C1929C9"
}
```

## Error codes

|Error code|Error message|HTTP status code|Description|
|:---------|:------------|:---------------|:----------|
|InvalidDomain.NotFound|The domain provided does not belong to you.|404|The error message returned because the specified domain does not exist or does not belong to you.|
|IllegalOperation|Illegal domain operate is not permitted.|403|The error message returned because you are not authorized to perform this operation.|
|ServiceBusy|The specified Domain is configuring, please retry later.|403|The error message returned because the specified domain is being configured. Try again later.|
|InvalidDomain.Offline|The domain provided is offline.|400|The error message returned because the specified domain is disabled.|
|OperationDenied|Your CDN service is suspended.|403|The error message returned because CDN has been suspended for your account due to overdue payments. Add funds to your account.|
|InvalidServerCertificateStatus.ValueNotSupported|The specified value of parameter Enable is not supported.|400|The error message returned because the specified ServerCertificateStatus parameter is invalid.|
|ServerCertificate.MissingParameter|An input parameter ServerCertificate that is mandatory for processing the request is not supplied.|400|The error message returned because the ServerCertificate parameter is not specified.|
|PrivateKey.MissingParameter|An input parameter PrivateKey that is mandatory for processing the request is not supplied.|400|The error message returned because the PrivateKey parameter is not specified.|
|InvalidCertificate|The Certificate you provided is malformed!|400|The error message returned because the specified certificate content is invalid.|
|InvalidPrivateKey|The Private Key you provided is malformed!|400|The error message returned because the specified private key is invalid.|
|Certificate.MissMatch|The Private Key does not math the specified Certificate!|400|The error message returned because the specified certificate content and private key do not match.|
|InvalidCertificate.TooLong|The Certificate you provided is over the max length!|400|The error message returned because the length of the certificate content exceeds the upper limit.|
|InvalidCertName.TooLong|The Certificate name you provided is over the max length 128!|400|The error message returned because the specified certificate name cannot contain more than 128 characters.|
|SetDomainServerCertificate.ParameterError|Parameters have error.|400|The error message returned because the specified parameters are invalid.|
|Certificate.StatusError|Certificate is not exist or its status is error.|400|The error message returned because the specified certificate does not exist or the certificate status is invalid.|
|DeleteFailed|Delete certificate is failed.|400|The error message returned because the system has failed to delete the specified certificate.|
|Certificate.NotFind|Not find the certificate info.|400|The error message returned because the specified certificate was not found.|
|Certificate.Duplicated|The certificate name is duplicated.|400|The error message returned because the specified certificate name already exists.|
|Certificate.FormatError|The certificate format is error.|400|The error message returned because the certificate format is invalid.|
|Certificate.StatusError|The certificate status is error.|400|The error message returned because the certificate status is invalid.|
|Certificate.KeyNull|The private key is not null.|400|The error message returned because the private key is not specified.|
|Key.Malformed|The private key format is error.|400|The error message returned because the format of the specified private key is invalid.|
|Certificate.NotPermittedOff|Turn off certificate will change domain scheduling, please contact customer service.|400|The error message returned because disabling the certificate may affect the scheduling of the specified domain. Contact Customer Service.|
|Certificate.SettedNotEffect|Certificate was successfully setted but does't take effect for protecting current service, please contact customer service.|400|The error message returned because the specified certificate is configured but temporarily disabled from protecting your service. To enable the certificate, contact Customer Service.|

This table lists the error codes that the operation can return. For more information, see [Error codes](https://error-center.aliyun.com/status/product/Cdn).

