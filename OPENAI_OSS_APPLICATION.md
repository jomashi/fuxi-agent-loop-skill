# Open Source Fund Application Draft

This is a reusable draft for applying to open-source AI or developer-credit programs. Edit the contact fields and usage metrics before submitting.

## Project

Fuxi Agent Loop Skill

Repository: https://github.com/jomashi/fuxi-agent-loop-skill

## Short description

Fuxi is a compact agent skill that turns vague, recurring, multi-step work into verifiable agent loops with discovery, handoff, independent verification, persistent state, budget limits, and human safety checkpoints.

## Problem

Many agent workflows fail because they do not have a reliable operating loop. Agents often act before inspecting source artifacts, lose context between sessions, verify their own generated work, or start automation before a safe manual run has been tested.

## Solution

Fuxi provides a small reusable loop contract and operating discipline for agents. It helps agents define the goal, owner, discovery sources, handoff artifact, verification method, memory location, stop rule, and budget before executing one safe loop turn.

## Why it is useful for open-source developers

Open-source maintainers often need help with recurring repository work: triage, documentation cleanup, release preparation, test checks, issue review, and project status reporting. Fuxi gives agents a safer pattern for doing this work without drifting into destructive or unverifiable actions.

## Current contents

- `SKILL.md`: the agent skill definition;
- `README.md`: Chinese homepage and installation guide;
- `README.en.md`: English guide;
- `PROMPTS.md`: copyable activation prompts;
- `EXAMPLES.md`: practical usage examples;
- `TEST_PLAN.md`: validation scenarios;
- `SECURITY.md`: safety and reporting guidance;
- `ACKNOWLEDGEMENTS.md`: attribution and source notes;
- `LICENSE`: MIT License.

## Safety stance

Fuxi is designed to stop before risky or irreversible actions such as deletion, overwriting, billing, credential changes, account operations, or unattended automation. It requires a manual loop turn before recurring automation.

## Credits requested

API credits would be used to test Fuxi across realistic open-source maintenance workflows, including repository inspection, documentation cleanup, multi-agent handoff, and verification scenarios.

## Suggested application summary

Fuxi Agent Loop Skill is a small open-source skill for making AI agents safer and more useful in recurring real-world work. It gives agents a repeatable loop contract: discover the real state, define handoffs, verify independently, persist durable state, respect budget limits, and stop at human checkpoints. The project is MIT licensed and includes installation guides, examples, prompt recipes, a test plan, and security guidance.