---
name: log-process
description: Record a novel workflow that worked. Use after completing something multi-step that might be repeated.
---

# Log Process

## When

After doing something complex that succeeded.

Ask yourself: "Would I do this again the same way?"

If yes → Log it.

## Trigger Check

Before creating, search for existing:

```bash
grep -ri "relevant-keyword" _LORE/processes/
```

If similar exists, consider updating it instead of creating duplicate.

## Create

`_LORE/processes/{name}.md`:

```markdown
# {Process Name}

## Trigger

[When to use this — natural language patterns that invoke it]

Examples:
- "Check if [person] is working on [thing]"
- "Deploy to staging"
- "Review MR from [person]"

## Procedure

1. [Step — link entities involved]
2. [Step]
3. [Step]

## Entities Used

- [[entities/systems/...]]
- [[entities/people/...]]
- [[entities/features/...]]

## Related Processes

- [[processes/...]] — [why related, don't duplicate]

## Gotchas

[What to watch out for — may link to patterns/bad/]
```

## Rules

1. **Link entities.** Every system/person/feature involved gets a link.
2. **Link related processes.** Don't duplicate content, reference.
3. **Capture triggers.** Natural language that should invoke this.
4. **Note gotchas.** Link to bad patterns if relevant.

## Process Discovery Prompt

When you complete a multi-step task successfully, ask:

> "Should I save this as a process?"

If yes, create the file immediately while context is fresh.
