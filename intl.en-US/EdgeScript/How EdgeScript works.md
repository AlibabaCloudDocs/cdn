# How EdgeScript works

This topic describes how EdgeScript \(ES\) works, the model of scripts in ES, positions where the scripts are executed, script priorities, and execution and termination of scripts.

## How it works

Scripts created by using ES are the same as the standard configurations specified in the Alibaba Cloud Content Delivery Network \(CDN\) console. They process requests that are sent to CDN nodes. The following figure shows the positions where scripts are executed. After a CDN node receives a request, the CDN node processes the request based on the configurations in the Alibaba Cloud CDN and scripts in ES. In a request processing pipeline, you can specify the position where a script is executed. A script can be executed before the configurations in the console are applied \(head\) or after they are applied \(foot\).

![5](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7950738161/p255453.png)

## Model

Scripts in ES are executed based on the following model:

-   ES executes scripts to achieve different functions. Functions are triggered only when the conditions in scripts are met.
-   You can specify the position where a script is executed and the priority of the script in a request processing pipeline.
-   Scripts in ES are managed based on domain names.

## Positions and priorities

The positions and priorities for executing scripts are:

-   Positions

    You can execute a script at the head or foot of a request processing pipeline.

    -   Head: for authentication, blocking, or throttling.
    -   Foot: for cache settings, back-to-origin authentication, and A/B testing.
    ![ES](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4522036061/p62071.png)

-   Priorities

    If you want to execute more than one script at the head or foot of a request processing pipeline, you can assign priorities to these scripts to determine the execution order.


## Execution and termination

The execution and termination of scripts are defined based on the following rules:

-   Execution of scripts
    -   If a condition that ends with `return true` in a script is met, the script is executed.
    -   If a condition that ends with `return false` in a script is met, the script is skipped.
-   Termination of scripts

    For scripts that are executed in the same position, you can choose to skip the subsequent scripts when a script is executed.


