# Query image information

This topic describes how to query image information and provides examples of how to query image information.

**Note:**

-   This feature is in private preview. To participate in the private preview, [submit a ticket](https://workorder-intl.console.aliyun.com/?spm=5176.2020520001.aliyun_topbar.18.dbd44bd3e4f845#/ticket/createIndex).
-   This feature is **free of charge** during the private preview. After it is officially released, it charges fees. For more information, see the product updates.

## Parameters

Set the action to `info`.

Example: `image_process=info`.

The image information is returned in JSON format. The information includes the height, width, format, quality, and orientation of the specified image.

```
{
  "Length":1055089,
  "Width":1920,
  "Height":1080,
  "Quality":100,
  "Format":"JPEG",
  "Orientation":"UNDEFINED"}
```

