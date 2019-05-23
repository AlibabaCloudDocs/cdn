# Notify\_URl setting {#concept_hsf_mz2_xdb .concept}

## Introduction {#section_anb_rz2_xdb .section}

Call back stream-status real-time information and promptly notify users about the video streaming results.

## Attentions {#section_rgd_sz2_xdb .section}

-   Principle: By sending GET requests to the user server through the HTTP interface, the real-time stream status feedback is sent to the users. The user server returns 200 to the return interface.
-   You do not have to identify the URL if normal access is ensured. See the following rules for URL response.
-   In case of access time-out, the URL can be retried. The current time-out duration is 5 seconds, the number of retries is 5, and the interval is 1 second.

## Procedure {#section_bvf_tz2_xdb .section}

Configuration can be performed on the console, and it is optional.

Example:

```
http://1.1.1.1/pub?action=publish&app=xc.cdnpe.com&appname=hello&id=world&ip=42.120.74.183&node=cdnvideocenter010207116011.cm3
```

|Parameter|Value description|
|:--------|:----------------|
|time|unix timestamp|
|usrargs|User streaming parameters|
|action|publish indicates push streaming, and publish\_done indicates completion of push streaming|
|app|Default value is the custom streaming domain name. If no streaming domain name is bound, it is the playback domain name|
|appname|Application name|
|id|Stream name|
|node|The name of the node or machine in the CDN that receives the stream|
|ip|Streaming client's IP|

