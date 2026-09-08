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

需要 Node.js 和 npm/npx。下面的命令通过 `--global` 安装到用户级目录，并用 `--yes` 跳过提示。只想在当前项目使用时，在项目目录运行并去掉 `--global`。如需复制文件而非创建符号链接，可添加 `--copy`。

### Codex

```sh
npx --yes skills@latest add wlsnD7/restraining-ui-text --skill restraining-ui-text --agent codex --global --yes
```

### Claude Code

```sh
npx --yes skills@latest add wlsnD7/restraining-ui-text --skill restraining-ui-text --agent claude-code --global --yes
```

其他 coding agent 用同一条命令，把 `--agent` 换成对应标识即可。参数见 [Skills CLI 官方说明](https://github.com/vercel-labs/skills#install-a-skill)，更多工具见其[支持列表](https://github.com/vercel-labs/skills#supported-agents)。列表里能装，不代表本技能已在该客户端实测。如果安装后没有出现，请重新加载 agent 或开启新会话，并检查技能列表。

手动安装：把 `SKILL.md`、`references/` 和 `agents/` 放到目标 agent 技能目录下的 `restraining-ui-text` 文件夹，并保持相对位置。技能本身不需要运行时或外部服务；上面的安装器才需要 Node.js。

## 使用

让 agent 使用 `restraining-ui-text` 即可。在 Codex 中可以用 `$restraining-ui-text` 指定调用。

技能根据请求判断方式：生成时克制新文案、只报告有依据的问题、或在授权范围内直接修改。在 agent 有相应访问能力时，可结合截图、源码或运行中的界面检查；仅凭截图不能认定隐藏功能的真实行为。

默认保持界面现有语言，审查说明使用用户偏好的对话语言。保留地区拼写、术语、大小写、简繁体、动态变量和复数规则。双语版本保持动作和后果等价，不要求长度一致。修改范围限定在用户请求的语言版本。

## 审查重点

- 按钮中枚举进入后可编辑的内容，或解释“如何点击”。
- Placeholder 和辅助提示复述已有标签。
- 自动添加的副标题，以及整页不同位置的重复说明。
- 对用户决策没有帮助的内部实现说明。
- 只在特定状态下需要、却始终常驻的操作指引。

可以删除多余文字节点、缩短字符串、合并重复信息，并清理直接受影响的间距和无障碍引用。新建帮助系统或重做布局不属于常规文案清理。

主要适用于表单、设置页、数据看板、后台、编辑器等操作型 UI。叙事内容、品牌文案、用户正文和明确的教学内容不会自动纳入。

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
