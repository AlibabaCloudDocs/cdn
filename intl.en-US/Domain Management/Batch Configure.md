# Batch Configure {#concept_orv_fcc_r2b .concept}

## Introduction {#section_ed3_5qd_r2b .section}

You can copy specific configurations of a domain name then apply them to one or more other domain names.

**Note:** You can only copy the configuration of a domain name when it is running normally.

## Procedure {#section_pw1_zqd_r2b .section}

Make sure that you have configured the domain name that you want to copy.

**Note:** You cannot copy an HTTPS certificate to another domain name. Configure it independently.

**Warning:** You cannot return to the configuration before copying. Make sure the source domain name is on service or has existing configuration, and its bandwidth is large. Copy with caution.

1.  On the Domain Names page, select the domain name you want to copy, then click **Copy Configuration**. ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17043/15631027348715_en-US.png)
2.  Select the configuration items you want to copy, then click **Next**.

    **Note:** You cannot copy the origin site and other configurations at the same time.

3.  Select the target domain name you want to apply configurations to, then click **Next Step**.

    You can also enter keywords to search for the domain name.

    **Note:** The copied configurations will overwrite any configurations you previously set for the target domain name. Take caution when copying configurations, or your service may become unavailable.

4.  Click **Confirm**. 

## Note {#section_pbl_wfm_w2b .section}

-   For Custom back-to-origin HTTP header, copying means adding configuration to your existing. For example, if Domain A has 2 Custom back-to-origin HTTP header configurations, and you copy 5 configurations from Domain B, you may have 7 configurations in total.
-   For HTTP header, copying means covering existing configurations. For example, if Domain A's Cache\_Control is set to Private, and you copy Domain B's configuration of Public, then your Cache Control is now set to Public.
-   Copying configurations of switches, Referer or IP's blacklist or whitelists cover existing configurations.

