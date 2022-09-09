## 模型介绍

DocumentAI中通常会用到一下模型，下面试对模型的简单介绍。

- ocr
  - 文字检测模型，一般命名为DA_Ocr_Detection_xxxxx.model，可得到文字的坐标。在OCR功能模块中使用
  - 文字识别模型，一般命名为DA_Ocr_Recgnization_xxxxx.model，可得到文字的信息。一般情况下，和文字检测模型联级使用，对检测到的文字坐标做文字识别。
- detection
  - 