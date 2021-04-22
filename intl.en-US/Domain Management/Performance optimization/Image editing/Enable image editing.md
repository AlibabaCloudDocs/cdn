# Enable image editing

The image editing feature is available to apps and websites whose services use images. You must enable image editing before you can use it. This topic describes how to edit images. You can set parameters to resize, crop, and rotate images based on business requirements.

## Enable image editing

**Note:** Image editing is a paid service. It is currently free of charge until further notice.

1.  Log on to the [Alibaba Cloud CDN console](https://cdn.console.aliyun.com).

2.  In the left-side navigation pane, click **Domain Names**.

3.  On the **Domain Names** page, find the domain name that you want to manage and click **Manage** in the Actions column of the domain name.

4.  In the management pane of the domain name, click **Optimization**.

5.  In the **Image Editing** section, turn on **Image Editing**.

6.  In the Image Editing dialog box, follow the instructions to set the parameters.

    ![Enable image editing](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4140738161/p255870.png)

    |Parameter|Description|
    |---------|-----------|
    |**Supported Image Formats**|Select the formats of images that you want to edit. Supported formats are JPEG, PNG, WebP, BMP, GIF, TIFF, and JPEG 2000.|
    |**Automatic Conversion to WebP**|Turn on **Automatic Conversion to WebP** based on your business requirements. After you turn on **Automatic Conversion to WebP**, images in other formats are automatically converted to the WebP format. **Note:** After you enable automatic conversion to WebP, the cache hit ratio decreases. It automatically increases after a short period of time. Do not enable this feature during peak hours. |
    |**Automatic Rotation**|Turn on **Automatic Rotation** based on your business requirements. After you turn on **Automatic Rotation**, images are automatically rotated to a proper orientation. Only images that carry the orientation parameter are rotated. **Note:** After you enable automatic conversion to WebP, the cache hit ratio decreases. It automatically increases after a short period of time. Do not enable this feature during peak hours. |
    |**Automatic Compression**|Automatic compression supports only the JPEG and WebP formats. It compresses images without changing the width, height, or format of the images. Therefore, automatic compression can reduce the amount of data transfer. **Automatic Compression** is enabled by default. You can enable or disable automatic compression based on your business requirements. If you set Automatic Compression to 90%, the quality of images is changed to 90% of the original quality.

    -   100%: disables automatic compression.
    -   Values other than 100%: enables automatic compression. |

7.  Click **OK**.

    After you enable image editing, you must set actions and parameters for editing images.


## Configure image editing

**Usage notes**

Alibaba Cloud Content Delivery Network \(CDN\) allows you to edit images on CDN nodes. You must set parameters to specify how you want to edit images. You must pass one or more actions such as `crop` and `rotate` to the `image_process` object to specify how you want to edit images. Separate multiple actions with forward slashes \(/\). Alibaba Cloud CDN edits images in order of actions. For example, `image_process=resize,w_200/rotate,90` specifies that Alibaba Cloud CDN resizes images to a width of 200 pixels, and rotates images 90° clockwise.

-   Format: `image_process=action1,param_value1/action2,param_value2`.
-   Example: `image_process=resize,l_200/quality,q_90/format,webp`.

**Add parameters to the URL of an image**

You can add image editing parameters to the end of the URL of an image.

-   Format: `http://example.com/example.jpg?image_process=action,param_value`
    -   `example.com`: the domain name accelerated by Alibaba Cloud CDN.
    -   `example.jpg`: the name of the image.
    -   `image_process`: the object to which you can pass image editing parameters.
    -   `action, param_value`: the action, parameter, and value that specify how the image is edited. For more information, see [Actions](#section_tte_xhn_v81).
-   Example: `http://example.com/example.jpg?image_process=resize,w_200/rotate,90`

## Actions

You can pass one or more actions to image\_process based on your business requirements. The following table describes the actions in different scenarios.

|Feature|Action|Description|
|-------|------|-----------|
|[Convert image formats](/intl.en-US/Domain Management/Performance optimization/Image editing/Convert image formats.md)|format|Converts images to specified formats.|
|[Change image quality](/intl.en-US/Domain Management/Performance optimization/Image editing/Change image quality.md)|quality|Changes the quality of images.|
|[Crop images](/intl.en-US/Domain Management/Performance optimization/Image editing/Crop images.md)|crop|Crops images based on specified sizes.|
|[Resize images](/intl.en-US/Domain Management/Performance optimization/Image editing/Resize images.md)|resize|Resizes images to specified sizes.|
|[Rotate images](/intl.en-US/Domain Management/Performance optimization/Image editing/Rotate images.md)|-   auto-orient: automatically rotates images.
-   rotate: rotates images to specified orientations.

|Automatically rotates images that carry the orientation parameter to a proper orientation or rotates images clockwise based on a specified angle.|
|[Change the color of an image](/intl.en-US/Domain Management/Performance optimization/Image editing/Change the color of an image.md)|-   bright: specifies the brightness of images.
-   contrast: specifies the contrast of images.
-   sharpen: specifies the sharpness of images.

|Adjusts the brightness, contrast, and sharpness of images.|
|[Manage image watermarks](/intl.en-US/Domain Management/Performance optimization/Image editing/Manage image watermarks.md)|watermark|Adds picture or text watermarks to images.|
|[Query image information](/intl.en-US/Domain Management/Performance optimization/Image editing/Query image information.md)|info|Queries image information, including the width, height, format, and quality.|

