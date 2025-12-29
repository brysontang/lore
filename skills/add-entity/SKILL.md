---
name: add-entity
description: Create or update an entity. Use when encountering something worth remembering that doesn't have a file yet — a person, system, feature, or concept.
---

# Add Entity

## When

- You encounter a name/system/concept not in `_LORE/entities/`
- You learn something new about an existing entity
- The human mentions something worth tracking

## Structure

```
_LORE/entities/{type}/{name}.md
```

Types: `people`, `systems`, `features`, `concepts`

## Templates

### Person

```markdown
# {Name}

## Identity
- Role: 
- Owns: [[entities/features/...]], [[entities/systems/...]]

## System IDs
- ClickUp: [ID]
- GitLab: @username
- Slack: @handle

## Working Patterns
[What you've observed about how they work]

## Notes
[Anything worth remembering]
```

### System

```markdown
# {Name}

## Connection
- MCP tools: `mcp__{name}__*`

## Key IDs
[Workspace, project, channel IDs — whatever speeds up queries]

## Query Patterns
[What works when you need to find things]

## Entities Here
[What types of things live in this system]
```

### Feature

```markdown
# {Name}

## Status
[Current state]

## Owner
[[entities/people/...]]

## Systems
[[entities/systems/...]]

## History
[Key decisions, context]
```

### Concept

```markdown
# {Name}

## What It Is
[Definition in this context]

## Why It Matters
[Relevance to this project]

## Related
[[links to related entities]]
```

## Rules

1. **Always capture IDs.** They're the bridge to live MCP data.
2. **Link to other entities.** Use `[[relative/path]]` from _LORE root.
3. **Stub is fine.** Fill what you know, note what's missing.
4. **Update on encounter.** Entity files grow through use.
