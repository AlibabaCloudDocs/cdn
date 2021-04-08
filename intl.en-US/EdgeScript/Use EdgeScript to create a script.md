# Use EdgeScript to create a script

In the Alibaba Cloud Content Delivery Network \(CDN\) console, you can create scripts based on the EdgeScript \(ES\) coding conventions, and publish the scripts to the production environment to customize your CDN service. This topic describes how to use ES to create a script in the Alibaba Cloud CDN console.

## Procedure

![1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8371687161/p249648.png)

1.  Log on to the[Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  Find the domain name that you want to manage and click **Manage**.

4.  Click **EdgeScript**.

5.  Create a script in the staging environment.

    1.  On the **Staging Environment** tab, click **Add Rule** and set the parameters.

        **Note:** You can create only one script for each domain name. To create more scripts for a domain name,[submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).

        ![1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8371687161/p249714.png)

        The following table describes the parameters.

        |Parameter|Required|Description|
        |---------|--------|-----------|
        |Script Name|Yes|Specify a name for the script. The name can contain letters, digits, and underscores \(\_\).|
        |Script Code|Yes|Specify the content of the script.         -   You can directly write a script or click **Use Code Template** to use a code template.
        -   Write a script based on your business requirements. For more information, see [EdgeScript scenarios](/intl.en-US/EdgeScript/EdgeScript scenarios.md). |
        |Priority|Yes|Specify a priority for the script. Valid values are **0 to 999**. A greater value indicates a higher priority.|
        |Run Script At|Yes|Specify the position where you want to execute the script. For more information, see [Positions and priorities](/intl.en-US/EdgeScript/How EdgeScript works.md).|
        |Enable|Yes|Specify whether you want to enable the script.|
        |Break|No|Specify whether to skip the subsequent scripts if the current script is executed. After you turn on Break, the subsequent scripts are skipped if the current script is executed.|
        |Extensions|No|ES supports extensions. You can add only the `_es_dbg=signature` extension.|

    2.  Click **Publish to Staging Environment**.

6.  Test the script in the staging environment.

    The test IP address in the following figure is for reference only. The actual test IP address shall prevail.

    ![IP address of the test host](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6689762061/p65164.png)

    On your client, find the hosts file under the path C:\\Windows\\System32\\drivers\\etc. Add the IP address of the test host to the hosts file.

7.  After you test the script, click **Publish All Rules to Production Environment** to publish all scripts from the staging environment to the production environment.

    **Note:** After you publish the script from the staging environment to the production environment, the script is automatically deleted from the staging environment.

    ![Publish all scripts to the production environment](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6689762061/p65390.png)

8.  To create more scripts or modify the scripts that are already published to the production environment, you must first copy the scripts from the production environment to the staging environment, and then modify them or create more scripts. Click **Copy Rules from Production Environment** to copy the scripts from the production environment to the staging environment.

    ![Copy scripts from the production environment](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6689762061/p65389.png)

    After you copy a script from the production environment to the staging environment, you can modify the copied script in the staging environment, as shown in the following figure.

    ![Modify scripts in the staging environment](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6689762061/p65397.png)


You can also use the EdgeScript CLI to create and manage scripts. For more information, see [t1054241.md\#](/intl.en-US/EdgeScript/FAQ/Use the EdgeScript CLI to configure scripts.md).

