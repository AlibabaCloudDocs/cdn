# DescribeL2VipsByDomain

Query the virtual IP address list of an L2 node by the domain name. This interface takes effect after a whitelist is configured.

**Note:**

-   Users with daily peak bandwidth greater than 1 Gbps can open a ticket to apply for the interface call permission. Click [Apply now](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).
-   For more information about scenarios, see What back-to-origin addresses does the Alibaba Cloud CDN support?

## Request parameters

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|DescribeL2VipsByDomain|The name of this interface. Value: DescribeL2VipsByDomain|
|DomainName|String|Yes.|www.yourdomain.com|Domain name.

Value range: Only one domain name is supported and it must be added to the whitelist. |

## Return parameters

|Parameters|Type|Example values|Description|
|DomainName|String|xxxx.com|Domain name.|
|Vips|String|“Vip”: \[ “1.1.1.1/25”, “2.2.2.2/25” \]|Vip list.|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request.|

## Examples

**Request example**

```
https://cdn.aliyuncs.com?Action=DescribeL2VipsByDomain&DomainName=xxxx.com&Public request parameters
```

**Normal return example**

-   JSON format

    ```
    
        "DomainName":"xxxx.com",
        "RequestId":"820E7900-5CA9-4AEF-B0DD-20ED5F64BE55",
        "Vips":{
            "Vip":[
                "1.1.1.1/25",
                "2.2.2.2/25"
            
        }
                        
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
                        
    ```


