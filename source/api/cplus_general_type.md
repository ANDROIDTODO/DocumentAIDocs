## 通用类型

**#include [<sdk_document_ai_common.h>]()**

| **接口名称** | **功能** |
| ---- | :--- |
| [da_result_t](#api_general_da_result_t) | 返回结果 |
| [da_pixel_format_e](#api_general_da_pixel_format_e) | 图片像素格式类型 |
| [da_image_t](#api_general_da_image_t) | 图片格式 |
| [da_handle_t](#api_general_da_handle_t) | 模型句柄 |
| [da_pointf_t](#api_general_da_pointf_t) | 二维float类型坐标 |
| [da_point_t](#api_general_da_point_t) | 二维int类型坐标 |
| [da_rect_t](#api_general_da_rect_t) | 矩形框 |
| [da_object_t](#api_general_da_object_t) | 目标类型 |
| [da_ocr_det_t](#api_general_da_ocr_det_t) | ocr检测结果 |
| [da_ocr_rec_t](#api_general_da_ocr_rec_t) | ocr识别结果 |



<a id = 'api_general_da_result_t'>`da_result_t` </a>


功能：

返回结果

声明：

```c
typedef errcode da_result_t;
```

成员：

| 定义                            | **错误码** | **描述**           |
| ------------------------------- | ---------- | ------------------ |
| E_DA_SUCCESS                    | 0          | 正常运行           |
| E_DA_FAIL                       | -1         | 运行失败，内部错误 |
| E_DA_INVALID_ARG                | -2         | 无效参数           |
| E_DA_INVALID_HANDLE             | -3         | 句柄错误           |
| E_DA_FILE_NOT_FOUND             | -4         | 文件不存在         |
| E_DA_LICENSE_MODEL_MISMATCH | -5         | 序列号和模型不匹配  |
| E_DA_INVALID_MODEL_FORMAT       | -6         | 不合法的模型格式   |
| E_DA_INVALID_LICENSE            | -7         | license不合法      |
| E_DA_MODEL_EXPIRE               | -8         | 模型过期           |
| E_DA_SDK_EXPIRE                 | -9         | SDK过期            |
| E_DA_LICENSE_EXPIRE             | -10        | 序列号过期                       |
| E_DA_LICENSE_UNINITIALIZED      | -11        | 调用接口时未调用初始化序列号接口 |
| E_DA_MODEL_PLATFORM_UNSUPPORTED | -12 | 模型不支持该平台 |
| E_DA_IMAGE_DATA_EMPTY | -13 | 输入的图片不存在或者为空 |
| E_DA_IMAGE_W_H_ERROR | -14 | 输入的图片宽高错误 |
| E_DA_IMAGE_UNSUPPORTED_FORMAT | -15 | 不支持的图片格式 |
| E_DA_SDK_MODEL_MISMATCH | -16 | SDK不支持该模型 |
| E_DA_MISSING_ARG | -17 | 缺少参数 |
| E_DA_UNSUPPORTED_API | -18 | 当前SDK或者模型不支持的API接口 |
| E_DA_LICENSE_PLATFORM_UNSUPPORTED | -19 | license不支持当前的SDK |

<a id = 'api_general_da_pixel_format_e'>`da_pixel_format_e` </a>

功能：

图片像素格式类型，用于指定<a id = 'api_general_da_image_t'>`da_image_t` </a>图片的像素格式

声明：

```c
typedef enum da_pixel_format{
    UNKNOWN = 0,
    DA_PIX_FMT_GRAY8,
    DA_PIX_FMT_BGR565,
    DA_PIX_FMT_BGR888,
    DA_PIX_FMT_BGRA8888,
} da_pixel_format_e;
```

成员：

| 定义                | **描述**                           |
| ------------------- | ---------------------------------- |
| UNKNOWN             | 未知类型                           |
| DA_PIX_FMT_GRAY8    | 单通道 8bit 灰度像素               |
| DA_PIX_FMT_BGR565   | RGB565彩色模式, 一个像素占两个字节 |
| DA_PIX_FMT_BGR888   | 3 通道 24bit BGR 像素              |
| DA_PIX_FMT_BGRA8888 | 4 通道 32bit BGRA 像素             |


<a id = 'api_general_da_image_t'>`da_image_t` </a>


功能：

图片格式，适用于SDK中所有需要传入图片的接口

声明：

```c
typedef struct da_image{
    void *data;
    da_pixel_format_e pixel_format;
    int width;
    int height;
} da_image_t;
```

成员：

| 定义         | **描述**               |
| ------------ | ---------------------- |
| data         | 图像数据指针           |
| pixel_format | 像素格式               |
| width        | 图像宽度(以像素为单位) |
| height       | 图像高度(以像素为单位) |

<a id = 'api_general_da_handle_t'>`da_handle_t` </a>

功能：

句柄指针

声明：

```c
typedef void *da_handle_t;
```



<a id = 'api_general_da_pointf_t'>`da_pointf_t` </a>

功能：

float 类型描述点定义

声明：

```c
typedef struct da_pointf{
    float x;
    float y;
} da_pointf_t;
```

成员：

| 定义 | **描述**                   |
| ---- | -------------------------- |
| x    | 点的水平方向坐标，为浮点数 |
| y    | 点的垂直方向坐标，为浮点数 |
|      |                            |


<a id = 'api_general_da_point_t'>`da_point_t` </a>

功能：

int 类型描述点定义

声明：

```c
typedef struct da_point{
    int x;
    int y;
} da_point_t;
```

成员：

| 定义 | **描述**                 |
| ---- | ------------------------ |
| x    | 点的水平方向坐标，为整数 |
| y    | 点的垂直方向坐标，为整数 |
|      |                          |


<a id = 'api_general_da_rect_t'>`da_rect_t` </a>

功能：

图像矩形框定义

声明：

```c
typedef struct da_rect{
    int left;
    int top;
    int right;
    int bottom;
} da_rect_t;
```

成员：

| 定义   | **描述**         |
| ------ | ---------------- |
| left   | 矩形最左边的坐标 |
| top    | 矩形最上边的坐标 |
| right  | 矩形最右边的坐标 |
| bottom | 矩形最下边的坐标 |
|        |                  |

<a id = 'api_general_da_object_t'>`da_object_t` </a>

功能：

枚举目标类型

声明：

```c
typedef enum da_object{
    DA_OT_FIGURE = 1,
    DA_OT_TABLE,
    DA_OT_SEAL,
    DA_OT_TEXT,
    DA_OT_FONT,
    DA_OT_UNKNOWN
} da_object_t;
```

成员：

| 定义          | **描述**                           |
| ------------- | ---------------------------------- |
| DA_OT_FIGURE  | 未知类型                           |
| DA_OT_TABLE   | 表格类型                           |
| DA_OT_SEAL    | RGB565彩色模式, 一个像素占两个字节 |
| DA_OT_TEXT    | 文字类型                           |
| DA_OT_FONT    | 4 通道 32bit BGRA 像素             |
| DA_OT_UNKNOWN | 无                                 |


<a id = 'api_general_da_ocr_det_t'>`da_ocr_det_t` </a>

功能：

ocr检测的单个结果，以矩形框表示

声明：

```c
typedef struct da_ocr_det : public da_handle_result{
    int bbox[8] = {0};
} da_ocr_det_t;
```

成员：

| 定义 | **描述**                                              |
| ---- | ----------------------------------------------------- |
| bbox | 文字所在原图的位置 （左上角，右上角，右下角，左下角） |
|      |                                                       |


<a id = 'api_general_da_ocr_rec_t'>`da_ocr_rec_t` </a>

功能：

ocr识别的单个结果，以识别的文字和置信度表示

声明：

```c
typedef struct da_ocr_rec : public da_handle_result{
    char text[256];
    float confidence;
} da_ocr_rec_t;
```

成员：

| 定义       | **描述**                                    |
| ---------- | ------------------------------------------- |
| text       | 识别的文字                                  |
| confidence | 识别的置信度，范围[0,1]，值越大，置信度越高 |
|            |                                             |



