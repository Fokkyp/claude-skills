# Claude Skills

一个用于存放可复用 Claude Skills 的仓库。每个 skill 都是独立目录，入口文件为 `SKILL.md`，可按场景直接复用或继续扩展。

## 安装

先安装 Claude Code：

```bash
npm install -g @anthropic-ai/claude-code
```

然后选择以下任一方式安装本仓库中的 skills。

### 方式一：安装到个人技能目录

安装后可在所有项目中使用：

```bash
git clone https://github.com/Fokkyp/claude-skills.git
mkdir -p ~/.claude/skills
cp -R claude-skills/prd-generator ~/.claude/skills/
cp -R claude-skills/competitive-analysis ~/.claude/skills/
```

### 方式二：安装到项目目录

仅在当前项目生效：

```bash
git clone https://github.com/Fokkyp/claude-skills.git
mkdir -p .claude/skills
cp -R claude-skills/prd-generator .claude/skills/
cp -R claude-skills/competitive-analysis .claude/skills/
```

## Included Skills

### `prd-generator`

适用于产品需求文档（PRD）编写与迭代。

功能：
- 通过问答逐步收集产品背景、目标用户、功能需求和非功能需求
- 生成 PRD 大纲、完整 PRD 文档和 Mermaid 流程图
- 支持竞品研究、模块 review 和内容优化

使用示例：

```text
帮我创建一份PRD，产品是一个 AI 会议纪要助手
帮我完善用户痛点这个模块，目标用户是产品经理
基于收集的信息，生成完整的 PRD 文档
```

### `competitive-analysis`

适用于竞品分析、竞品调研和多产品对比。

功能：
- 支持单品拆解与多品对比两种模式
- 先确认分析范围，再进行信息收集与报告撰写
- 支持快速分析和深度分析，并结合常见分析框架输出结构化报告

使用注意事项：
- 建议使用上下文长度 `1M` 以上的模型，例如 `Claude Opus 4.6 [1M]`
- 在 `GPT-5.4 xhigh` 的测试中，任务结束时通常只剩约 `25%` 上下文
- 如果是复杂分析、竞品较多或资料较长，较小上下文模型可能无法完整跑完流程
- 遇到上下文不足时，建议缩小分析范围、减少竞品数量，或拆成多轮执行

使用示例：

```text
帮我分析一下 Notion AI
对比 Cursor、GitHub Copilot 和 Windsurf，做一份竞品分析
分析我们和竞品的差距，重点看 AI 功能和商业模式
```

## How to Use

1. 选择对应的 skill 目录。
2. 阅读其中的 `SKILL.md`，了解触发条件、工作流和输出要求。
3. 在 Claude 中直接用自然语言描述任务，或使用 `/skill-name` 直接调用。

如果某个 skill 包含额外资料，例如 `references/`，这些文件用于补充分析框架、图表规范或采集流程。

例如：

```text
/prd-generator
/competitive-analysis
```

## Repository Structure

```text
.
├── README.md
├── AGENTS.md
├── prd-generator/
│   └── SKILL.md
└── competitive-analysis/
    ├── SKILL.md
    └── references/
```

## Conventions

- 每个 skill 使用单独目录
- 目录名使用 `kebab-case`
- 入口文件统一为 `SKILL.md`

<small>友链：<a href="https://linux.do/">linux.do</a></small>
