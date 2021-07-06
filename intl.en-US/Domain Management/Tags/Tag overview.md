---
keyword: [tag management, add tags, remove tags]
---

# Tag overview

This topic provides an overview of domain name tags. Tags do not carry special definitions. Each tag is a key-value pair that is used to mark or filter domain names. Alibaba Cloud Content Delivery Network \(CDN\) allows you to add tags to domain names, remove tags from domain names, and use tags to group or filter domain names.

## Limits

Before you manage tags, take note of the following limits on the tags:

-   Each tag is a `key-value` pair.
-   You can add at most 20 tags to a domain name.
-   Among the tags that are added to the same domain name, the key of each tag must be unique. If two tags have the same key but different values, the later one overwrites the earlier one. For example, if you create the `Key1:Value1` tag and then the `Key1:Value2` tag for the `test.example.com` domain name, only the `Key1:Value2` tag is added to the domain name.``
-   A key cannot start with `aliyun` or `acs:`, contain `http://` or `https://`, or be left unspecified.
-   A value cannot contain `http://` or `https://`, but can be left unspecified.
-   A key must be 1 to 64 Unicode characters in length.
-   A value must be 0 to 128 Unicode characters in length.
-   Tags are case-sensitive.

## Related features

You can use tags to manage domain names. The following table lists the features supported by tags.

|Feature|Description|
|-------|-----------|
|[Add tags to domain names](/intl.en-US/Domain Management/Tags/Add tags to domain names.md)|Add tags to one or more domain names to identify or group the domain names.|
|[Remove a tag](/intl.en-US/Domain Management/Tags/Remove a tag.md)|Remove tags from one or more domain names.|
|[Use tags to manage domain names](/intl.en-US/Domain Management/Tags/Use tags to manage domain names.md)|Group domain names based on tags.|
|[Query data of domain names by tag](/intl.en-US/Domain Management/Tags/Query data of domain names by tag.md)|Query domain names based on tags.|
|[Tag use case](/intl.en-US/Domain Management/Tags/Tag use case.md)|Provide cases on how to manage domain names by using tags.|

