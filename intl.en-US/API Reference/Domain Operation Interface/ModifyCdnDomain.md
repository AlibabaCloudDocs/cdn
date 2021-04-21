# ModifyCdnDomain

Modify CDN domains. Currently, source site can be modified.

Restrictions:

-   Before creating CDN domain name, CDN service must be activated.
-   CDN domain name must complete the registration process.

## Request parameters

|Name|Type|Required|Example|Description|
|:---|:---|:-------|:------|:----------|
|Action|String|Yes|ModifyCdnDomain|The name of this interface. Value:

ModifyCdnDomain |
|DomainName|String|Yes|www.yourdomain.com|The domain name that have access to CDN. |
|Priorities|String|No|20|Priorities, which correspond to source sites.

Multiple source sites are separated by comma.

Default value: 20. |
|ResourceGroupId|String|No|rg-acfmyuji4b6r4\*\*|The resource group ID. |
|SourcePort|Integer|No|80|The source site port. |
|SourceType|String|No|domain|The source site type. Value:

-   ipaddr: IP source site.
-   domain: domain name source site.
-   oss: OSS Bucket is the source site \( inner common: public source\).

**Note:** If you select the business type of live streaming media acceleration, the source site and information are not required. |
|Sources|String|No|Yourdomain.com|Source address, which can be IP or domain name.

-   IP or domain name supports up to 20 addresses, which are separated by comma.
-   IP and domain name cannot be both entered.
-   If the business type is live streaming media acceleration, the source address is not required to enter. If the business type is other type, source address is required \(inner user, the type is common source, and type enum value can be entered\). |
|TopLevelDomain|String|No|your.top.domain.com|Top-level domain, only users in the whitelist CDN\_TOP\_LEVEL\_DOMAIN\_GREY\_USER\_LIST can configure effectively. |

## Return parameters

|Parameters|Type|Example values|Description|
|:---------|:---|:-------------|:----------|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|Request ID|

## Examples

**Request example**

```
http://cdn.aliyuncs.com?Action=ModifyCdnDomain&SourceType=domain&DomainName=test.com&Sources=test.com&Public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "Requestid": "maid"
                        
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
                        
    ```


