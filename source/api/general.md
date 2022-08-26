## 通用类型

| **接口名称** | **功能** |
| ---- | :--- |
| [da_result_t](#general_da_result_t) | 返回结果 |
| da_pixel_format_e | 图片像素格式类型 |
| da_image_t | 图片格式 |
| da_handle_t | 模型句柄 |
| da_pointf_t | 二维float类型坐标 |
| da_point_t | 二维int类型坐标 |
| da_rect_t | 矩形框 |
| da_object_t | 目标类型 |
| da_ocr_rec_t | ocr检测结果 |
| da_ocr_rec_t | ocr识别结果 |

da

d

d

d

d

d

d

d

d



d

d

d

d

d

d

d

d

d

d

d

d

d

d

d

d

d

d

d

<a id = 'general_da_result_t'>`da_result_t` </a>

功能：返回结果

声明：

```c
typedef errcode da_result_t;
```







## sdk_add_license

 \#include &lt;[sdk_document_ai_api.h](https://github.com/PaddlePaddle/Paddle-Lite/tree/develop/lite/api/paddle_api.h)&gt;

```c++
da_result_t sdk_add_license(const char* license);
```

设置license，根据