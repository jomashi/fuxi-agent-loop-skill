# Examples / 使用案例

These examples show what Fuxi is designed to produce: a small loop contract, a safe next turn, and a clear stopping point.

## Example 1: Knowledge-base cleanup

User request:

```text
Use fuxi to clean duplicate knowledge-base files and remove old copies.
```

Expected Fuxi behavior:

```text
Goal: Build a verified duplicate inventory before any deletion.
Discovery: Scan target folders, file names, sizes, hashes, and modified times.
Owner: Agent prepares inventory; human approves deletion rules.
Handoff: A duplicate report with keep/delete candidates.
Verification: Re-check hashes and sample contents before any destructive action.
Memory: Save duplicate rules, approved paths, and unresolved conflicts.
Stop rule: Stop before deleting, moving, or overwriting files.
Budget: One inventory pass only.
Next safe loop turn: Generate the duplicate inventory report.
```

Why it matters:

- prevents accidental deletion;
- separates inventory from cleanup;
- keeps human approval at the irreversible step.

## Example 2: Weekly research-to-writing workflow

User request:

```text
Use fuxi to coordinate a researcher agent and a writer agent for a weekly report workflow.
```

Expected Fuxi behavior:

```text
Goal: Produce a verified weekly report packet.
Discovery: Check source list, deadlines, previous report format, and required sections.
Owner: Researcher gathers sources; writer drafts; verifier checks citations and gaps.
Handoff: Research packet -> draft -> verification notes -> final packet.
Verification: Source count, citation links, missing-section checklist.
Memory: Save report template, source rules, unresolved questions, next deadline.
Stop rule: Stop if sources conflict or required data is unavailable.
Budget: One report cycle, one verification pass.
Next safe loop turn: Build the source checklist and handoff template.
```

Why it matters:

- avoids losing context between agents;
- makes review separate from generation;
- creates a repeatable reporting loop.

## Example 3: Repository health check

User request:

```text
Use fuxi to automate a daily repository health check.
```

Expected Fuxi behavior:

```text
Goal: Define a safe daily repo check before scheduling automation.
Discovery: Inspect package files, test commands, CI config, open issues, and recent commits.
Owner: Agent runs read-only checks; human approves recurring automation.
Handoff: A health-check checklist and output format.
Verification: Run one manual check and confirm output is useful.
Memory: Save commands, expected outputs, known failures, next check time.
Stop rule: Do not create scheduled automation until manual check passes.
Budget: One manual dry run.
Next safe loop turn: Identify available test/lint/status commands.
```

Why it matters:

- keeps automation from running before it is understood;
- prevents noisy or unsafe recurring jobs;
- makes the first run auditable.

## Example 4: Creative production loop

User request:

```text
Use fuxi to make this vague creative workflow safe to run every day.
```

Expected Fuxi behavior:

```text
Goal: Create a repeatable daily creative production loop.
Discovery: Inspect brief format, source materials, output requirements, review criteria, and archive path.
Owner: Generator creates draft; reviewer checks intent; human approves final direction.
Handoff: Brief -> draft -> review notes -> accepted version -> archive entry.
Verification: Intent checklist, style checks, missing-material check, final artifact existence.
Memory: Save accepted direction, rejected variants, file paths, and next prompt.
Stop rule: Stop if creative direction is unclear or source material is missing.
Budget: One draft and one review pass.
Next safe loop turn: Build the daily brief template.
```

Why it matters:

- preserves intent across repeated runs;
- prevents the tool from drifting away from the user's taste;
- keeps human taste decisions out of blind automation.