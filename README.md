# Fuxi Agent Loop Skill

[简体中文](README.zh-CN.md) | English

**Turn vague work into a verifiable agent loop.**

Fuxi is a compact operating skill for AI agents that need to manage real work across files, tools, repositories, creative pipelines, research tasks, and multi-agent handoffs without drifting into guesswork.

It is not another giant prompt. It is a small control layer that tells an agent when to discover, when to act, when to verify, when to persist state, and when to stop.

## Why Fuxi matters

Most long-running agent failures do not come from one bad answer. They come from weak loops:

- the agent acts before inspecting the real source of truth;
- the task expands but no one defines the next checkpoint;
- one agent generates work and then rubber-stamps its own output;
- useful decisions disappear between sessions;
- automation starts before a single safe manual run has proved the workflow.

Fuxi turns those failure modes into a reusable loop contract.

## What Fuxi gives an agent

| Capability | What changes in practice |
|---|---|
| Intent translation | Rough human requests become concrete next actions. |
| Source-first discovery | Agents inspect files, repos, logs, or docs before deciding. |
| Controlled execution | Work advances in small loop turns instead of uncontrolled sprawl. |
| Handoff discipline | Humans, tools, and agents receive clear next artifacts. |
| Independent verification | Results are checked with evidence, not confidence. |
| Durable memory | Only decisions, blockers, paths, and next actions are persisted. |
| Safety stops | Risky or irreversible actions stop at human checkpoints. |

## Good fits

Use Fuxi when an agent is asked to handle:

- messy project cleanup;
- recurring creative or writing workflows;
- multi-agent coordination;
- repository inspection and maintenance;
- knowledge-base deduplication;
- automation planning;
- daily or weekly project monitoring;
- vague non-technical requests that still need real execution.

## Not a fit

Do not use Fuxi for one-shot answers, casual chat, tiny edits, or tasks where no state, handoff, verification, or repetition is involved.

## Install

Copy this repository's `SKILL.md` into your agent skills directory.

For Codex-style skill folders:

```text
skills/
  fuxi/
    SKILL.md
```

Then ask your agent to use `fuxi` for recurring, multi-step, multi-agent, workflow, automation, cleanup, or project-monitoring tasks.

## Example prompts

```text
Use fuxi to turn this messy project cleanup into a repeatable workflow.
```

```text
Use fuxi to coordinate several agents without losing state.
```

```text
Use fuxi to make this vague creative workflow safe to run every day.
```

```text
Use fuxi to inspect this repository, define the next handoff, and stop before risky changes.
```

## The loop contract

Every Fuxi loop answers eight questions:

| Field | Question |
|---|---|
| Goal | What useful state should exist after the loop? |
| Owner | Which agent, tool, or project owns each part? |
| Discovery | Which source artifacts must be inspected? |
| Handoff | What exact artifact should the next actor receive? |
| Verification | How will success be checked independently? |
| Memory | Where should durable decisions and status be saved? |
| Stop rule | When must the loop stop instead of guessing? |
| Budget | What time, token, retry, file, or tool-call limit applies? |

## Design principles

- Run one safe loop turn before building automation.
- Inspect real source artifacts instead of relying on memory.
- Separate generation from verification.
- Persist decisions, not noise.
- Stop when risk, ambiguity, or irreversible action appears.

## Acknowledgements

Fuxi is inspired by public work on agent loops and workflow discipline, especially the Loop Engineering Orange Book by alchaincyf.

It also reflects general lessons from public discussions around agent operating discipline, prompt robustness, and multi-agent handoff design. This repository does not include copied proprietary system prompts.

See `ACKNOWLEDGEMENTS.md` for more detail.

## License

MIT License. See `LICENSE`.