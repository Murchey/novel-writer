# 小说写手多智能体系统

## 系统概述
本系统是一个基于多智能体协作的小说创作平台，通过四个专业智能体的协同工作，完成从创意到成稿的完整创作流程。

## 智能体架构

### 1. 灵感工程师（Inspirer）
- **职责**：创意发散，将用户输入拓展为丰富素材
- **输入**：用户的创意需求（主题、关键词、情感基调等）
- **输出**：灵感报告
- **输出路径**：`WORKSPACE/[书名]/AGENT/Inspirer.md`
- **定义文件**：`AGENTS/Inspirer.MD`
- **核心技能**：`SKILLS/Creative_Divergence.MD`

### 2. 章节内容架构师（Architect）
- **职责**：结构设计，将灵感转化为大纲和细纲
- **输入**：灵感报告
- **输出**：全书大纲 + 章节细纲
- **输出路径**：
  - 全书大纲：`WORKSPACE/[书名]/OUTLINE/outline.md`
  - 章节细纲：`WORKSPACE/[书名]/DETAILED_OUTLINE/chapter_[X].md`
- **定义文件**：`AGENTS/Architect.MD`
- **核心技能**：`SKILLS/Structure_Design.MD`

### 3. 写手（Writer）
- **职责**：内容创作，根据细纲完成章节写作
- **输入**：章节细纲 + 风格要求
- **输出**：章节内容
- **输出路径**：`WORKSPACE/[书名]/CONTENT/chapter_[X].md`
- **定义文件**：`AGENTS/Writer.MD`

### 4. 语言润色师（Polisher）
- **职责**：语言优化，提升内容的文学性和人性化
- **输入**：章节内容初稿
- **输出**：润色后的最终版本
- **输出路径**：`WORKSPACE/[书名]/CONTENT/chapter_[X].md`（覆盖原文件）
- **定义文件**：`AGENTS/Polisher.MD`

## 工作流程

### 完整创作流程
```
用户输入 → 灵感工程师 → 章节内容架构师 → 写手 → 语言润色师 → 最终输出
```

### 详细步骤
1. **创意阶段**
   - 用户提供创意需求
   - 灵感工程师进行创意发散
   - 输出灵感报告

2. **设计阶段**
   - 章节内容架构师接收灵感报告
   - 设计全书大纲
   - 编写章节细纲（长篇按10章分组）

3. **创作阶段**
   - 写手接收章节细纲
   - 阅读风格要求
   - 完成章节内容创作

4. **润色阶段**
   - 语言润色师接收初稿
   - 进行语言优化
   - 输出最终版本

## 小说类型支持

### 短篇小说（1-10章）
- 单一流程完成
- 一次性规划所有章节

### 中篇小说（11-30章）
- 分批次规划
- 每批次10章

### 长篇连载（30章以上）
- 分组管理，每10章为一组
- 进度跟踪，记录在CURRENT.MD
- 断篇续写支持

## 进度管理

### CURRENT.MD文件
- 记录当前创作进度
- 包含最近完成章节信息
- 提供续写指引

### 断篇续写流程
1. 读取CURRENT.MD获取进度
2. 读取最近2章内容
3. 读取下一章细纲
4. 基于上下文续写

## 风格管理

### 风格文件
- `STYLES/Default_Style.MD`：默认风格
- `STYLES/Romance_Style.MD`：言情风格
- `STYLES/Mystery_Style.MD`：悬疑风格
- `STYLES/Historical_Style.MD`：历史风格
- `STYLES/Fantasy_Style.MD`：玄奇风格

### 风格选择
- 根据小说类型选择对应风格
- 可自定义风格要求
- 全书保持风格统一

## 目录结构
```
novel-writer/
├── AGENTS.MD              # 主工作流文件
├── AGENTS/                # 智能体定义
│   ├── Inspirer.MD       # 灵感工程师
│   ├── Architect.MD      # 章节内容架构师
│   ├── Writer.MD         # 写手
│   └── Polisher.MD       # 语言润色师
├── SKILLS/                # 技能定义
│   ├── Creative_Divergence.MD  # 创意发散技能
│   └── Structure_Design.MD     # 结构设计技能
├── STYLES/                # 风格定义
│   ├── Default_Style.MD  # 默认风格
│   ├── Romance_Style.MD  # 言情风格
│   ├── Mystery_Style.MD  # 悬疑风格
│   ├── Historical_Style.MD # 历史风格
│   └── Fantasy_Style.MD  # 玄奇风格
└── WORKSPACE/             # 工作空间
    └── [书名]/            # 项目文件夹
        ├── AGENT/         # 智能体输出
        │   └── Inspirer.md
        ├── CONTENT/       # 章节内容
        │   ├── chapter_1.md
        │   ├── chapter_2.md
        │   └── ...
        ├── OUTLINE/       # 全书大纲
        │   └── outline.md
        ├── DETAILED_OUTLINE/ # 章节细纲
        │   ├── chapter_1.md
        │   ├── chapter_2.md
        │   └── ...
        └── CURRENT_PROCESS/ # 当前进度
            └── current.md
```

## 使用说明

### 开始创作
1. 告诉系统你的创意需求
2. 系统自动启动灵感工程师
3. 按流程完成创作

### 续写作品
1. 告诉系统要续写的作品
2. 系统读取CURRENT.MD
3. 自动完成续写

### 更换风格
1. 指定风格类型
2. 系统应用对应风格
3. 重新润色相关内容

## 注意事项
1. 长篇连载建议按10章分组管理
2. 每完成10章更新进度记录
3. 续写前务必读取最近2章内容
4. 保持全书风格统一
5. 注意情节连贯性和人物一致性