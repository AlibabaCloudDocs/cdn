# Query image information

This topic describes how to query image information and provides examples of how to query image information.

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

