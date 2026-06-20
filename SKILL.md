---
name: fuxi
description: Use when a vague, recurring, multi-step, multi-agent, project-monitoring, creative-production, automation, or workflow-management request needs to become a controlled repeatable work loop.
---

# Fuxi

## Overview

Fuxi turns a broad request into a controlled agent loop: discover the real state, define the next handoff, verify independently, persist state, then decide whether to continue, stop, or ask the user.

## Core Rule

Never start an unattended loop from a vague request. First produce one safe loop contract, run only the current turn, and stop at the next human checkpoint unless the user already approved automation.

## Loop Contract

Before running a loop, establish:

| Field | Required answer |
|---|---|
| Goal | What useful state should exist after the loop? |
| Owner | Which agent, tool, or project owns each part? |
| Discovery | Which files, repositories, logs, documents, or tools must be inspected? |
| Handoff | What exact artifact should the next actor receive? |
| Verification | How will success be checked independently? |
| Memory | Where should decisions, paths, and status be saved? |
| Stop rule | When must the loop stop instead of guessing? |
| Budget | Max time, tokens, retries, files, or tool calls for one turn. |

If any field is unknown, make the smallest safe assumption and state it, or ask one necessary question.

## One Loop Turn

1. Translate the rough intent into a concrete objective.
2. Discover the real current state from source artifacts, not memory or habit.
3. Do the smallest useful next step that moves the loop forward.
4. Verify with a different check than the one used to create the result.
5. Persist only durable facts: paths, decisions, blockers, next action.
6. Report the result, evidence, and next checkpoint.

## Inner-Run Discipline

For each agent run:

- Give one substantive next step before asking questions.
- Ask at most one clarification question unless blocked.
- Scale tool depth to risk: quick read for simple tasks, full inspection for code, data, and workflow decisions.
- Keep chat separate from deliverables: a user-facing summary is not the working artifact.
- Verify actual files, commands, logs, or outputs before saying done.

## Loop Patterns

| Situation | Pattern |
|---|---|
| User cannot define requirements | Translate into a task card, then execute the safest first slice. |
| Multiple agents or tools involved | Assign one owner per artifact and define handoff format. |
| Repeated creative workflow | Preserve user intent, separate generation from review, keep versioned outputs. |
| Repository or system maintenance | Inspect source, patch minimally, run direct validation, record changed paths. |
| Knowledge-base cleanup | Inventory first, dedupe second, delete only after a human checkpoint. |
| Automation idea | Simulate one manual loop before scheduling anything. |

## State Format

Use this compact state block in a file, memory entry, or handoff message when persistence is needed:

```text
Loop:
Goal:
Current state:
Sources inspected:
Actions taken:
Verification:
Decisions:
Blocked by:
Next action:
Stop rule:
Budget used:
```

## Safety Stops

Stop and ask the user when:

- Deletion, overwriting, purchase, account, billing, credential, or irreversible external action is required.
- Discovery sources conflict and the correct source of truth is unclear.
- Verification fails twice for the same reason.
- The next step would exceed the agreed budget or scope.
- The loop would begin acting continuously without explicit approval.

## Common Mistakes

| Mistake | Correction |
|---|---|
| Building a grand workflow before one real run | Run one manual loop turn first. |
| Trusting prior summaries | Re-open source artifacts when accuracy matters. |
| Letting the generator verify itself | Use independent checks, tests, logs, or a reviewer pass. |
| Saving everything to memory | Save only durable decisions and next actions. |
| Continuing because progress feels possible | Stop at the checkpoint when risk or uncertainty rises. |

## Output Shape

For user updates, keep it short:

```text
Conclusion: ...
Evidence: ...
Completed: ...
Verification: ...
Next: ...
```

For agent handoff, use the State Format instead of prose.