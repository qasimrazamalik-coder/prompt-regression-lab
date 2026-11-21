# Prompt Regression Lab

> Prompt edits silently break output contracts because teams compare examples by eye.

Provider-neutral AI skill for Claude Code, Codex, ChatGPT, Claude, Gemini, Grok and custom agent runtimes. It combines concise agent instructions with a deterministic Python execution path.

## What it does

Run deterministic regression checks over prompt outputs using required claims, forbidden phrases, structural contracts and length budgets. Use when changing system prompts, agent instructions, templates, or model providers.

## Architecture

```text
User/Agent → SKILL.md → input contract → deterministic runner → validated JSON result
```

## Install

Copy `skill/` into your agent's skills directory, or reference `skill/SKILL.md` from an agent configuration. No API key or network access is required.

## Demo

```bash
python skill/scripts/run.py examples/input.json --mode regression
pytest -q
```

![Workflow preview](assets/workflow-preview.svg)

## Compatibility

| Runtime | Method |
|---|---|
| Codex / ChatGPT | Install or reference `skill/` |
| Claude Code | Add `skill/SKILL.md` to project instructions or a command wrapper |
| Gemini / Grok | Supply `SKILL.md` as system/project context and expose the runner as a tool |
| MCP agents | Wrap the runner as a stdio tool with the documented JSON contract |

## Safety

See [SECURITY.md](SECURITY.md) and [docs/GUARDRAILS.md](docs/GUARDRAILS.md). The skill does not bypass access controls or transmit input data.
