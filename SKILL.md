# skill.md

```yaml
name: Daedalus
version: 1.0.5
description: 代达罗斯（Daedalus）——对话式产品孵化技能。帮助零基础用户将模糊想法转化为结构化产品需求文档（PRD），并提供门槛评估、风险提示、竞品对照、边界定义和工具链推荐。
author: Product Coach Community
tags:
  - product-management
  - ideation
  - mvp
  - prd
  - no-code
  - startup
skill_type: conversation
compatible_models:
  - GPT-4
  - GPT-4 Turbo
  - Claude-3 Opus
  - Claude-3.5 Sonnet
  - Gemini 1.5 Pro
  - DeepSeek-V3
context_requirements:
  min_tokens: 4096
  recommended_tokens: 8192
license: MIT
```

------

## 概述

代达罗斯（Daedalus）是一个对话式产品孵化技能。你只需像聊天一样说出你的产品想法（哪怕很模糊），代达罗斯会通过结构化提问、风险提示、竞品对照、成本评估和边界定义，帮助你走向清晰的可执行产品方案，并最终生成一份完整的 **产品需求文档（PRD）**。

> 名称源自希腊神话中的伟大建筑师、发明家代达罗斯（Daedalus），他建造了迷宫。本技能意为：你只需动嘴（提出需求），技能自动帮你构建出复杂的“产品迷宫”。

------

## 文件结构

本技能包含以下文件（位于 `daedalus-skill/` 目录下）：

```text
daedalus-skill/
├── skill.md                    # 本文件（技能元信息与入口）
├── README.md                   # 详细使用说明与安装指南
├── instructions.md             # 系统指令（System Prompt）
├── flow.md                     # 对话流程总览
├── rules.md                    # 判断规则（立项、风险、边界）
├── capabilities.md             # 能力清单
├── templates/                  # 各轮提问与输出模板
│   ├── round1_question.md
│   ├── round2_question.md
│   ├── round3_triggers.md
│   ├── risk_checklist.md
│   ├── boundary_template.md
│   ├── final_prd_template.md
│   └── toolchain_recommend.md
├── examples/
│   └── sample_conversation.md  # 示例对话
├── changelog.md                # 版本记录
└── assets/
    └── daedalus-skill_banner.svg  # 宣传图
```



------

## 快速开始

### 1. 安装

- **复制系统指令**：将 `instructions.md` 的内容作为 System Prompt 粘贴到支持自定义指令的 AI 对话平台（如 ChatGPT、Claude、Coze、Dify）。
- **（可选）上传规则文件**：部分平台允许上传额外文件，可将 `rules.md`、`flow.md` 等作为知识库附件，提升遵循度。
- **配置 Banner**（可选）：将 `assets/daedalus-skill_banner.svg` 用作技能图标。

### 2. 使用

- 直接对 AI 说出你的产品想法，例如：“我想做一个分享小众好店的App。”
- 代达罗斯会开始引导对话。你只需凭直觉回答每轮不超过3个问题。
- 当对话到达第8轮或你觉得想法成熟时，回复“开始做”，即可获得完整的 PRD 文档。

### 3. 保存进度

- 回复“保存退出”，代达罗斯会输出当前进度的快照（Markdown格式）。下次新建对话时，将快照粘贴并说“继续之前的项目”，即可恢复。

------

## 核心能力速览

| 能力                    | 说明                                             |
| :---------------------- | :----------------------------------------------- |
| 承接模糊想法            | 用感性、开放的问题帮助用户具象化                 |
| 每轮反馈（亮点+留意点） | 肯定有价值的部分，温和提示风险                   |
| 项目门槛评估            | 列出技术、资金、时间成本，提供轻量/中等/完整路径 |
| 竞品参考推荐            | 基于关键词匹配内置竞品库                         |
| 合规+安全风险提示       | 分法律/伦理和技术/产品设计两类                   |
| 立项判断                | 后台评估方向清晰度，并告知用户                   |
| 边界定义                | 强制V1功能≤3个，防止范围蔓延                     |
| 结构化PRD输出           | 9章节Markdown文档，可直接交给AI编程工具          |
| 工具链推荐              | 分专业工具和零代码工具，附带白话解释             |
| 进度保存与恢复          | 支持中断后继续                                   |
| 降级策略                | 用户回复过短时切换为二选一菜单                   |

------

## 使用要求

- **推荐模型**：GPT-4、Claude-3、Gemini 1.5 Pro 或更高版本（上下文建议8K以上）。
- **轻量模型**：可能会影响引导深度，技能会自动降级为菜单模式。
- **网络**：如需调用地图API或外部知识库，需要网络（但核心对话功能离线可用）。

------

## 常见问题（FAQ）

**Q：我不会编程，能用这个技能吗？**
A：完全可以。技能专门为零基础设计，最终输出的PRD会包含零代码工具链推荐（Canva、微信小程序云开发、[v0.dev](https://v0.dev/)等）。

**Q：对话需要多久才能拿到PRD？**
A：最少3轮即可获得立项判断，通常8-12轮可输出完整PRD。每轮回答只需1-3分钟。

**Q：技能会帮我写代码吗？**
A：不会写代码，但会推荐最适合你的代码生成工具（如[v0.dev](https://v0.dev/)），并告诉你如何把PRD丢给它们。

**Q：风险提示会阻止我的想法吗？**
A：不会。技能只告知风险，不禁止任何方向。你可以选择忽略风险（但会在PRD中记录已告知）。

**Q：可以商业化使用本技能产出的内容吗？**
A：可以。本技能采用MIT许可证，产出的PRD版权归用户所有。

------

## 许可证

MIT License © 2026 Product Coach Community

------

**本文件 `skill.md` 是代达罗斯技能的入口文件。请确保所有文件按照上述结构放置在 `daedalus-skill/` 目录下。**

