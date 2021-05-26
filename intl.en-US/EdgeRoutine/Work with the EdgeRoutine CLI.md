# Work with the EdgeRoutine CLI

Alibaba Cloud Content Delivery Network \(CDN\) provides the EdgeRoutine CLI to run custom JavaScript code on CDN nodes. This topic describes how to use the EdgeRoutine CLI to deploy JavaScript code.

The runtime environment of the EdgeRoutine CLI must be Node.js 8.0 or later.

To enable EdgeRoutine, you must map the serverless computing environment on CDN nodes to your accelerated domain name. If you have not prepared the accelerated domain name and AccessKey information for mapping, you must log on to the Alibaba Cloud CDN console with your Alibaba Cloud account. In the console, you can add the domain name to Alibaba Cloud CDN. For more information, see [Add a domain name to Alibaba Cloud CDN](/intl.en-US/Quick Start/Add a domain name to Alibaba Cloud CDN.md). For more information about how to obtain an AccessKey ID and an AccessKey secret, see [Create an AccessKey pair]().

1.  Install the EdgeRoutine CLI.

    On your terminal, run the following command to install the EdgeRoutine CLI:

    ```
    $ npm install @alicloud/edgeroutine-cli -g
    ```

    **Note:** The latest version of the EdgeRoutine CLI is 2.0.3. After you install the EdgeRoutine CLI, you can run the `edgeroutine-cli -v` command to query the version number. We recommend that you upgrade your EdgeRoutine CLI to the latest version. If you use the latest version of the EdgeRoutine CLI to perform the build operation and the message "The specified ArgValue is invalid" appears, run the `edgeroutine-cli config` command to initialize the config.js file and perform the build operation again.

2.  Run the following command to create a code directory and change to the directory:

    ```
    $ mkdir yourProject; cd yourProject
    ```

3.  Initialize the environment and create a code template.

    Run the following command to initialize the environment:

    ```
    $ edgeroutine-cli init
    ```

    The following example shows a code template. If you want to use your own code, you can move your code file to the code directory that you have created, and rename the code file edge.js.

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

4.  Specify your AccessKey ID and AccessKey secret.

    ```
    $ edgeroutine-cli config
    ```

5.  Specify the position where EdgeRoutine runs the script.

    1.  Double-click the config.js file generated in Step 4.

    2.  Set the pos parameter to head or foot based on your business requirements. The default value is head.

        The pos parameter specifies the position where EdgeRoutine runs the script. For example, it specifies whether EdgeRoutine runs the script before or after EdgeRoutine applies the cache settings, HTTPS settings, access control settings, performance settings, and video-related settings.

        -   head: EdgeRoutine runs the script before EdgeRoutine applies the settings specified in the Alibaba Cloud CDN console.
        -   foot: EdgeRoutine runs the script after EdgeRoutine applies the settings specified in the Alibaba Cloud CDN console.
6.  Deploy the code to the staging environment.

    **Note:** Before you deploy the code to the production environment, you must validate the code in the staging environment.

    1.  Build the code in the staging environment.

        ```
        $ edgeroutine-cli build
        ```

    2.  View the code in the staging environment.

        ```
        $ edgeroutine-cli build --show
        ```

    3.  Roll back the code in the staging environment.

        You can roll back code from the staging environment to the production environment. After you roll back code, you can deploy new code to the staging environment. However, you cannot deploy empty code blocks to the production environment.

        ```
        $ edgeroutine-cli build --rollback
        ```

    4.  Delete the code from the staging environment.

        This operation deletes configurations of the staging environment. After you delete code from the staging environment, you can deploy new code to the staging environment. You can deploy empty code blocks to the production environment to delete the deployed code from the production environment. Proceed with caution.

        ```
        $ edgeroutine-cli build --delete
        ```

7.  Validate the code in the staging environment.

    You must connect to the accelerated domain name in the terminal environment by using the IP address of the staging environment for EdgeRoutine. The IP address is 42.123.119.100 or 42.123.119.101.

    ```
    $ curl-v'http://yourdomain.com/yourpath/'-x42.123.119.100:80
    ```

8.  Deploy the code to the production environment.

    1.  After you validate the code in the staging environment, you can deploy the code to the production environment.

        ```
        $ edgeroutine-cli publish
        ```

        **Note:** EdgeScript and EdgeRoutine use the same deployment system. If you use [EdgeScript](/intl.en-US/EdgeScript/Overview.md) and EdgeRoutine at the same time, the `edgeroutine-cli publish` command that is run in the EdgeRoutine CLI will deploy scripts of both EdgeScript and EdgeRoutine from the staging environment to the production environment. Before you deploy code, you can run the `edgeroutine-cli build -s` command to query scripts of EdgeScript and EdgeRoutine that are in the staging environment. After you confirm the configurations that you want to deploy to the production environment, run the edgeroutine-cli publish command to deploy the configurations.

    2.  View the code in the production environment.

        ```
        $ edgeroutine-cli publish --show
        ```

    3.  Delete the code from the production environment. Then, the code and relevant configurations are deleted. This step is optional.

        ```
        $ edgeroutine-cli publish --delete
        ```

9.  Run tests in the production environment.

    You can test the workloads of the accelerated domain name in the production environment.

    ```
    $ curl -v 'https://yourdomain.com/yourpath/'
    ```


