## 通用接口

**#include [<sdk_document_ai_api.h>]()**

| **接口名称** | **功能** |
| ---- | :--- |
| [sdk_add_license](#api_general_sdk_add_license) | 添加license字符串 |
| [sdk_add_license_file](#api_general_sdk_add_license_file) | 添加license文件 |
| [sdk_version](#api_general_sdk_version) | 获取sdk版本号 |
| [sdk_model_version](#api_general_sdk_model_version) | 获取模型版本号 |
| [sdk_image_create](#api_general_sdk_image_create) | 根据图片路径创建图像指针并分配内存 |
| [sdk_image_create_by_buffer](#api_general_da_pointf_t) | 根据图片数据创建图像指针并分配内存 |
| [sdk_image_crop](#api_general_da_point_t) | 图像扣取 |
| [sdk_image_save](#api_general_da_rect_t) | 图像保存 |
| [sdk_image_release](#api_general_da_object_t) | 释放图像数据 |
| [sdk_handle_release](#api_general_da_object_t) | 释放模型句柄 |
| [sdk_handle_common_release](#api_general_da_object_t) | 释放返回的数据结果 |

<a id = 'api_general_sdk_add_license'>`sdk_add_license` </a>

```c++
da_result_t
sdk_add_license(
  const char* license
);
```

设置license。若license不正确，所有非通用的接口都不能正常使用

**示例：**

```c++
da_result_t add_license_result = sdk_add_license("xxxxxxxxxxxx");
if(add_license_result == E_DA_SUCCESS){
  //add license successful.
}else{
  //something went wrong.
}
```

**参数**

| **变量名** | **输入/输出** | **描述**      |
| ---------- | ------------- | ------------- |
| license    | [in]          | License字符串 |

**响应**

正常返回E_DA_SUCCESS，否则返回[错误类型](./cplus_general_type)



<a id = 'api_general_sdk_add_license_file'>`sdk_add_license_file` </a>

```c++
da_result_t
sdk_add_license_file(
  const char* license_path
);
```

设置license文件。若license不正确，所有非通用的接口都不能正常使用

**示例：**

```c++
da_result_t add_license_result = sdk_add_license_file("license file path");
if(add_license_result == E_DA_SUCCESS){
  //add license successful.
}else{
  //something went wrong.
}
```

**参数**

| **变量名**   | **输入/输出** | **描述**        |
| ------------ | ------------- | --------------- |
| license_path | [in]          | License文件路径 |

**响应**

正常返回E_DA_SUCCESS，否则返回[错误类型](./cplus_general_type)



<a id = 'api_general_sdk_version'>`sdk_version` </a>

```c++
da_result_t
sdk_version(
  char* version
);
```

获取SDK版本号

**示例：**

```c++
char version[10];
sdk_version(version);
std::cout << "sdk version :" << std::string(version) << std::endl;
```



**参数**

| **变量名** | **输入/输出** | **描述**    |
| ---------- | ------------- | ----------- |
| version    | [out]         | SDK版本指针 |

**响应**

正常返回E_DA_SUCCESS，否则返回[错误类型](./cplus_general_type)



<a id = 'api_general_sdk_model_version'>`sdk_model_version` </a>

```c++
da_result_t
sdk_model_version(
  const char* model_path,
  char* model_version
);
```

获取模型版本号

**示例：**

```c++
char model_version[128];
da_result_t acquire_model_version_result = sdk_model_version("xxxxxxxxxx.model",model_version);
if (acquire_model_version_result == E_DA_SUCCESS){
  std::cout << "model version:" << std::string(model_version) << std::endl;
}else {
  //something went wrong.
}
```



**参数**

| **变量名**    | **输入/输出** | **描述**     |
| ------------- | ------------- | ------------ |
| model_path    | [in]          | 模型路径     |
| model_version | [out]         | 模型版本指针 |

**响应**

正常返回E_DA_SUCCESS，否则返回[错误类型](./cplus_general_type)



<a id = 'api_general_sdk_image_create'>`sdk_image_create` </a>

```c++
da_result_t
sdk_image_create(
  const char* image_path,
  da_image_t *image
);
```

根据图片路径创建图像指针并分配内存。若不使用，需要[释放]()该指针

**示例：**

```c++
da_image_t image;
da_result_t create_image_result = sdk_image_create("xxxxxxx.png", &image);
if(create_image_result == E_DA_SUCCESS){
  //create image successful
}else {
  //something went wrong.
}
```

**参数**

| **变量名** | **输入/输出** | **描述**             |
| ---------- | ------------- | -------------------- |
| image_path | [in]          | 图片路径             |
| image      | [out]         | 输出图像指针所在地址 |

**响应**

正常返回E_DA_SUCCESS，否则返回[错误类型](./cplus_general_type)