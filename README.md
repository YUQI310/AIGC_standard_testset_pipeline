# AIGC_standard_testset_pipeline
第二阶段：公开数据集批量获取与质量验证
## 目录结构
06_scripts/
├── main.py # 主控脚本
├── config/
│ └── datasets_config.json
├── core/
│ ├── config_loader.py
│ ├── convert_text.py
│ ├── convert_image.py
│ ├── convert_video.py
│ ├── metadata_builder.py
│ ├── cleaner.py
│ └── compliance_router.py
├── review/
│ ├── review_sampler.py
│ └── review_merger.py
└── utils/
├── logger.py
├── file_utils.py
└── ffmpeg_helper.py
## 代码组织说明
本仓库目前以**设计文档 + 目录结构 + 伪代码**为主，具体实现依赖以下开源工具和库：

| 功能 | 依赖/来源 | 说明 |
|------|-----------|------|
| 文本转换 | Python + json 库 | 统一转为 JSONL |
| 图像转换 | Pillow (PIL) | PNG/WebP → JPEG |
| 视频转换 | FFmpeg | 统一转为 H.264 / AAC MP4 |
| 数据集下载 | Hugging Face `datasets` / Kaggle API | 原始数据接入 |
| 重复检测 | hashlib / 可选 phash | 去重 |
| 日志与统计 | Python logging / pandas | 统计输出 |

详细设计见同目录下《数据清洗与格式转换自动化脚本.docx》。


