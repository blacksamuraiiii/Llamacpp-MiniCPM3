# MiniCPM Web 交互界面

基于 LLaMA.cpp 和 MiniCPM 系列模型构建的 Streamlit 网页交互界面

## 项目简介

本项目提供了一个基于 Streamlit 的网页界面，用于与 MiniCPM 系列模型进行交互，包括：
- 文本对话功能（支持 MiniCPM-3 和 Qwen2 模型）
- 图像识别功能（支持 MiniCPM-V-2.6 模型）
- 视频识别功能（实验性支持）

## 功能特点

- 简洁直观的网页界面
- 支持多种 MiniCPM 系列模型
- 可调节的模型参数（温度、top-p、top-k等）
- 实时显示生成耗时

## 环境要求

- Linux (推荐 WSL2) 或 macOS
- Python 3.8+
- 已安装 FFmpeg 和相关开发库

## 安装步骤

### 1. 安装系统依赖
```bash
sudo apt update
sudo apt install ffmpeg pkg-config build-essential make libavformat-dev libavcodec-dev libavutil-dev libswscale-dev
```

### 2. 获取项目代码
```bash
git clone https://github.com/blacksamuraiiii/Llamacpp-MiniCPM3.git
cd Llamacpp-MiniCPM3
```

### 3. 编译 LLaMA.cpp
```bash
cd llama.cpp
sudo make -j8
```

### 4. 获取模型文件

在 `models` 目录下放置量化后的模型文件：
- MiniCPM-3: `ggml-model-Q4_K_M.gguf`
- MiniCPM-V-2.6: `ggml-model-Q4_K_M.gguf` 和 `mmproj-model-f16.gguf`

可以从 Hugging Face 或 ModelScope 下载现成的量化模型。

## 使用方法

### 安装 Python 依赖
```bash
pip install -r requirements.txt
```

### requirements.txt 内容
```
streamlit
llama-cpp-python
numpy
pillow
opencv-python
ffmpeg-python
```

### 启动网页应用
```bash
streamlit run app.py
```

应用启动后，默认会在浏览器中打开交互界面。

## 界面功能

### 文本对话
- 支持 MiniCPM-3 和 Qwen2 模型
- 可调节上下文长度、生成长度等参数

### 图像识别
- 支持上传图片并识别内容
- 可调节识别参数

### 视频识别（实验性）
- 支持上传视频并识别内容

## 效果展示

### 文本对话模式
![对话示例1](https://github.com/user-attachments/assets/ab867096-0eab-44f7-bff6-1d5a9fc74cf5)
![对话示例2](https://github.com/user-attachments/assets/acb7ffc0-8c6e-4a61-a5b7-f884dbcb5290)

### 图像识别模式
![图像识别示例1](https://github.com/user-attachments/assets/ee371e8b-0bb4-4fb8-abeb-68aa9e635ff8)
![图像识别示例2](https://github.com/user-attachments/assets/bfd96352-3a4a-46e6-a7de-a88da791bae3)

## 常见问题

1. 如果遇到模型加载问题，请检查模型路径是否正确
2. 视频识别功能可能较慢且结果不稳定
3. 确保有足够的显存/内存运行模型

## 贡献

欢迎提交 Issue 或 Pull Request 改进本项目。













