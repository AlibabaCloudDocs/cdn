# Use the EdgeScript CLI to configure scripts

This topic describes the functions of the EdgeScript command line interface \(CLI\) and how to use the EdgeScript CLI.

## Functions

The EdgeScript CLI supports the following functions:

-   Publish scripts to the staging environment.
-   Publish scripts from the staging environment to all CDN nodes \(production environment\), and roll back scripts from the production environment to the staging environment.
-   Query, modify, and delete scripts in the staging and production environments.

## Download the EdgeScript CLI

You can click [attachment](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/113904/cn_zh/1580886874093/openapi-es-tools-master-b7a3ee97c5d23b5885d8e0ed5fa674b10f83d9e5.zip) to download the EdgeScript CLI.

## Work with EdgeScript CLI

You can use the EdgeScript CLI to perform the following tasks:

-   Configure your AccessKey pair.

    ```
    $python ./es.py config --id=AK_ID --secret=AK_SECRET
    $cat aliyun.ini
    [Credentials]
    accesskeyid = AccessKey ID
    accesskeysecret = AccessKey secret
    ```

-   Publish a script to the staging or production environment.

    ```
    ./es.py action=push_test_env domain=<domain> rule='{"pos":"<head|foot>","pri":"0-999","rule_path":"<the es code path>","enable":"<on|off>"}'
    ./es.py action=push_product_env domain=<domain> rule='{"pos":"<head|foot>","pri":"0-999","rule_path":"<the es code path>","enable":"<on|off>","configid":"<configid>"}'                    
    ```

    **Note:**

    -   Create a script: No configuration ID \(configid\) is required.
    -   Modify a script: You must specify the configuration ID \(configid\). You can perform the query action to query the configuration ID \(configid\) of a script.
    -   You can specify multiple scripts.
-   Query scripts in the staging or production environment.

    ```
    ./es.py action=query_test_env domain=<domain>
    ./es.py action=query_product_env domain=<domain>
    ```

-   Delete a script from the staging or production environment.

    ```
    ./es.py action=del_test_env domain=<domain> configid=<configid>
    ./es.py action=del_product_env domain=<domain> configid=<configid>                  
    ```

    **Note:** You can also call an API operation to query the configuration IDs \(configid\) of scripts.

-   Publish scripts from the staging environment to the production environment or roll back scripts from the production environment to the staging environment.

    ```
    ./es.py action=publish_test_env domain=<domain>
    ./es.py action=rollback_test_env domain=<domain>
    ```


## Request header debugging

1.  Perform debugging.

    To perform debugging, you can configure the \_es\_dbg parameter in the Alibaba Cloud CDN console that supports WebIDE or run the following command:

    ```
     ./es.py action=push_test_env domain=<domain> rule='{"pos":"<head|foot>","pri":"0-999","rule_path":"<the es code path>","enable":"<on|off>","configid":"<configid>", "option":"_es_dbg=123"}'
    ```

2.  Check debugging results.

    The \_es\_dbg parameter is contained in the request header. The value of \_es\_dbg is set to the value of \_es\_dbg that you set in the option extension of the script. To view the debugging result, check the following information contained in the response header:

    TRACE information: `X-DEBUG-ES-TRACE-RULE-{Script ID}`. Check the control flow of the scrip. The format of the control flow is `_flow number_function name (input parameter): Response{_execution time}`.


