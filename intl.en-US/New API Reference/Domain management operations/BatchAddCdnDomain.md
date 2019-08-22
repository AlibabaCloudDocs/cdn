# BatchAddCdnDomain {#reference_1095928 .reference}

You can call the BatchAddCdnDomain operation to add one or more CDN domains. You can add a maximum of 20 CDN domains per request under the same account.

When you call the BatchAddCdnDomain operation, make sure that the following requirements are met:

-   Before you add a CDN domain, the CDN service must be activated. For more information, see [Activate CDN](../../../../intl.en-US/Quick Start/Activate CDN.md#).
-   Your CDN domain must have an ICP license.
-   If your origin site is not hosted on the Alibaba Cloud platform, your origin site content must be reviewed and approved by Alibaba Cloud. The review will take a maximum of one working day to complete.

## Debugging {#section_bxb_qz6_941 .section}

Alibaba Cloud provides [OpenAPI Explorer](https://api.aliyun.com/new#/?product=Cdn&api=BatchAddCdnDomain) to simplify API usage. You can use OpenAPI Explorer to search for APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#section_2ee_pea_5ra .section}

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Action|String |Yes|The operation that you want to perform. Set this parameter to BatchAddCdnDomain.|
|DomainName|String|Yes|The names of the domains for which CDN is enabled. Separate multiple domain names with commas \(,\).|
|CdnType|String|Yes|The business type of the CDN domain. Valid values: -   web: the acceleration of image and small file distribution.
-   download: the acceleration of large file downloads.
-   video: the acceleration of on-demand video and audio content.

 |
|Sources|String|Yes|The list of origin addresses.|
|CheckUrl|String|No|The URL that is used to test the accessibility of the origin.|
|Scope|String|No|The scope. Valid values: -   domestic
-   overseas
-   global

 |
|ResourceGroupId|String|No|The ID of the resource group. If you do not specify this parameter, the system automatically uses the ID of the default resource group.|
|TopLevelDomain|String|No|The primary domain name.|

Sources syntax

``` {#codeblock_424_9ii_bb8}
[{"content":"1.1.1.1","type":"ipaddr","priority":"20","port":80,"weight":"15"}]
```

Parameters in Sources

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|type|String|Yes|The origin type. Valid values: -   ipaddr: IP address
-   domain: domain name
-   oss: Internet domain name of an Alibaba Cloud OSS bucket
-   fc\_domain: Function Compute domain name

 |
|content|String|Yes|The address of the origin, which can be an IP address or a domain name.|
|port|Integer|No|The port number. You can specify port 443 or port 80. You can also customize the port number. Default value: 80. If you set this parameter to 443, CDN communicates with the origin by using HTTPS.|
|priority|String|No|The priority of the origin when multiple origins exist. Default value: 20.|
|weight|String|No|The weight of the origin when multiple origins exist. Default value: 10.|

## Response parameters {#section_szl_9bz_to8 .section}

|Parameter|Type|Description|
|:--------|:---|:----------|
|RequestID|String|The ID of the request.|

## Examples {#section_sax_dww_8mr .section}

Sample request

``` {#codeblock_eqm_gi5_lvu}
http://cdn.aliyuncs.com?Action=BatchAddCdnDomain&CdnType=web&DomainName=example.com&Sources=[{"content":"1.1.1.1","type":"ipaddr","priority":"20","port":80}]&<Common request parameters>
```

Sample success response

`JSON` format

``` {#codeblock_yoa_1so_l47}
{
  "RequestId": "15C66C7B-671A-4297-9187-2C4477247A74"
}
```

## Error codes {#section_npn_9i6_km8 .section}

|Error code|Error message|HTTP status code|Description|
|:---------|:------------|:---------------|:----------|
|InvalidDomainName.Malformed|Specified DomainName is malformed.|400|The error message returned because the specified DomainName parameter is invalid.|
|InvalidCdnType.Malformed|Specified CdnType is malformed.|400|The error message returned because the specified CdnType parameter is invalid.|
|InvalidSourceType.Malformed|Specified SourceType is malformed.|400|The error message returned because the specified SourceType parameter is invalid.|
|InvalidSources.Malformed|Specified Sources is malformed.|400|The error message returned because the specified origin address does not match the origin type.|
|InvalidScope.Malformed|Specified Scope is malformed.|400|The error message returned because the specified Scope parameter is invalid.|
|InvaildParameter|The Certificate you provided is malformed!|400|The error message returned because the specified certificate is invalid.|
|BusinessExist|Business exist do not repeated submission|400|The error message returned because the specified domain is being added. Do not repeat this operation.|
|DomainAlreadyExist|This domain name is exist already|400|The error message returned because the specified domain is already added.|
|DomainOverLimit|The Number of Domain is over the limit|403|The error message returned because the maximum number of the domains that can be added per request has been exceeded.|
|DomainNotRegistration|The Domain name is not registered|404|The error message returned because the specified domain does not have an ICP license.|
|IllegalOperation|Illegal domain operate is not permitted.|403|The error message returned because you are not authorized to perform this operation.|
|ServiceBusy|The specified Domain is configuring, please retry later.|403|The error message returned because the specified domain is being configured. Try again later.|
|InvalidDomain.NotFound|The domain provided does not belong to you.|404|The error message returned because the specified domain does not exist or does not belong to you.|
|InnerAddDomainDenied|Your account haven't bind aoneId, can not add domain.|400|The error message returned because you cannot add a domain by using an internal account that is not bound to an AoneId.|
|ExtensiveAndAllBothExist|Extensive domain and the domain begins with 'all.' can not exist at the same time.|400|The error message returned because you cannot specify both wildcard domain names and domain names that start with `all.` in the same request.|
|CdnTypeNotSupportExtensiveDomain|Extensive domain not supported for this cdn type.|400|The error message returned because wildcard domain names are not supported for the specified business type.|
|ExtensiveAndSpecificDomainConflict|Extensive domain and corresponding specific domain are mutually exclusive.|400|The error message returned because the specified wildcard domain name matches an exact domain name. Wildcard domain names are mutually exclusive with any matching exact domain names.|
|InvalidParameter|Add live region parameters have error.|400|The error message returned because the system has failed to specify the region parameter for the ApsaraVideo Live service.|
|InvalidRegion.Malformed|Specified Region is malformed.|400|The error message returned because the specified region parameter is invalid.|
|Abs.resourceGroupId.Malformed|Specified ResourceGroupId is malformed.|400|The error message returned because the specified resource group ID is invalid.|
|InvalidTopLevelDomain.Malformed|Specified TopLevelDomain is malformed.|400|The error message returned because the specified TopLevelDomain parameter is invalid.|
|TopLevelDomain.NotFound|TopLevelDomain is not exist.|400|The error message returned because the specified TopLevelDomain parameter does not exist.|
|InvalidResourceGroupId.Malformed|Specified ResourceGroupId is malformed.|400|The error message returned because the specified ResourceGroupId parameter is invalid.|
|EntityNotExists.ResourceGroup|The resource group does not exist.|400|The error message returned because the specified resource group ID does not exist.|
|InvalidStatus.ResourceGroup|It’s now allowed to do this operation because of the current status of resource-group.|400|The error message returned because the specified resource group is in an invalid status.|
|InvalidPriorities.Malformed|The length of priorities is not the same with source.|400|The error message returned because the number of priority settings does not match the number of origins.|
|NotInternationRealIdentity|You need to do real name authentication when you use Chinese mainland resources.|400|The error message returned because you have not completed the real-name authentication that is required to use resources in Mainland China.|
|DomainReserved|The root domain of your domain is reserved by another account. Submit a ticket to contact customer support.|400|The error message returned because the root domain of the specified domain is used by another account. If you still want to add the domain, submit a ticket.|

