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
## 状态

- [ ] 开发中，预计本周五前完成第一版
