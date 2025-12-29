---
name: record-decision
description: Capture a judgment call. Use when something is decided for non-obvious reasons, when you deviate from standard process, or when the outcome of an action needs to be recorded.
---

# Record Decision

## When

- A choice was made between options
- Process was overridden for a reason
- Something is done "this way because..."
- You need to record "would I do this again?"

## Create

`_LORE/decisions/{YYYY-MM-DD}-{summary}.md`:

```markdown
# {Summary}

**Date:** YYYY-MM-DD

## Context

[What prompted this decision]

## Options Considered

1. [Option A]
2. [Option B]

## Decision

[What was decided]

## Why

[The actual reason — even if political/historical/weird]

## Entities Involved

- [[entities/people/...]]
- [[entities/systems/...]]
- [[entities/features/...]]

## Processes Affected

- [[processes/...]]

## Would Repeat

**Yes** / **No** / **Conditional**

[If no: what went wrong, what to do instead]
[If conditional: under what circumstances]
```

---

## The Calibration Loop

This is how the system learns.

### On "Would Repeat: No"

Ask: "Should this become a pattern to avoid?"

If yes → Create `_LORE/patterns/bad/{description}.md`:

```markdown
# {Anti-pattern Name}

## What Happened

[Brief description]

## Why It Was Wrong

[What went badly]

## What To Do Instead

[The correction]

## Origin

[[decisions/YYYY-MM-DD-summary]]

## Entities

[[links to relevant entities]]
```

### On "Would Repeat: Conditional"

Capture the condition clearly. This decision overrides normal process only when the condition applies.

Example: "Don't deploy billing on Fridays" is conditional — it overrides the normal deploy process, but only for billing, only on Fridays.

### On "Would Repeat: Yes" (with insight)

If something worked especially well, consider:

Ask: "Should this become a pattern to follow?"

If yes → Create `_LORE/patterns/good/{description}.md`:

```markdown
# {Pattern Name}

## What To Do

[The good practice]

## Why It Works

[What makes it effective]

## Example

[Concrete instance]

## Origin

[[decisions/YYYY-MM-DD-summary]]

## Entities

[[links to relevant entities]]
```

---

## Rules

1. **Always include "Would Repeat"** — This is how learning happens.
2. **Link entities** — Decisions are findable by what they touch.
3. **Link processes** — Decisions override processes.
4. **Promote to patterns** — Bad outcomes become avoidance patterns. Good outcomes become best practices.

## The Learning Flow

```
Mistake happens
    → record-decision with "would repeat: no"
    → promote to patterns/bad/
    → next search-process finds it
    → mistake not repeated
```

This is case law for agents.
