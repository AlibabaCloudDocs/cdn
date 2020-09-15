# Quick start

This topic provides examples to describe how to use EdgeScript to create, save, test, and publish scripts.

You can use EdgeScript to perform the following operations:

-   Save a script to a local file.

    For example, the m3u8.es script is used to block all .m3u8 requests. You can save the script to a local file.

    ```
    $cat m3u8.es
    if eq(substr($uri, -5, -1), '.m3u8') {
        add_rsp_header('X-DEBUG-DENY-REASON', 'block m3u8')
        exit(400)
    }
    ```

-   Publish a script to the test environment.

    ```
    $./es.py action=push_test_env domain=<your domain> rule='{"pos":"head","pri":"0","rule_path":"./m3u8.es","enable":"on"}'
    
    Response Code:
    =============
    200 OK
    
    Response Info:
    ==============
    {
        "RequestId": "FB98CC67-8FBA-44CF-A98A-BCE3B19FE510"
    }
    ```

-   Query scripts in the test environment.

    ```
    $./es.py action=query_test_env domain=<your domain>
    Response Code:
    =============
    200 OK
    
    Response Info:
    ==============
    {
        "DomainConfigs": [
            {
                "Status": "success",    # If success is returned, the script is enabled.
                "ConfigId": 17432558, 
                "FunctionArgs": [
                    {
                        "ArgName": "enable", 
                        "ArgValue": "on"
                    }, 
                    {
                        "ArgName": "pri", 
                        "ArgValue": "0"
                    }, 
                    {
                        "ArgName": "pos", 
                        "ArgValue": "head"
                    }, 
                    {
                        "ArgName": "rule", 
                        "ArgValue": "if eq(substr($uri, -5, -1), '.m3u8') {\n    add_rsp_header('X-DEBUG-DENY-REASON', 'block m3u8')\n    exit(400)\n}\n"
                    }
                ], 
                "FunctionName": "dsl_ex"
            }
        ], 
        "RequestId": "4DDBF3DB-BCAC-4074-AC1E-B6C1F1C6CBFB"
    }
    ```

-   Test scripts.

    ```
    $curl -x Test environment IP:80 -o /dev/null -v 'http://www.archnote.net/test.m3u8'
    < HTTP/1.1 400 Bad Request
    < Server: Tengine
    < Date: Thu, 18 Jul 2019 09:40:41 GMT
    < Content-Type: text/html
    < Content-Length: 265
    < Connection: close
    < X-DEBUG-DENY-REASON: block m3u8
    < Via: cache1.cn1191-1[,0]
    < Timing-Allow-Origin: *
    < EagleId: 2a7b771b15634428415537484e
    ```

-   Publish all scripts in the test environment to the production environment.

    ```
    $./es.py action=push_product_env domain=<your domain>
    Response Code:
    =============
    200 OK
    
    Response Info:
    ==============
    {
        "RequestId": "F4B378F8-6AAE-457A-A70C-E856ED8341D8"
    }
    ```

-   Query scripts in the production environment.

    ```
    $./es.py action=query_product_env domain=<your domain>
    Response Code:
    =============
    200 OK
    
    Response Info:
    ==============
    {
        "DomainConfigs": {
            "DomainConfig": [
                {
                    "Status":"success", 
                    "ConfigId": 17432558, 
                    "FunctionArgs": {
                        "FunctionArg": [
                            {
                                "ArgName": "enable", 
                                "ArgValue": "on"
                            }, 
                            {
                                "ArgName": "pri", 
                                "ArgValue": "0"
                            }, 
                            {
                                "ArgName": "pos", 
                                "ArgValue": "head"
                            }, 
                            {
                                "ArgName": "rule", 
                                "ArgValue": "if eq(substr($uri, -5, -1), '.m3u8') {\n    add_rsp_header('X-DEBUG-DENY-REASON', 'block m3u8')\n    exit(400)\n}\n"
                            }
                        ]
                    }, 
                    "FunctionName": "dsl_ex"
                }
            ]
        }, 
        "RequestId": "36D57C1D-C820-43DA-8E70-DADC4B8BD4DD"
    }
    ```


