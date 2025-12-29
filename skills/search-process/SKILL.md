---
name: search-process
description: Find how to do something before starting complex work. Use when asked to do something multi-step, or when you're about to do something that might have a documented process.
---

# Search Process

## When

Before starting complex or repeatable work.

## Procedure

### 1. Identify Entities

What entities are involved in this task?
- People?
- Systems?
- Features?

### 2. Search Processes

```bash
# Find processes involving these entities
grep -r "entities/people/mubeen" _LORE/processes/
grep -r "entities/systems/clickup" _LORE/processes/
```

Or search by keyword:
```bash
grep -ri "deploy" _LORE/processes/
grep -ri "review" _LORE/processes/
```

### 3. Check Decisions

```bash
# Find decisions that might override standard process
grep -r "entities/people/mubeen" _LORE/decisions/
grep -r "entities/systems/clickup" _LORE/decisions/
```

**Decisions override processes.** If a decision applies, follow it.

### 4. Check Patterns

```bash
# Find patterns to follow or avoid
grep -r "keyword" _LORE/patterns/good/
grep -r "keyword" _LORE/patterns/bad/
```

Apply good patterns. Avoid bad patterns.

### 5. Execute

| Found | Action |
|-------|--------|
| Exact process match | Use it |
| Partial match | Use as base, ask human for gaps |
| Similar processes | Combine, ask human to confirm |
| Decision override | Apply the override |
| Pattern match | Follow good, avoid bad |
| No match | Ask human how, offer to log when done |

### 6. After

If you did something new that worked → use `log-process` skill

If a judgment call was made → use `record-decision` skill
