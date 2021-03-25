# EdgeScript monitoring

EdgeScript \(ES\) supports the monitoring feature. You can query the monitoring data to check whether scripts are executed as expected at the edges.

ES allows you to create scripts to customize your Alibaba Cloud Content Delivery Network \(CDN\) service. If the standard features provided in the Alibaba Cloud CDN console cannot meet your configuration requirements, you can use ES to create custom scripts that support more complex request processing logic. ES provides a wide array of built-in functions that simplify the programming process. You can use simple syntax and logic to invoke these functions in custom scripts. For more information, see [Overview](/intl.en-US/EdgeScript/Introduction/Overview.md).

## Features

You can navigate to the EdgeScript page to query the status of scripts. You can query the monitoring data of scripts and errors within the last three months. The time range in each query can be up to one month.

|Metric|Description|
|------|-----------|
|**Status**|Indicates the status of each script. If you have configured a script for an accelerated domain name, the script can be in one of the following status after a client request arrives at a CDN node:-   NonExecution

The script is not executed. For example, the script is set to be executed at the foot of the pipeline. This indicates that the script is executed only after all other scripts are executed. However, a request may be completed before it reaches the foot of the pipeline. For example, the request may be redirected or blocked by hotlink protection. In this case, the script at the foot of the pipeline is not executed.

-   ExecutedAndHit

The script is executed and the execution result is return true. This indicates that the request matches the logic in the script.

-   ExecutedButNotHit

The script is executed but the execution result is not return true. This indicates that the request does not match the logic in the script. For example, the script does not contain a return true statement, or the script automatically returns a return false result.

-   Exception

An error occurs while Alibaba Cloud CDN is executing the script. Typically, the error is caused by logic errors in the script or timeouts of script execution. For example, a parameter passed to the request is set to an invalid value or Alibaba Cloud CDN has been executing the script for more than 50 milliseconds. You can add the \_es\_dbg **extension** to the script and use the debugging tool in the upper-corner of the EdgeScript page to debug the code. Then, you can use the debugging information to troubleshoot the error. For more information about how to add the \_es\_dbg extension, see [Configure a script in the Alibaba Cloud CDN console](/intl.en-US/EdgeScript/Introduction/Configure a script in the Alibaba Cloud CDN console.md).

**Note:** You can set \_es\_dbg to any value. Client requests must carry the same value. For example, if you set \_es\_dbg=123 in the Alibaba Cloud CDN console, client requests must also carry \_es\_dbg=123. |
|**Error**|Indicates that an error occurs while Alibaba Cloud CDN is executing the script. In this case, an error code is returned. Error codes and descriptions:-   400: The script contains an unsupported function.
-   401: The number of parameters expected by the function is invalid.
-   402: The type of string does not match the one specified in the function.
-   403: The type of digit does not match the one specified in the function.
-   404: The type of dictionary does not match the one specified in the function.
-   405: The Boolean type does not match the one specified in the function.
-   406: The type of function does not match the one specified in the function.
-   407: The script timed out.
-   408: The number of times that Alibaba Cloud CDN has executed scripts has reached the upper limit.
-   409: The number of times that the script has been looped has reached the upper limit.
-   410: The number of times that the script has been looped has reached the upper limit.
-   499: An unknown error occurred. |

## Procedure

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, choose **Monitoring & Usage Analytics** \> **EdgeScript**.

3.  On the **EdgeScript** page, click the **Status** or **Error** tab.

4.  Select the domain name that you want to query, set the time range to query, and then click **Query**.

    The system returns scripts that are in one of the preceding states or error codes based on the specified query conditions.


