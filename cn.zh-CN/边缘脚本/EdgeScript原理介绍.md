# EdgeScript原理介绍

本文为您介绍EdgeScript的运行原理、规则模型、执行位置与优先级、命中与中断执行。

## 运行原理

您配置的边缘脚本规则与CDN控制台上的标准配置一样，都是对CDN请求进行处理。边缘脚本的执行位置如图所示，当客户端请求到达CDN节点后，CDN节点网关会根据您在控制台上设置的标准配置、边缘脚本规则对请求进行处理。以CDN控制台上的标准配置为参照物，边缘脚本可选择在请求处理的最前面或最后面生效。

![5](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8625907161/p255453.png)

## 规则模型

EdgeScript的规则模型如下：

-   EdgeScript的规则模型的核心出发点是将不同业务功能隔离至不同规则，以及控制规则的执行流。
-   EdgeScript的规则模型中的每条规则可以各自选择规则的执行位置（即介入请求处理的位置）和优先级。
-   EdgeScript的规则模型以域名为度。

## 执行位置与优先级

EdgeScript的执行位置与优先级如下：

-   执行位置

    EdgeScript规则的执行位置为请求处理开始和请求处理结尾。

    -   请求处理开始：常用应用场景为一次鉴权、拦截、限速等。
    -   请求处理结束：常用应用场景为缓存设置、回源鉴权、AB测试等。
    ![ES](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/7064139651/p62071.png)

-   优先级

    处于同一执行位置的多条规则，可以通过选择优先级，决定其先后执行顺序。


## 命中与中断执行

EdgeScript的命中与中断执行如下：

-   EdgeScript规则的命中定义
    -   当规则结尾是以`return true`返回时：规则模型认为该规则命中。
    -   当规则结尾是以`return false`返回时：规则模型认为该规则未命中。
-   EdgeScript规则的中断执行

    对于命中规则，可以选择终止本阶段剩余规则的执行。


