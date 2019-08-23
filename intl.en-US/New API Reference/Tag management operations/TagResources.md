# TagResources {#reference_226991 .reference}

You can call the TagResources operation to add a tag to a resource.

## Request parameters {#section_6j6_jy9 .section}

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Action|String |Yes|The operation that you want to perform. Set this parameter to TagResources.|
|ResourceId.N|String |Yes|The ID of the resource to add the tag to. Specify a CDN domain name as the resource ID. Valid values of N: 1 to 50.|
|ResourceType|String|Yes|The resource type. Set this value to DOMAIN.|
|Tag.N.Key|String |Yes|The key of the tag. Valid values of N: 1 to 20.|
|Tag.N.Value|String|No|The value of the tag. Valid values of N: 1 to 20.|

## Examples {#section_xr1_ch1 .section}

Sample request

``` {#codeblock_9er_pet_ij2}
https://cdn.aliyuncs.com/?Action=TagResoruces
&ResourceId. 1=example.com
&ResourceType=DOMAIN
&Tag. 1.Key=env
&Tag. 1.Value=''
&<Common request parameters>
```

Sample success response

`JSON` format

``` {#codeblock_gu6_skx_8b0}
{
"RequestId":"97C68796-EB7F-4D41-9D5B-12B909D76508"
}
```

