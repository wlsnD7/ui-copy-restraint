# UI 文案克制

[English](README.md) | **中文**

帮助 agent 删除界面中多余的解释，同时保留用户完成操作所需的信息。

适合处理按钮里的功能清单、复述标签的输入提示，以及每个区域都附带的操作说明。支持中英文操作型界面。

> 如果删除这段文字，用户会失去什么必要信息？

## 修改示例

| 上下文 | 修改前 | 修改后 |
| --- | --- | --- |
| 已明确对象的项目菜单 | 点击此处编辑当前项目 | 编辑 |
| 已有“名称”标签的输入框 | 请在此输入名称 | 删除 placeholder |
| 轨道编辑入口 | 编辑轨道（锚点/全部拍点/角色） | 编辑轨道 |
| 确实执行保存和发布的按钮 | 保存并发布 | 保留两个动作 |
| 真实的上传限制 | 仅限 PDF，最大 20 MB | 保留限制 |

这些判断依赖上下文，不是固定替换表。必要标签、限制、操作后果、错误恢复信息，以及不易发现操作的指引都应保留。

## 安装

需要 Node.js 和 npm/npx。运行下面的命令，交互选择你的 coding agent：

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint --skill ui-copy-restraint
```

也可以点击对应 agent，复制一条命令安装。按钮跳转到安装命令，点击 GitHub README 按钮本身不会执行安装程序。

[![Codex](https://img.shields.io/badge/Codex-Install-30363d?style=flat-square)](#codex)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Install-30363d?style=flat-square)](#claude-code)
[![Cursor](https://img.shields.io/badge/Cursor-Install-30363d?style=flat-square)](#cursor)
[![Gemini CLI](https://img.shields.io/badge/Gemini%20CLI-Install-30363d?style=flat-square)](#gemini-cli)
[![GitHub Copilot](https://img.shields.io/badge/GitHub%20Copilot-Install-30363d?style=flat-square)](#github-copilot)
[![Windsurf](https://img.shields.io/badge/Windsurf-Install-30363d?style=flat-square)](#windsurf)
[![Cline](https://img.shields.io/badge/Cline-Install-30363d?style=flat-square)](#cline)
[![OpenCode](https://img.shields.io/badge/OpenCode-Install-30363d?style=flat-square)](#opencode)
[![Antigravity](https://img.shields.io/badge/Antigravity-Install-30363d?style=flat-square)](#antigravity)
[![Trae](https://img.shields.io/badge/Trae-Install-30363d?style=flat-square)](#trae)
[![Trae CN](https://img.shields.io/badge/Trae%20CN-Install-30363d?style=flat-square)](#trae-cn)
[![Kimi Code CLI](https://img.shields.io/badge/Kimi%20Code%20CLI-Install-30363d?style=flat-square)](#kimi-code-cli)
[![Qwen Code](https://img.shields.io/badge/Qwen%20Code-Install-30363d?style=flat-square)](#qwen-code)

### 安装范围

以下各 agent 的命令通过 `--global` 安装到用户级目录，使用 `--yes` 跳过选择提示。只想在当前项目使用时，在项目目录运行并去掉 `--global`。如需复制文件而非创建符号链接，可添加 `--copy`。

<a id="codex"></a>

### Codex

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint --skill ui-copy-restraint --agent codex --global --yes
```

<a id="claude-code"></a>

### Claude Code

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint --skill ui-copy-restraint --agent claude-code --global --yes
```

<a id="cursor"></a>

### Cursor

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint --skill ui-copy-restraint --agent cursor --global --yes
```

<a id="gemini-cli"></a>

### Gemini CLI

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint --skill ui-copy-restraint --agent gemini-cli --global --yes
```

<a id="github-copilot"></a>

### GitHub Copilot

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint --skill ui-copy-restraint --agent github-copilot --global --yes
```

<a id="windsurf"></a>

### Windsurf

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint --skill ui-copy-restraint --agent windsurf --global --yes
```

<a id="cline"></a>

### Cline

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint --skill ui-copy-restraint --agent cline --global --yes
```

<a id="opencode"></a>

### OpenCode

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint --skill ui-copy-restraint --agent opencode --global --yes
```

<a id="antigravity"></a>

### Antigravity

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint --skill ui-copy-restraint --agent antigravity --global --yes
```

<a id="trae"></a>

### Trae

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint --skill ui-copy-restraint --agent trae --global --yes
```

<a id="trae-cn"></a>

### Trae CN

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint --skill ui-copy-restraint --agent trae-cn --global --yes
```

<a id="kimi-code-cli"></a>

### Kimi Code CLI

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint --skill ui-copy-restraint --agent kimi-code-cli --global --yes
```

<a id="qwen-code"></a>

### Qwen Code

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint --skill ui-copy-restraint --agent qwen-code --global --yes
```

### 同时安装到多个 agent

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint --skill ui-copy-restraint --agent codex claude-code cursor --global --yes
```

Agent 标识和参数依据 [Skills CLI 官方说明](https://github.com/vercel-labs/skills#install-a-skill)。更多工具见其[支持列表](https://github.com/vercel-labs/skills#supported-agents)。安装器支持路由到这些工具，不代表本技能已在所有客户端完成实测。如果安装后没有出现，请重新加载 agent 或开启新会话，并检查其技能列表。

### 手动安装

下载仓库，将 `SKILL.md`、`references/` 和 `agents/` 放进目标 agent 技能目录下的 `ui-copy-restraint` 文件夹。保留入口与引用文件的相对位置。技能本身不需要运行时或外部服务；上面的安装器才需要 Node.js。

## 使用

让 agent 使用 `ui-copy-restraint` 即可。在 Codex 中可以用 `$ui-copy-restraint` 指定调用。

**预防**生成多余文案：

```text
做这个设置页时使用 ui-copy-restraint，避免重复的副标题和辅助说明，
保留必要标签与输入限制。
```

**审查**而不修改：

```text
用 ui-copy-restraint 审查这个界面的多余解释，只列出有依据的问题，
不要修改文件。
```

**审查并修复**：

```text
用 ui-copy-restraint 审查并精简这个页面的文案，直接修改，
保留必要信息和原有功能行为。
```

技能根据请求判断方式。在 agent 有相应访问能力时，可结合截图、源码或运行中的界面检查；仅凭截图不能认定隐藏功能的真实行为。

## 中英文支持

默认保持界面现有语言，审查说明使用用户偏好的对话语言。

```text
用 ui-copy-restraint 审查这个英文界面。用中文解释，
改后的 UI 文案仍保持英文。
```

保留地区拼写、术语、大小写、简繁体、动态变量和复数规则。双语版本保持动作和后果等价，不要求长度一致。修改范围限定在用户请求的语言版本。

参阅[中文案例](references/examples.md)或 [English examples](references/examples.en.md)。

## 审查重点

- 按钮中枚举进入后可编辑的内容，或解释“如何点击”。
- Placeholder 和辅助提示复述已有标签。
- 自动添加的副标题，以及整页不同位置的重复说明。
- 对用户决策没有帮助的内部实现说明。
- 只在特定状态下需要、却始终常驻的操作指引。

可以删除多余文字节点、缩短字符串、合并重复信息，并清理直接受影响的间距和无障碍引用。新建帮助系统或重做布局不属于常规文案清理。

主要适用于表单、设置页、数据看板、后台、编辑器等操作型 UI。叙事内容、品牌文案、用户正文和明确的教学内容不会自动纳入。

## 与 Impeccable clarify 的关系

[Impeccable clarify](https://github.com/pbakaus/impeccable) 同样处理冗余和不清晰的界面文案。本技能更集中于辅助文字是否需要存在、应当何时出现，以及在生成阶段预防多余说明。可独立使用；保留下来的文案仍需要改善清晰度时，可配合 clarify。

本技能不检测 AI 作者身份、不设字数硬限制，也不承诺效果优于 clarify。

## 验证情况

已进行独立中文、英文和跨语言情境测试，并使用静态 HTML 修改材料检查必要信息、共享文案和无障碍引用。这些是有限场景验证，不是广泛用户测试，也不是每个支持 agent 的端到端实测。

## 文件结构

```text
SKILL.md                    共享 agent 指令
references/examples.md      中文案例
references/examples.en.md   英文及跨语言案例
agents/openai.yaml          Codex 展示信息
README.md                   English guide
README.zh-CN.md             中文指南
```

## 反馈

欢迎[提交 issue](https://github.com/wlsnD7/ui-copy-restraint/issues)，附上原文、周围界面上下文、语言、期望结果和 agent 的实际修改。分享前请移除私密内容。
