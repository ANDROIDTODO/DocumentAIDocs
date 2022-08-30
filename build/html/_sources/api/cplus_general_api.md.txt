## 通用接口

**#include [<sdk_document_ai_api.h>]()**

| **接口名称** | **功能** |
| ---- | :--- |
| [sdk_add_license](#api_general_da_result_t) | 添加license |
| [sdk_version](#api_general_da_pixel_format_e) | 获取sdk版本号 |
| [sdk_model_version](#api_general_da_image_t) | 获取模型版本号 |
| [sdk_image_create](#api_general_da_handle_t) | 根据图片路径创建图像指针并分配内存 |
| [sdk_image_create_by_buffer](#api_general_da_pointf_t) | 根据图片数据创建图像指针并分配内存 |
| [sdk_image_crop](#api_general_da_point_t) | 图像扣取 |
| [sdk_image_save](#api_general_da_rect_t) | 图像保存 |
| [sdk_image_release](#api_general_da_object_t) | 释放图像数据 |
| [sdk_handle_release](#api_general_da_object_t) | 释放模型句柄 |
| [sdk_handle_common_release](#api_general_da_object_t) | 释放返回的数据 |

`sdk_add_license`

```c++
da_result_t
sdk_add_license(
  const char* license
);
```

设置license。若license不正确，所有非通用的接口都不能正常使用

**参数**

| **变量名** | **输入/输出** | **描述**      |
| ---------- | ------------- | ------------- |
| license    | [in]          | License字符串 |

**响应**

正常返回E_DA_SUCCESS，否则返回[错误类型](./cplus_general_type)



`sdk_version`

```c++
da_result_t
sdk_version(
  char* version
);
```

获取SDK版本号

**参数**

| **变量名** | **输入/输出** | **描述**    |
| ---------- | ------------- | ----------- |
| version    | [out]         | SDK版本指针 |

**响应**

正常返回E_DA_SUCCESS，否则返回错误类型



`sdk_model_version`

```c++
da_result_t
sdk_model_version(
  const char* model_path,
  char* model_version
);
```

获取模型版本号

**参数**

| **变量名**    | **输入/输出** | **描述**     |
| ------------- | ------------- | ------------ |
| model_path    | [in]          | 模型路径     |
| model_version | [out]         | 模型版本指针 |

**响应**

正常返回E_DA_SUCCESS，否则返回错误类型