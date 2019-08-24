# DescribeUserCustomLogConfig {#reference_lyx_thf_vdb .reference}

Queries all custom log configurations of a user.

## Request parameters {#section_anm_whf_vdb .section}

|Parameters|Type|Required|Instance Value|Description|
|Action|String|Yes|DescribeUserCustomLogConfig|The name of this interface. Value: DescribeUserCustomLogConfig|
|Version|String|No|2014-11-11|API version.|

## Response parameters {#section_qh4_ckf_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|94E3559F-7B6A-4A5E-AFFD-44E2A208A249|The ID of the request.|
|ConfigIds|String|\[ “c3bb2c78-2915-4d5a-b6a1-557789255555”, “25473b84-d598-498e-b148-f23d0a255555”, “1f1e6c6e-6701-4193-ae4d-54bf3e555555” \]|Log configuration ID.|

## Example {#section_x5y_fkf_vdb .section}

**Request example**

``` {#codeblock_yme_d9i_nen}
https://cdn.aliyuncs.com?Action=DescribeUserCustomLogConfig&public request parameter
```

 **Normal return example** 

-   JSON format

    ``` {#codeblock_w6p_mgv_c6t}
        "ConfigIds":{
            "ConfigId":[
                "c3bb2c78-2915-4d5a-b6a1-557789255555",
                "25473b84-d598-498e-b148-f23d0a255555",
                "1f1e6c6e-6701-4193-ae4d-54bf3e555555"
    
    
        "RequestId":"95D5B69F-8AEC-419B-8F3A-612B35032B0D"
    					
    ```


 **Exception return example** 

-   JSON format

    ``` {#codeblock_9it_fat_s2n}
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"                
    ```


