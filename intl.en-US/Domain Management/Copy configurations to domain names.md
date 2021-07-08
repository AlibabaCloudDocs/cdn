# Copy configurations to domain names

Alibaba Cloud Content Delivery Network \(CDN\) allows you to copy configurations from a domain name to one or more domain names. This topic describes how to copy configurations to one or more domain names.

## Scenarios

Alibaba Cloud CDN allows you to copy configurations from a domain name to one or more domain names. You can select a source domain name based on business requirements and copy its configurations to one or more domain names. This simplifies the process of configuring accelerated domain names.

## Usage notes

When you copy configurations from a domain name to other domain names, take note of the following rules:

-   After you copy the configurations of a domain name to another domain name, the copied configurations cannot be rolled back. Make sure that the configurations that you want to copy are correct.
-   For domain names that generate a large amount of network traffic or high bandwidth values, proceed with caution to avoid financial loss.
-   Special configurations that are applied through tickets cannot be copied.

## Procedure

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Copy Configurations**.

    ![Domain Names](../images/p64602.png)

4.  Select the configurations that you want to copy and click **Next**.

    **Note:**

    -   You cannot copy the origin information and basic information \(CNAME, business type, and accelerated region\) at the same time.
    -   You cannot copy SSL certificates from a domain name to another domain name.
    -   When you copy custom request headers configured for requests that are redirected to origin servers to another domain name, the headers are added to the domain name, instead of overwriting the existing headers. For example, if Domain Name A has two request headers and you copy five request headers from Domain B to Domain Name A, Domain Name A has seven request headers.
    -   When you copy HTTP headers to another domain name, the HTTP headers overwrite the existing HTTP headers. For example, if the cache\_control HTTP header is set to private for Domain Name A and to public for Domain Name B and you copy cache\_control from Domain Name B to Domain Name A, cache\_control HTTP of Domain Name A is set to public.
    -   When you copy configurations of feature switches to another domain name, the copied configurations overwrite the existing configurations.
    -   When you copy the referer field, the blacklist, or the whitelist to another domain name, the copied configurations overwrite the existing configurations.
    ![Copy configurations](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6746219951/p8715.png)

5.  Select the domain names to which you want to apply the copied configurations and click **Next**.

    You can enter a keyword to search for domain names.

    ![Select configurations](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6746219951/p8716.png)

6.  In the **Copy Configurations** message, click **OK**.

    ![Select domain names](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6746219951/p8717.png)


