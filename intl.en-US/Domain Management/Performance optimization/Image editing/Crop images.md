# Crop images

Alibaba Cloud Content Delivery Network \(CDN\) allows you to crop images based on a specified size. This topic describes how to crop images and provides examples.

**Note:** Image editing is a paid service. It is currently free of charge until further notice.

## Parameters

Set the action to `crop`.

The following table describes the parameters.

**Note:** If one of the preceding parameters is set to a negative value, the image remains in its original size.

|Parameter|Description|Valid value|
|---------|-----------|-----------|
|w|The width of the cropped area.|The default value is 0. The total pixels of the cropped area cannot exceed 16,777,216 pixels.|
|h|The height of the cropped area.|
|x|The X coordinate of the cropped area. The default value is the X coordinate of the upper-left corner of the image.|
|y|The Y coordinate of the cropped area. The default value is the Y coordinate of the upper-left corner of the image.|
|g|The position of the area to be cropped in a 3 by 3 grid. The image is located in a 3 by 3 grid, which has 9 tiles. Each tile is positioned by its upper-left corner.|-   nw: the upper-left tile
-   north: the upper-center tile
-   ne: the upper-right tile
-   west: the center-left tile
-   center: the center tile
-   east: the center-right tile
-   sw: the lower-left tile
-   south: the lower-center tile
-   se: the lower-right tile

For more information, see the following figure that shows the position of each tile in a 3 by 3 grid.|

The following figure shows the position of each tile in a 3 by 3 grid.

![Crop images](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9230397061/p185134.png)

## Examples

The following table describes how to crop images.

|Feature|Description|Example|
|-------|-----------|-------|
|Cropping in a circle shape|You can specify the radius of a circle to crop an image. The radius can be at most half the length of the shorter side of the base image.|```
image_process=circle,200
``` |
|Cropping in a 3 by 3 grid|An image can be represented by a 3 by 3 grid. You can specify the position of the tile in the grid that you want to crop.|```
image_process=crop,w_200,h_200,g_se
``` |
|Cropping based on an X and Y coordinate|You can specify the X coordinate, y coordinate, width, and height to crop an image. The X and Y coordinate represents the lower-left corner of the cropped area. The width and height specify the size of the cropped area.|```
image_process=crop,x_10,y_10,w_400,h_200
``` |
|Centered cropping|You can specify the width and height to crop equally on all four sides at a time.|```
image_process=crop,mid,w_400,h_200
``` |

