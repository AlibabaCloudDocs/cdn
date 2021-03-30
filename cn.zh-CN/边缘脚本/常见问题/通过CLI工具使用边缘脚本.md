# 通过CLI工具使用边缘脚本

阿里云为您提供边缘脚本CLI工具，可以将您本地编写的边缘脚本规则发布到模拟环境进行测试，并发布至生产环境，也可以对模拟环境和生产环境的边缘脚本规则进行查询、修改和删除。本文为您介绍边缘脚本CLI工具的使用方法。

1.  下载CLI工具。更多信息，请参见[下载CLI工具](https://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/113904/cn_zh/1580886874093/openapi-es-tools-master-b7a3ee97c5d23b5885d8e0ed5fa674b10f83d9e5.zip)。

2.  配置AccessKey ID和AccessKey Secret。

    ```
    python ./es.py config --id=AK_ID --secret=AK_SECRET
    cat aliyun.ini
    [Credentials]
    accesskeyid = 更新后的AccessKey ID
    accesskeysecret = 更新后的AccessKey Secret
    ```

3.  发布边缘脚本规则至模拟环境或生产环境。

    ```
    ./es.py action=push_test_env domain=<domain> rule='{"pos":"<head|foot>","pri":"0-999","rule_path":"<the es code path>","enable":"<on|off>"}'
    ./es.py action=push_product_env domain=<domain> rule='{"pos":"<head|foot>","pri":"0-999","rule_path":"<the es code path>","enable":"<on|off>","configid":"<configid>"}'                    
    ```

    规则字段说明，请参见下表：

    |字段名称|是否必选|说明|
    |----|----|--|
    |enable|是|是否生效。取值：     -   **on**
    -   **off** |
    |pos|是|执行位置。取值：     -   **head**
    -   **foot** |
    |pri|是|执行优先级。不同执行位置的优先级各自独立。取值范围：**0~999**。    -   0表示优先级最高
    -   999表示优先级最低。 |
    |rule|是|规则内容。|
    |brk|否|本规则命中情况下，是否终止本阶段剩余规则的执行。取值：     -   **on**
    -   **off** |
    |testip|否|测试客户IP。默认为空。如果配置了该参数，则只有客户端IP地址可触发本条规则执行。|
    |option|否|扩展项。当前支持扩展。`_es_dbg=signature`用于增加调试响应头。|

    **说明：**

    -   新增规则不需要指定configid。
    -   修改规则需要指定configid，使用查询接口可获取到对应规则的configid。
    -   您可以指定多条rule。
4.  查询模拟环境或生产环境下的边缘脚本规则。

    ```
    ./es.py action=query_test_env domain=<domain>
    ./es.py action=query_product_env domain=<domain>
    ```

5.  删除模拟环境或生产环境下的边缘脚本规则。

    ```
    ./es.py action=del_test_env domain=<domain> configid=<configid>
    ./es.py action=del_product_env domain=<domain> configid=<configid>                  
    ```

6.  模拟环境的边缘脚本规则执行正式发布或回滚。

    ```
    ./es.py action=publish_test_env domain=<domain>
    ./es.py action=rollback_test_env domain=<domain>
    ```


基于m3u8.es规则拦截所有.m3u8请求做示例，为您详细介绍边缘规则的编写、保存、测试和发布的操作方法。具体操作，请参见[边缘脚本操作示例]()。

## 实时调试方式

1.  配置实时调试。

    您可以通过控制台的WebIDE图形化操作页面进行`_es_dbg`配置，也可以使用如下命令进行配置。

    ```
     ./es.py action=push_test_env domain=<domain> rule='{"pos":"<head|foot>","pri":"0-999","rule_path":"<the es code path>","enable":"<on|off>","configid":"<configid>", "option":"_es_dbg=123"}'
    ```

2.  测试请求。

    测试时请求参数中携带`_es_dbg`参数，参数值为配置的option中`_es_dbg`的值，关注如下响应头信息。

    Trace信息：`X-DEBUG-ES-TRACE-RULE-{规则ID}`，查看对应规则的执行流，格式为`_行号_函数名(入参):返回值{_执行耗时}`。


