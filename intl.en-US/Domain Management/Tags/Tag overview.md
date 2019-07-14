# Tag overview {#concept_d4k_zb3_4gb .concept}

This topic provides an overview of domain name tags. Each tag is represented by a string of characters. In Alibaba Cloud CDN, you cannot define tags, but you can attach tags to domain names, detach tags from domain names, and use tags to group or filter domain names.

## Limits {#section_qcm_kc3_4gb .section}

-   Each tag is a key-value pair \(`Key:Value`\), which consists of a key and a value.
-   Up to 20 tags can be attached to a domain name.
-   For the same domain name, the key for each tag must be unique. If two tags have the same key but different values, the current tag overwrites the previous tag. For example, if you configure the `Key1:Value1` tag and then the `Key1:Value2` tag for the `test.example.com` domain name, only the `Key1:Value2` tag is attached to the domain name.
-   A key cannot start with *aliyun* or *acs*, contain `http://` or `https://`, or be left unspecified.
-   A value cannot contain `http://` or `https://`, but can be left unspecified.
-   A key can contain up to 64 Unicode characters.
-   A value can contain up to 128 Unicode characters.
-   Tags are case-sensitive.

## Functions {#section_1g2_cdc_iyi .section}

You can use tags to perform the following operations:

-   Attach tags to domain names to identify or group the domain names. For more information, see [Attach tags](reseller.en-US/Domain Management/Tags/Attach tags to a domain name.md#).
-   Detach tags from domain names. For more information, see [Detach tags](reseller.en-US/Domain Management/Tags/Detach tags from a domain name.md#).
-   Manage domain names based on their tags. For more information, see [Manage domain names by tag](reseller.en-US/Domain Management/Tags/Manage domain names by tag.md#).
-   Query the domain names to which specific tags are attached. For more information, see [Filter domain names by tag](reseller.en-US/Domain Management/Tags/Query domain names by tag.md#).

