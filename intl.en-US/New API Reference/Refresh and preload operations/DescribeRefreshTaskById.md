# DescribeRefreshTaskById

Queries the status of refresh or prefetch tasks by ID for an accelerated domain name.

**Note:**

-   You can query data up to the last 30 days.
-   The maximum number of times that each user can call this operation per second is 30.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer automatically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeRefreshTaskById&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeRefreshTaskById|The operation that you want to perform. Set the value to **DescribeRefreshTaskById**. |
|TaskId|String|Yes|12345678|The ID of the task that you want to query.

 You can call the [RefreshObjectCaches](~~91164~~) operation to query task IDs. Then, you can use the task IDs to query task status. You can specify at most 10 task IDs. Separate multiple task IDs with commas \(,\). |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|E0C2EF95-B1EC-4C93-855E-2059A7DA2B7B|The ID of the request |
|Tasks|Array of CDNTask| |A list of tasks. |
|CreationTime|String|2020-08-03T08:54:23Z|The time when the task was created. The time is displayed in UTC. |
|Description|String|Internal Error|The error returned when the refresh or prefetch task failed. Valid values:

 -   **InternalError**: An internal error occurred.
-   **OriginTimeout**: The response from the origin server timed out.
-   **OriginReturn StatusCode 5XX**: The origin server returned a 5XX error. |
|ObjectPath|String|http://example.com/abc.jpg|The path of the object refreshed by the refresh task. |
|ObjectType|String|file|The type of the task. Valid values:

 -   **file**: refreshes an individual file.
-   **directory**: refreshes files under the specified directories.
-   **preload**: prefetches an individual file. |
|Process|String|100%|The progress of the task, in percentage. |
|Status|String|Complete|The status of the task. Valid values:

 -   **Complete**: the task has completed.
-   **Pending**: The task is pending.
-   **Refreshing**: The task is in progress.
-   **Failed**: The task has failed. |
|TaskId|String|12345678|The ID of the task. |
|TotalCount|Long|2|The total number of tasks. |

## Examples

Sample requests

```
http(s)://cdn.aliyuncs.com/? Action=DescribeRefreshTaskById
&TaskId=12345678
&<Common request parameters>
```

Sample responses

`XML` format

```
<DescribeRefreshTaskByIdResponse>
  <RequestId>E0C2EF95-B1EC-4C93-855E-2059A7DA2B7B</RequestId>
  <Tasks>
        <CreationTime>2020-08-03T08:54:23Z</CreationTime>
        <Description></Description>
        <ObjectPath>http://example.com/abc.jpg</ObjectPath>
        <ObjectType>file</ObjectType>
        <Process>100%</Process>
        <Status>Complete</Status>
        <TaskId>12345678</TaskId>
  </Tasks>
  <Tasks>
        <CreationTime>2020-08-03T09:12:44Z</CreationTime>
        <Description></Description>
        <ObjectPath>http://example.com/bcd.jpg</ObjectPath>
        <ObjectType>file</ObjectType>
        <Process>99.37%</Process>
        <Status>Refreshing</Status>
        <TaskId>23456789</TaskId>
  </Tasks>
  <TotalCount>2</TotalCount>
</DescribeRefreshTaskByIdResponse>
```

`JSON` format

```
{
    "RequestId": "E0C2EF95-B1EC-4C93-855E-2059A7DA2B7B",
    "Tasks": [
        {
            "CreationTime": "2020-08-03T08:54:23Z",
            "Description": "",
            "ObjectPath": "http://example.com/abc.jpg",
            "ObjectType": "file",
            "Process": "100%",
            "Status": "Complete",
            "TaskId": "12345678"
        },
        {
            "CreationTime": "2020-08-03T09:12:44Z",
            "Description": "",
            "ObjectPath": "http://example.com/bcd.jpg",
            "ObjectType": "file",
            "Process": "99.37%",
            "Status": "Refreshing",
            "TaskId": "23456789"
        }
    ],
    "TotalCount": 2
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

