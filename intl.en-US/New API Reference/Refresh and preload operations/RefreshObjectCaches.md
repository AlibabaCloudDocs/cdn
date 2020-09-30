# RefreshObjectCaches

Refreshes files on Content Delivery Network \(CDN\) nodes. Alibaba Cloud CDN allows you to refresh content from multiple URLs at a time.

**When you call this operation, note that:**

-   Alibaba Cloud CDN supports POST requests in which parameters are sent as a form.
-   You can call the **RefreshObjectCaches** operation to refresh content and call the **PushObjectCache** operation to prefecth content.
-   You can refresh content from a maximum of 2,000 URLs and 100 directories each day.
-   You can specify a maximum of 1,000 URLs in each refresh request.
-   The maximum number of times that each user can call this operation per second is 50.

**Note:** For more information about how to use scripts to automatically refresh or prefetch content, see [Scripts for refresh and prefetch tasks](~~151829~~).


## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=RefreshObjectCaches&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|RefreshObjectCaches|The operation that you want to perform. Set the value to **RefreshObjectCaches**. |
|ObjectPath|String|Yes|abc.com/image/1.png\\nabc.com/image/2.png|The URLs from which content is refreshed. Format: **Accelerated domain name/paths or directories of files to be refreshed**.

 Separate multiple URLs with line feed characters \(\\n\) or a pair of carriage return and line feed characters \(\\r\\n\). |
|ObjectType|String|No|File|The type of content to be refreshed. Valid values:

 -   **File**: files with the specified URLs. This is the default value.
-   **Directory**: the files under the specified directories. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RefreshTaskId|String|704222904|The IDs of the refresh tasks. If multiple tasks are returned, the IDs are separated with commas \(,\). |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request. |

## Examples

Sample requests

```
https://cdn.aliyuncs.com?&Action=RefreshObjectCaches
&ObjectPath=abc.com/image/1.png\nabc.com/image/2.png
&ObjectType=File
&<Common request parameters>
```

Sample success responses

`XML` format

```
<RefreshObjectCaches>	
  <RefreshTaskId>704222904</RefreshTaskId>
	  <RequestId>D61E4801-EAFF-4A63-AAE1-FBF6CE1CFD1C</RequestId>
</RefreshObjectCaches>
```

`JSON` format

```
{
"RefreshTaskId":"704222904",
"RequestId":"D61E4801-EAFF-4A63-AAE1-FBF6CE1CFD1C"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

