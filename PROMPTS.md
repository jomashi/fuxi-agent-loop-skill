# Prompt Recipes / 提示词模板

Use these short prompts to test or activate Fuxi in an agent conversation.

## Minimal activation

```text
Use fuxi for this task. First build a loop contract, then run only one safe loop turn.
```

## 中文最短触发

```text
用 fuxi 处理这个任务。先建立 loop contract, 再只跑一轮安全的 loop turn。
```

## Repository inspection

```text
Use fuxi to inspect this repository, identify the real current state, define the next handoff, verify with evidence, and stop before risky changes.
```

## Multi-agent workflow

```text
Use fuxi to coordinate multiple agents. Define owners, handoff artifacts, verification, persistent state, budget, and stop rules.
```

## Creative workflow

```text
Use fuxi to turn this recurring creative workflow into a controlled loop. Preserve intent, separate generation from review, and stop at the next human checkpoint.
```

## Automation planning

```text
Use fuxi to design one manual loop turn before any automation. Do not schedule recurring execution until the manual turn is verified.
```

## Cleanup with deletion risk

```text
Use fuxi to plan cleanup safely. Inventory first, verify duplicates, and stop before deleting, overwriting, or moving files.
```

## Expected shape

A good Fuxi response should include:

```text
Goal:
Discovery:
Owner:
Handoff:
Verification:
Memory:
Stop rule:
Budget:
Next safe loop turn:
```