# EdgeRoutine CLI工具使用说明

阿里云CDN为您提供EdgeRoutine CLI工具，可以直接在CDN节点执行您自行编写的JavaScript代码，通过本文您可以了解使用EdgeRoutine CLI工具发布代码的具体步骤。

EdgeRoutine CLI工具运行环境需要Node.js 8.0及以上版本。

EdgeRoutine需要将边缘Serverless环境绑定至您的CDN加速域名，依赖您的阿里云账号来进行相关配置，所以您需要在控制台完成添加加速域名，具体操作请参见[添加加速域名](/cn.zh-CN/快速入门/添加加速域名.md)。获取AccessKeyID和AccessKeySecret，请参见[创建AccessKey]()。

1.  安装EdgeRoutine CLI工具。

    在终端中运行以下命令进行安装。

    ```
    $ npm install @alicloud/edgeroutine-cli -g
    ```

2.  创建代码目录并切换到已创建目录。

    ```
    $ mkdir yourProject; cd yourProject
    ```

3.  初始化环境并创建模板代码。

    初始化环境命令如下所示。

    ```
    $ edgeroutine-cli init
    ```

    代码模板示例如下，如果您已有目标代码，您可以将您的代码文件移动到当前目录命名为edge.js即可。

    ```
    /**
     * Add the necessary event listener
     * @param {Event} fetch event, {Function} async function
     */
    addEventListener('fetch', event => {
      event.respondWith(handleRequest(event.request))
    })
    /**
     * Make a response to client
     * @param {Request} request
     */
    async function handleRequest(request) {
      return new Response('Hello World!', { status: 200 })
    }
    ```

4.  配置域名和AK信息（AccessKeyID和AccessKeySecret）。

    ```
    $ edgeroutine-cli config
    ```

5.  代码发布到灰度环境。

    **说明：** 在您将代码发布到生产环境之前必须执行验证灰度环境。

    1.  创建灰度环境代码。

        ```
        $ edgeroutine-cli build
        ```

    2.  查看灰度环境代码。

        ```
        $ edgeroutine-cli build --show
        ```

    3.  删除灰度环境代码。

        ```
        $ edgeroutine-cli build --delete
        ```

    4.  回滚灰度环境代码。

        您可以随时继续发布，但此时您无法将空代码发布到生产环境，请注意回滚和删除的区别。

        ```
        $ edgeroutine-cli build --rollback
        ```

6.  测试灰度环境代码。

    请您在终端环境中访问目标域名，EdgeRoutine灰度环境节点IP：42.123.119.50或42.123.119.51。

    ```
    $ curl-v'http://yourdomain.com/yourpath/'-x42.123.119.50:80
    ```

7.  发布代码到生产环境。

    1.  当您完成验证灰度环境时，您可将灰度环境的代码发布到线上环境。

        ```
        $ edgeroutine-cli publish
        ```

    2.  查看线上环境代码。

        ```
        $ edgeroutine-cli publish --show
        ```

    3.  （可选）删除线上环境代码，此时将直接彻底删除代码和配置。

        ```
        $ edgeroutine-cli publish --delete
        ```

8.  测试生产环境。

    此时您可直接测试目标域名的线上业务。

    ```
    $ curl -v 'https://yourdomain.com/yourpath/'
    ```


