# 通过CLI工具配置EdgeScript

本文为您介绍EdgeScript CLI工具的用途和使用说明。

## 用途

使用EdgeScript CLI工具，用户可以执行如下操作：

-   将本地编写的EdgeScript规则发布到模拟环境进行测试。
-   将模拟环境的EdgeScript规则发布至全网（生产环境）或回滚（模拟环境）。
-   对模拟环境和生产环境的EdgeScript规则进行查询、修改和删除。

## 工具下载

您可以下载CLI工具配置EdgeScript。更多信息，[下载CLI工具](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/113904/cn_zh/1580886874093/openapi-es-tools-master-b7a3ee97c5d23b5885d8e0ed5fa674b10f83d9e5.zip)。

## 使用说明

EdgeScript CLI的使用说明如下：

-   配置AccessKey ID和AccessKey Secret

    ```
    python ./es.py config --id=AK_ID --secret=AK_SECRET
    cat aliyun.ini
    [Credentials]
    accesskeyid = 更新后的AccessKey ID
    accesskeysecret = 更新后的AccessKey Secret
    ```

-   发布EdgeScript规则至模拟环境或生产环境

    ```
    ./es.py action=push_test_env domain=<domain> rule='{"pos":"<head|foot>","pri":"0-999","rule_path":"<the es code path>","enable":"<on|off>"}'
    ./es.py action=push_product_env domain=<domain> rule='{"pos":"<head|foot>","pri":"0-999","rule_path":"<the es code path>","enable":"<on|off>","configid":"<configid>"}'                    
    ```

    **说明：**

    -   新增规则不需要指定configid。
    -   修改规则需要指定configid，使用查询接口可获取到对应规则的configid。
    -   您可以指定多条rule。
-   查询模拟环境或生产环境下的EdgeScript规则

    ```
    ./es.py action=query_test_env domain=<domain>
    ./es.py action=query_product_env domain=<domain>
    ```

-   删除模拟环境或生产环境下的EdgeScript规则

    ```
    ./es.py action=del_test_env domain=<domain> configid=<configid>
    ./es.py action=del_product_env domain=<domain> configid=<configid>                  
    ```

    **说明：** 使用查询接口可获取到对应规则的configid。

-   模拟环境的EdgeScript规则执行正式发布或回滚

    ```
    ./es.py action=publish_test_env domain=<domain>
    ./es.py action=rollback_test_env domain=<domain>
    ```


## 实时调试方式

1.  配置实时调试。

    您可以通过控制台的WebIDE图形化操作页面进行\_es\_dbg配置，也可以使用如下命令进行配置。

    ```
     ./es.py action=push_test_env domain=<domain> rule='{"pos":"<head|foot>","pri":"0-999","rule_path":"<the es code path>","enable":"<on|off>","configid":"<configid>", "option":"_es_dbg=123"}'
    ```

2.  测试请求。

    测试时请求参数中携带\_es\_dbg参数，参数值为配置的option中\_es\_dbg的值，关注如下响应头信息。

    Trace信息：`X-DEBUG-ES-TRACE-RULE-{规则ID}`，查看对应规则的执行流，格式为`_行号_函数名(入参):返回值{_执行耗时}`。


