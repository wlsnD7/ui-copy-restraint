# UI Copy Restraint

**English** | [中文](README.zh-CN.md)

An agent skill for removing redundant UI copy: overexplained buttons, repeated hints, and unnecessary implementation details. Supports Chinese and English, preserving the interface language and essential information.

Use it to prevent unnecessary copy during development, audit existing interfaces, or make focused edits. Works independently of Impeccable.

## Install

Requires Node.js and npm/npx.

**Codex**

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint --agent codex --global --yes
```

**Claude Code**

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint --agent claude-code --global --yes
```

**Other agents** — select your agent interactively:

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint
```

Remove `--global` to install only in the current project. More options: [Skills CLI](https://github.com/vercel-labs/skills#install-a-skill).

## Use

Ask your agent to use `ui-copy-restraint` and specify whether to audit or edit. In Codex, invoke it with `$ui-copy-restraint`.

Best suited to forms, settings, editors, and admin interfaces. It preserves necessary labels, constraints, action consequences, and accessibility information; it does not apply word-count limits or detect AI authorship.
