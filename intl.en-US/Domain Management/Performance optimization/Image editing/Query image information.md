# Query image information

This topic describes how to query image information and provides examples.

## Parameters

Set the action to `info`.

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

## Examples

```
image_process=info
```

