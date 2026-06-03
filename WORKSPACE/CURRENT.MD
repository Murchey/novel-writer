# 当前进度（全局）

## 项目列表
- **暂无项目**：开始创作后会自动创建项目文件夹

## 项目结构说明
每个项目的工作区结构如下：
```
WORKSPACE/
└── [书名]/
    ├── AGENT/         # 智能体输出
    │   └── Inspirer.md
    ├── CONTENT/       # 章节内容（最终版本）
    │   ├── chapter_1.md
    │   └── ...
    ├── OUTLINE/       # 全书大纲
    │   └── outline.md
    ├── DETAILED_OUTLINE/ # 章节细纲
    │   ├── chapter_1.md
    │   └── ...
    └── CURRENT_PROCESS/ # 当前进度
        └── current.md
```

## 使用说明
1. 开始创作新小说时，系统会自动创建 `[书名]/` 目录
2. 每个智能体的输出会保存到对应的目录中
3. 续写时请查看 `[书名]/CURRENT_PROCESS/current.md` 获取进度