# UI 文案克制

[English](README.md) | **中文**

清理 UI 中多余文案的 agent skill：过度解释的按钮、重复提示，以及不必要的内部实现说明。支持中英文，保留界面原有语言和必要信息。

可在开发时预防冗余文案，也可审查或直接精简已有界面。独立使用，不依赖 Impeccable。

## 安装

需要 Node.js 和 npm/npx。

**Codex**

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint --agent codex --global --yes
```

**Claude Code**

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint --agent claude-code --global --yes
```

**其他 agent**：运行后交互选择。

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint
```

去掉 `--global` 可仅安装到当前项目。更多参数见 [Skills CLI](https://github.com/vercel-labs/skills#install-a-skill)。

## 使用

让 agent 使用 `ui-copy-restraint`，并说明只审查还是直接修改。在 Codex 中可用 `$ui-copy-restraint` 调用。

主要适用于表单、设置页、编辑器和后台。保留必要标签、输入限制、操作后果和无障碍信息；不设字数硬限制，也不判断文案是否由 AI 创作。
