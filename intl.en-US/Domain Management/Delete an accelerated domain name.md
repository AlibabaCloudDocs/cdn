# Delete an accelerated domain name

If you no longer need to use Alibaba Cloud Content Delivery Network \(CDN\) to accelerate access to a domain name, you can delete the accelerated domain name in the console. After the accelerated domain name is deleted, you are no longer charged for the domain name.

After you activate Alibaba Cloud CDN, you cannot disable it by deleting your Alibaba Cloud account. To stop using Alibaba Cloud CDN, delete the accelerated domain names.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the accelerated domain name that you want to delete, click the More icon in the Actions column, and then select **Delete**.

    **Note:** If you want to suspend Alibaba Cloud CDN for an accelerated domain, select Disable. After an accelerated domain name is disabled, requests are directly sent to the domain name instead of the CNAME. However, the DNS settings of the domain name are retained on the CDN nodes. If the DNS settings are cached on the local DNS servers, or you have specified the DNS settings in the hosts file to resolve the accelerated domain name to a CDN node, traffic is still forwarded to Alibaba Cloud CDN. Therefore, you must delete the accelerated domain name from Alibaba Cloud CDN to ensure that no unnecessary charges are incurred.

    ![ ](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3110462061/p58738.png)

4.  In the message that requires you to confirm the operation, click **OK**.

5.  In the SMS Verification dialog box, click **Obtain**.

    ![SMS verification](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3060019951/p66084.png)

6.  A verification code is sent to the phone number associated with your Alibaba Cloud account. Enter the **verification code** into the verification code field.

7.  Click **OK**.


