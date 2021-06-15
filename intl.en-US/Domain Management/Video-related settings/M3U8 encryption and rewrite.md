# M3U8 encryption and rewrite

This topic describes how to configure M3U8 encryption and rewrite.

## Overview

To accelerate the delivery of HTTP Live Streaming \(HLS\) content, Alibaba Cloud Content Delivery Network \(CDN\) rewrites the `#EXT-X-KEY` tag in an M3U8 file that is transmitted over HLS. After the `#EXT-X-KEY` tag is rewritten, the specified parameter name and value are added to the end of the URI attribute in the tag to decrypt the M3U8 file. The value of the parameter is provided by the client request.

The **M3U8 encryption and rewrite** feature allows you to enable M3U8 encryption and rewrite M3U8 files that are transmitted over HLS. You can specify a parameter name to rewrite an M3U8 file. The custom parameter name must be the same as that included in the client requests. If you do not specify a parameter name, the default parameter name `MtsHlsUriToken` is used.

## Procedure

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Video**.

5.  In the **M3U8 Encryption and Rewrite** section, turn on **M3U8 Encryption and Rewrite**.

    ![Turn on M3U8 Encryption and Rewrite](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4664788951/p146811.png)

    **Note:** After you turn on **M3U8 Encryption and Rewrite**, the parameter name `MtsHlsUriToken` is used by default.

6.  If you want to use a custom parameter name that is the same as that included in the client requests, perform the following steps:

    1.  Click **Modify** next to the **Custom Parameter Name** field.

    2.  In the **Custom Parameter Name** dialog box, set the **Parameter Name** parameter.

        ![Set the parameter name](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4664788951/p146856.png)

        **Note:** The parameter names are case-sensitive. Make sure that the specified parameter name is the same as that included in the client requests. For example, if the client requests include the `foobar` parameter name, the custom parameter name `FooBar` cannot take effect.

    3.  Click **OK**.


## Examples

Log on to the Alibaba Cloud CDN console, turn on **M3U8 Encryption and Rewrite**, and then set the custom parameter name to `foobar`. The following figure shows this custom parameter name.

![Example 1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4664788951/p146885.png)

A client request includes the `foobar` parameter. The parameter value is `yyyy`. To decrypt the M3U8 file and accelerate the delivery of the content over HLS, Alibaba Cloud CDN adds `foobar=yyyy` to the end of the URI attribute in the `#EXT-X-KEY` tag.

![Example 2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4664788951/p146892.png)

**Related topics**  


[BatchSetCdnDomainConfig](/intl.en-US/New API Reference/Domain name management/BatchSetCdnDomainConfig.md)

