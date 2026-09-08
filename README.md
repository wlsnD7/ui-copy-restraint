# UI Copy Restraint

**English** | [中文](README.zh-CN.md)

An agent skill for removing unnecessary UI explanations while keeping the information people need to act.

Use it when buttons become feature lists, placeholders repeat labels, or every section comes with a tutorial. Supports Chinese and English operational interfaces.

> What would the user lose if this text disappeared?

## Before and after

| Context | Before | After |
| --- | --- | --- |
| An identified project menu | Click here to edit this project | Edit |
| A field already labelled Name | Please enter your name here | Remove the placeholder |
| Track editor entry point | Edit track (anchors/all beats/characters) | Edit track |
| A button that saves and publishes | Save and publish | Keep both actions |
| An enforced upload restriction | PDF only, up to 20 MB | Keep the requirement |

These are contextual decisions, not automatic replacements. Necessary labels, limits, consequences, error recovery, and guidance for hard-to-discover actions stay.

## Install

Requires Node.js and npm/npx. Choose your coding agent interactively:

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint --skill ui-copy-restraint
```

Or select your agent below for a single-command install. The buttons jump to copyable commands; GitHub does not execute an installer when you click them.

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

### Installation scope

The agent-specific commands below install to your user account with `--global` and skip prompts with `--yes`. For a project-only install, run the command from your project folder and remove `--global`. Add `--copy` if you prefer independent files over symlinks.

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

### Multiple agents

```sh
npx --yes skills@latest add wlsnD7/ui-copy-restraint --skill ui-copy-restraint --agent codex claude-code cursor --global --yes
```

Agent identifiers and installation flags follow the [Skills CLI documentation](https://github.com/vercel-labs/skills#install-a-skill). See its [supported agents](https://github.com/vercel-labs/skills#supported-agents) for additional targets. Installation routing does not mean every client has been tested with this skill. If the skill does not appear, reload your agent or start a new session and check its skills list.

### Manual installation

Download this repository and copy `SKILL.md`, `references/`, and `agents/` into a folder named `ui-copy-restraint` in your agent's skills directory. Keep the reference files together with `SKILL.md`. The skill itself has no runtime or external-service dependency; Node.js is used by the installer above.

## Use

Ask your agent to use `ui-copy-restraint`. In Codex, you can invoke it with `$ui-copy-restraint`.

**Prevent** unnecessary copy while building:

```text
Use ui-copy-restraint when building this settings page. Avoid redundant
subtitles and helper text; retain necessary labels and constraints.
```

**Audit** without editing:

```text
Use ui-copy-restraint to audit this interface for unnecessary explanations.
Report supported findings only. Do not modify files.
```

**Fix** within the requested scope:

```text
Use ui-copy-restraint to audit and simplify this page's UI copy.
Make the changes, preserving required information and behavior.
```

The skill infers the mode from your request. It can inspect screenshots, code, or a running interface when your agent has access to them. A screenshot alone cannot establish hidden behavior.

## Chinese and English

The UI keeps its existing language unless translation is requested. Explanations follow the user's preferred conversation language.

```text
Audit this Chinese UI with ui-copy-restraint. Explain in English;
keep the interface text in Chinese.
```

It preserves regional spelling, terminology, capitalization, Simplified/Traditional Chinese conventions, interpolation variables, and plural rules. Bilingual versions should express equivalent actions and consequences without matching word counts. Changes stay within the requested locales.

Browse the [English examples](references/examples.en.md) or [中文案例](references/examples.md).

## What it checks

- Buttons that enumerate destination contents or explain clicking.
- Placeholders and helper text that repeat persistent labels.
- Automatic subtitles and repeated explanations across a page.
- Internal implementation notes that do not inform user decisions.
- Instructions shown persistently when they are only needed in a specific state.

Supported fixes include deleting text nodes, shortening strings, combining repeated information, and cleaning up directly affected spacing and accessibility references. Creating a new help system or redesigning a layout is outside routine copy cleanup.

Best suited to forms, settings, dashboards, admin software, editors, and other operational UI. Narrative, brand messaging, user-authored content, and purposeful teaching are not automatically included.

## Relationship to Impeccable clarify

[Impeccable clarify](https://github.com/pbakaus/impeccable) also addresses redundant and unclear UI text. This skill concentrates on whether supporting copy should exist and when it should appear, including preventing unnecessary additions during generation. It works independently; use clarify when retained text still needs broader clarity work.

It does not detect AI authorship, impose character limits, or promise better results than clarify.

## Validation

Checked with independent Chinese, English, and cross-language scenarios, plus a static HTML editing fixture covering necessary information, shared copy, and accessibility references. These are limited scenario checks, not broad user testing or end-to-end verification in every supported agent.

## Files

```text
SKILL.md                    Shared agent instructions
references/examples.md      Chinese examples
references/examples.en.md   English and cross-language examples
agents/openai.yaml          Codex display metadata
README.md                   English guide
README.zh-CN.md             中文指南
```

## Feedback

[Open an issue](https://github.com/wlsnD7/ui-copy-restraint/issues) with the original copy, surrounding UI context, language, expected result, and what the agent changed. Remove private content before sharing examples.
