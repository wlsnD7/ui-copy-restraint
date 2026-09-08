# Restraining UI Text

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

Requires Node.js and npm/npx. The commands below install to your user account (`--global`) and skip prompts (`--yes`). For a project-only install, run from the project folder and drop `--global`. Add `--copy` if you want files instead of symlinks.

### Codex

```sh
npx --yes skills@latest add wlsnD7/restraining-ui-text --skill restraining-ui-text --agent codex --global --yes
```

### Claude Code

```sh
npx --yes skills@latest add wlsnD7/restraining-ui-text --skill restraining-ui-text --agent claude-code --global --yes
```

Other coding agents use the same command with a different `--agent` value. See the [Skills CLI documentation](https://github.com/vercel-labs/skills#install-a-skill) and [supported agents](https://github.com/vercel-labs/skills#supported-agents). Being listed there does not mean this skill has been tested in that client. If it does not appear after install, reload the agent or start a new session and check the skills list.

To install by hand, copy `SKILL.md` and `agents/` into a folder named `restraining-ui-text` in the agent's skills directory. The skill has no runtime or external-service dependency; Node.js is only needed for the installer.

## Use

Ask the agent to use `restraining-ui-text`. In Codex, invoke it with `$restraining-ui-text`.

It infers the mode from the request: restrain new UI text while building, report supported findings without editing, or make authorized changes in the requested scope. It can inspect screenshots, code, or a running interface when the agent has access. A screenshot alone cannot establish hidden behavior.

The UI keeps its existing language unless translation is requested. Explanations follow the user's preferred conversation language. Regional spelling, terminology, capitalization, Simplified/Traditional Chinese conventions, interpolation variables, and plural rules stay as they are. Bilingual versions should express equivalent actions and consequences without matching word counts. Changes stay within the requested locales.

## What it checks

- Buttons that enumerate destination contents or explain clicking.
- Placeholders and helper text that repeat persistent labels.
- Automatic subtitles and repeated explanations across a page.
- Internal implementation notes that do not inform user decisions.
- Instructions shown persistently when they are only needed in a specific state.

Supported fixes include deleting text nodes, shortening strings, combining repeated information, and cleaning up directly affected spacing and accessibility references. Creating a new help system or redesigning a layout is outside routine text cleanup.

Best suited to forms, settings, dashboards, admin software, editors, and other operational UI. Narrative, brand messaging, user-authored content, and purposeful teaching are not automatically included.

## Validation

Checked with independent Chinese, English, and cross-language scenarios, plus a static HTML editing fixture covering necessary information, shared strings, and accessibility references. These are limited scenario checks, not broad user testing or end-to-end verification in every supported agent.

## Files

```text
SKILL.md                    Shared agent instructions
agents/openai.yaml          Codex display metadata
README.md                   English guide
README.zh-CN.md             中文指南
```
