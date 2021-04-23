# Use the EdgeScript CLI to configure scripts

Alibaba Cloud provides the EdgeScript command-line interface \(CLI\). The EdgeScript CLI allows you to publish scripts that are created on premises to the staging environment and production environment. You can query, modify, and delete scripts in the staging and production environments by using the EdgeScript CLI. This topic describes how to use the EdgeScript CLI.

1.  Download the [EdgeScript CLI](https://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/113904/cn_zh/1580886874093/openapi-es-tools-master-b7a3ee97c5d23b5885d8e0ed5fa674b10f83d9e5.zip).

2.  Configure your AccessKey ID and AccessKey secret.

    ```
    python ./es.py config --id=AK_ID --secret=AK_SECRET
    cat aliyun.ini
    [Credentials]
    accesskeyid = Updated AccessKey ID
    accesskeysecret = Updated AccessKey secret
    ```

3.  Publish a script to the staging or production environment.

    ```
    ./es.py action=push_test_env domain=<domain> rule='{"pos":"<head|foot>","pri":"0-999","rule_path":"<the es code path>","enable":"<on|off>"}'
    ./es.py action=push_product_env domain=<domain> rule='{"pos":"<head|foot>","pri":"0-999","rule_path":"<the es code path>","enable":"<on|off>","configid":"<configid>"}'                    
    ```

    The following table describes the fields in the script.

    |Field|Required|Description|
    |-----|--------|-----------|
    |enable|Yes|Specifies whether to enable or disable the script. Valid values:     -   **on**
    -   **off** |
    |pos|Yes|The position where the script is executed. Valid values:     -   **head**
    -   **foot** |
    |pri|Yes|The priority of the script. You can prioritize only scripts that are executed in the same position. Valid values: **0 to 999**.     -   The value 0 indicates the highest priority.
    -   The value 999 indicates the lowest priority. |
    |rule|Yes|The content of the script.|
    |brk|No|Specifies whether to skip the subsequent scripts if the current script is executed. Valid values:     -   **on**
    -   **off** |
    |testip|No|The IP address of the client. By default, this field is empty. If you specify a client IP address, only requests sent from the specified IP address can trigger the execution of the script.|
    |option|No|An extension. EdgeScript supports extensions. You can set this field to `_es_dbg=signature` to perform response header debugging.|

    **Note:**

    -   When you create a script, you do not need to specify the configuration ID.
    -   To modify a script, you must specify the configuration ID. You can call the query operation to obtain the configuration ID of the script.
    -   You can specify multiple scripts.
4.  Query scripts in the staging or production environment.

    ```
    ./es.py action=query_test_env domain=<domain>
    ./es.py action=query_product_env domain=<domain>
    ```

5.  Delete a script from the staging or production environment.

    ```
    ./es.py action=del_test_env domain=<domain> configid=<configid>
    ./es.py action=del_product_env domain=<domain> configid=<configid>                  
    ```

6.  Publish scripts from the staging environment to the production environment or roll back scripts from the production environment to the staging environment.

    ```
    ./es.py action=publish_test_env domain=<domain>
    ./es.py action=rollback_test_env domain=<domain>
    ```


For example, you can create, save, test, and publish the m3u8.es script that is used to block all M3U8 requests. For more information, see [Quick start]().

## Request header debugging

1.  Perform debugging.

    To perform debugging, you can configure the `_es_dbg` parameter in the ApsaraVideo Live console that supports WebIDE or run the following command:

    ```
     ./es.py action=push_test_env domain=<domain> rule='{"pos":"<head|foot>","pri":"0-999","rule_path":"<the es code path>","enable":"<on|off>","configid":"<configid>", "option":"_es_dbg=123"}'
    ```

2.  Check debugging results.

    The `_es_dbg` parameter is contained in the request header. The value of the \_es\_dbg parameter is set to the value of `_es_dbg` that you set in the option extension of the script. To view the debugging result, check the following information contained in the response header:

    TRACE information: `X-DEBUG-ES-TRACE-RULE-{Script ID}`. Check the control flow of the script. The format of the control flow is `_flow number_function name (input parameter): Response{_execution time}`.


