# EdgeRoutine CLI工具使用说明

阿里云CDN为您提供EdgeRoutine CLI工具，可以直接在CDN节点执行您自行编写的JavaScript代码，通过本文您可以了解使用EdgeRoutine CLI工具发布代码的具体步骤。

EdgeRoutine CLI工具运行环境需要是Node.js 8.0及以上版本。

EdgeRoutine需要将边缘Serverless环境绑定至您的CDN加速域名，依赖您的阿里云账号进行相关配置，因此您需要在控制台完成加速域名的添加，具体操作，请参见[添加加速域名](/cn.zh-CN/快速入门/添加加速域名.md)。获取AccessKey ID和AccessKey Secret，请参见[创建AccessKey]()。

1.  安装EdgeRoutine CLI工具。

    在终端中运行以下命令进行安装。

    ```
    $ npm install @alicloud/edgeroutine-cli -g
    ```

    **说明：** 目前EdgeRoutine CLI的最新版本为2.0.3，安装完成后您可以运行`edgeroutine-cli -v`命令查询版本号。如果您的版本非最新，建议您升级至最新版本。您使用最新版本的CLI进行build操作时，如果提示“The specified ArgValue is invalid参数无效”，请执行`edgeroutine-cli config`初始化config.js文件后重试。

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

4.  配置域名和AK信息（AccessKey ID和AccessKey Secret）。

    ```
    $ edgeroutine-cli config
    ```

5.  修改边缘程序ER（EdgeRoutine）的执行顺序。

    1.  双击步骤4生成的config.js文件。

    2.  修改pos参数为head或者foot，默认值为head。

        pos代表边缘程序ER执行的位置，决定边缘程序ER和CDN控制台配置（缓存配置、HTTPS配置、访问控制、性能优化、视频相关）的执行顺序。

        -   head：表示边缘程序ER在CDN控制台的配置前执行。
        -   foot：表示边缘程序ER在CDN控制台的配置后执行。
6.  代码发布到模拟环境。

    **说明：** 您将代码发布到生产环境之前必须执行验证模拟环境。

    1.  创建模拟环境代码。

        ```
        $ edgeroutine-cli build
        ```

    2.  查看模拟环境代码。

        ```
        $ edgeroutine-cli build --show
        ```

    3.  回滚模拟环境代码。

        可将模拟环境的代码回滚成线上的代码。回滚后您可以随时继续发布新代码至模拟环境，但此时您无法将空代码发布到生产环境。

        ```
        $ edgeroutine-cli build --rollback
        ```

    4.  删除模拟环境代码。

        删除是指将模拟环境的配置删除，删除后您可以随时继续发布新代码至模拟环境，也可以将空代码发布到生产环境达到删除生产环境ER代码的目的，请注意风险。

        ```
        $ edgeroutine-cli build --delete
        ```

7.  测试模拟环境代码。

    请您在终端环境中访问目标域名，EdgeRoutine模拟环境节点IP为42.123.119.100或42.123.119.101。

    ```
    $ curl-v'http://yourdomain.com/yourpath/'-x42.123.119.100:80
    $ curl -v 'http://yourdomain.com/yourpath/' -x 42.123.119.100:80
    ```

8.  发布代码到生产环境。

    1.  您在完成模拟环境验证后，可以将模拟环境的代码发布到线上环境。

        ```
        $ edgeroutine-cli publish
        ```

        **说明：** 目前EdgeScript和EdgeRoutine共用一个发布系统，如果您同时使用了[EdgeScript](/cn.zh-CN/边缘脚本/EdgeScript概述.md)和EdgeRoutine功能，当您在EdgeRoutine CLI中执行`edgeroutine-cli publish`命令进行发布时，系统会将模拟环境中的EdgeScript和EdgeRoutine配置一起发布至生产环境。您可以在执行publish前使用`edgeroutine-cli build -s`查看模拟环境中的EdgeScript和EdgeRoutine配置，确认无误后再执行publish发布至生产环境。

    2.  查看线上环境代码。

        ```
        $ edgeroutine-cli publish --show
        ```

    3.  （可选）删除线上环境代码，此时将直接彻底删除代码和配置。

        ```
        $ edgeroutine-cli publish --delete
        ```

9.  测试生产环境。

    此时您可直接测试目标域名的线上业务。

    ```
    $ curl -v 'https://yourdomain.com/yourpath/'
    ```


