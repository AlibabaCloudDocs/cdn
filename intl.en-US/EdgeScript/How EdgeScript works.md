# How EdgeScript works

This topic describes the model of scripts in EdgeScript, positions where the scripts are executed, script priorities, execution and termination of scripts, and fields that each script contains.

## Model

Scripts in EdgeScript are executed by using the following model:

-   EdgeScript executes scripts to achieve different functions. Functions are triggered when the conditions in scripts are met.
-   You can specify the position where a script is executed and the priority of the script in a request processing pipeline.
-   Scripts in EdgeScript are managed based on domain names.

## Positions and priorities

The execution positions and priorities for executing scripts are:

-   Positions

    You can execute a script at the start or end of a request processing pipeline.

    -   Start: for authentication, blocking, or throttling.
    -   End: for cache setting, back-to-origin authentication, and A/B testing.
    ![ES](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4522036061/p62071.png)

-   Priorities

    If you want to execute more than one script at the start or end of a request processing pipeline, you can assign priorities to these scripts to determine the execution order.


## Execution and termination

The execution and termination of scripts are defined as follows:

-   Execution of scripts
    -   If a condition that ends with `return true` in a script is met, the script is executed.
    -   If a condition that ends with `return false` in a script is met, the script is skipped.
-   Termination of scripts

    For scripts that are executed in the same position, you can choose to skip the subsequent scripts when a script is executed.


## Fields

The following table describes the fields that you can use in a script.

|Field|Required|Definition|Description|
|-----|--------|----------|-----------|
|enable|Y|Enables or disables the script.|Valid values: -   on
-   off |
|pos|Y|The position where the script is executed.|Valid values: -   head
-   foot |
|pri|Y|The priority of the script.|Valid values: from 0 to 999. Value 0 indicates the highest priority and value 999 indicates the lowest priority. You can only prioritize scripts that are executed in the same position.|
|rule|Y|The content of the script.|None|
|brk|N|Indicates whether to skip the subsequent scripts if the current script is executed.|Valid values: -   on
-   off |
|testip|N|The IP address of the client.|By default, this field is empty. If you specify a client IP address, only requests sent from the specified IP address can trigger the execution of the script.|
|option|N|An extension.|EdgeScript supports extensions. You can set this field to `_es_dbg=signature` to perform response header debugging.|

