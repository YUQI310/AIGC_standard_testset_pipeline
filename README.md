# AIGC 标准测试集构建 Pipeline

> 字节跳动风控合规实习 · 第二阶段产出：公开数据集批量接入、格式标准化、清洗与合规分流

## 目录结构
06_scripts/
├── main.py # 主控脚本（伪代码/框架）
├── config/
│ └── datasets_config.json # 数据集配置示例
├── core/
│ ├── config_loader.py # 配置读取
│ ├── convert_text.py # 文本 → JSONL
│ ├── convert_image.py # 图像 → JPEG（调用 Pillow）
│ ├── convert_video.py # 视频 → MP4（调用 FFmpeg）
│ ├── metadata_builder.py # 元数据生成
│ ├── cleaner.py # 去重、质量过滤
│ └── compliance_router.py # 许可合规分流
├── review/
│ ├── review_sampler.py # 抽样复核清单生成
│ └── review_merger.py # 复核结果回写与统计
└── utils/
├── logger.py
├── file_utils.py
└── ffmpeg_helper.py

 核心产出

- 设计文档：[数据清洗与格式转换自动化脚本.pdf](./数据清洗与格式转换自动化脚本.pdf)
- 详细定义了：
  - 统一格式与字段规则（7.3）
  - 许可合规分流规则（8.5）
  - 目录结构与状态映射（4.3）

 依赖工具（代码实现层面）

| 功能 | 依赖 |
|------|------|
| 文本处理 | Python + json |
| 图像转换 | Pillow |
| 视频转换 | FFmpeg |
| 数据下载 | Hugging Face `datasets` / Kaggle API |
| 日志与统计 | Python logging / pandas |

 ⚠️ 说明

本仓库以设计文档 + 目录结构 + 伪代码为主。  
作为法学背景实习生，主要产出是数据处理规则、合规分流机制和字段设计，代码层面基于开源工具进行工程化调用。

相关文档

- [完整脚本设计文档](./数据清洗与格式转换自动化脚本.pdf)
