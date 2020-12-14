# Configure a script in the Alibaba Cloud CDN console

EdgeScript enables script-based programmable configurations for Alibaba Cloud Content Delivery Network \(CDN\). EdgeScript allows you to efficiently customize your Alibaba Cloud CDN service based on your business requirements. In the Alibaba Cloud CDN console, you can create scripts based on the EdgeScript coding standard, and publish the scripts to the production environment to customize your Alibaba Cloud CDN service. This topic describes how to create a script in the Alibaba Cloud CDN console.

EdgeScript is a type of script that is designed for Alibaba Cloud CDN. EdgeScript supports complex scripts with simple syntax, and allows you to efficiently customize your Alibaba Cloud CDN service. You can use EdgeScript to build a custom business system based on Alibaba Cloud CDN. Custom scripts can take effect among all CDN nodes within several seconds. Agile and fast service releases and upgrades allow you to develop services in a more efficient way.

The following figure shows the procedure that is used to configure a script in the Alibaba Cloud CDN console.

![Procedure that is used to create a script in the Alibaba Cloud CDN console](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5689762061/p65439.png)

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column.

4.  Click **EdgeScript**.

5.  Create a script in the staging environment.

    1.  On the **Staging Environment** page, click **Add Rule**.

        **Note:** You can create only one script for each domain name. To create more scripts for a domain name, [submit ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).

        ![Staging environment](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5689762061/p65161.png)

    2.  In the pane that appears, set the parameters.

        ![Set the parameters](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5689762061/p98082.png)

        For more information about the EdgeScript parameters, see [Fields](/intl.en-US/EdgeScript/Introduction/How EdgeScript works.md).

        You can customize the script based on the requirements of the scenario. For more information, see [EdgeScript scenarios](/intl.en-US/EdgeScript/EdgeScript scenarios.md).

    3.  Click **Publish to Staging Environment**.

6.  Test the script in the staging environment.

    The following figure shows the IP address of the host that is used to test scripts in the staging environment. Use the IP address of the test host that appears in the Alibaba Cloud CDN console.

    ![IP address of the test host](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6689762061/p65164.png)

    On your machine, find the hosts file under the path C:\\Windows\\System32\\drivers\\etc. Add the IP address of the test host to the hosts file.

7.  After the test is completed, click **Publish All Rules to Production Environment** to publish the script to the production environment.

    **Note:** After you publish a script from the staging environment to the production environment, the script in the staging environment is automatically cleared.

    ![Publish all scripts to the production environment](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6689762061/p65390.png)

8.  To modify scripts that you have already published to the production environment, you must copy the scripts from the production environment to the staging environment, and then modify the scripts. You can click **Copy Rules from Production Environment** to copy scripts from the production environment to the staging environment.

    ![Click Copy Rules from Production Environment](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6689762061/p65389.png)

    After you copy a script from the production environment to the staging environment, you can modify the copied script in the staging environment.

    ![Modify scripts in the staging environment](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6689762061/p65397.png)


