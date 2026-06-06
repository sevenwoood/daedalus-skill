---
​---
name: daedalus-skill
version: 1.0.5
description: 对话式产品孵化技能。帮助零基础用户将模糊想法转化为结构化产品需求文档（PRD），包含门槛评估、风险提示、竞品对照、边界定义和工具链推荐。
​---
---

# Daedalus Skill · 代达罗斯

本技能是一个对话式产品孵化引擎。你只需像聊天一样说出你的产品想法，技能会通过结构化提问、风险提示、竞品对照、成本评估和边界定义，帮助你走向清晰的可执行产品方案，并最终生成完整的 **产品需求文档（PRD）**。

## 安装与使用

使用以下命令安装：

```bash
npx skills add sevenwoood/daedalus-skill --skill daedalus-skill
```



或通过 GitHub CLI：

```bash
gh skill install sevenwoood/daedalus-skill daedalus-skill
```



## 核心文件

- `instructions.md`：系统提示词（核心对话逻辑），需作为 System Prompt 植入。
- `rules.md`：判断规则（立项、风险、边界）。
- `flow.md`：对话流程总览。
- `capabilities.md`：能力清单。
- `templates/`：各轮提问与输出模板。
- `examples/`：示例对话。
- `changelog.md`：版本记录。
- `assets/`：图标与 banner。

## 快速开始

将 `instructions.md` 的内容复制到支持自定义 System Prompt 的 AI 平台（如 ChatGPT、Claude、Cursor 等），然后开始对话：

> “我想做一个分享小众好店的 App，周末经常不知道去哪逛……”

技能会引导你完成最多 12 轮对话，并在适当时机输出完整的 PRD。

## 要求

- 推荐模型：GPT-4、Claude-3、Gemini 1.5 Pro 或更高（上下文建议 8K+）。
- 零基础用户也可使用，技能包含降级策略和菜单模式。

## 许可证

MIT © 2026 Daedalus Skill Contributors
