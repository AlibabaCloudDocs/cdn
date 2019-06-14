# UA blacklist and whitelist {#task_371735 .task}

This topic describes UA blacklists and whitelists and how to configure them in the CDN console.

Both UA blacklists and whitelists contain `Usage-Agent` information elements \(IEs\), which are carried in request messages. After you configure UA blacklists or whitelists for a CDN node, the CDN node filters request messages and permits only the access requests from specific clients.

**Note:** 

-   `Usage-Agent` IEs are not case-sensitive and can contain wildcard characters \(\*\). The multiple options in a `Usage-Agent` IE are separated by using vertical bars \(|\). An example `Usage-Agent` IE is as follows: `*curl*|*IE*|*chrome*|*firefox*`.
-   Only the UA blacklist or whitelist can be enabled at a specific time point.

1.  Log on to the [CDN console](https://cdn.console.aliyun.com/overview).
2.  In the left-side navigation pane, click **Domain Names**.
3.  Find the domain name you want to set, and click **Manage** in the **Actions** column.
4.  In the left-side navigation pane, click **Resource Access Control**.
5.  On the UA whitelist/blacklist tab, click **Modify**.
6.  Configure the blacklist or whitelist as needed, and click **Confirm**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/301857/156047551748023_en-US.png)


