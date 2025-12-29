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

## Rules

1. **One entity per file.** If you feel the urge to cluster (multiple people in one file, multiple apps in one file), resist. Create separate files. Each entity is a node in the graph. You can't link to a heading inside a file.

2. **INDEX.md for navigation.** If a folder has many entities, create an INDEX.md that links to them all. The index is for humans browsing — not a substitute for individual files.

3. **Always capture IDs.** They're the bridge to live MCP data.

4. **Link to other entities.** Use `[[relative/path]]` from _LORE root.

5. **Stub is fine.** Fill what you know, note what's missing.

6. **Update on encounter.** Entity files grow through use.

## Examples

**Good:**
```
entities/systems/
├── INDEX.md
├── myapp-desktop.md
├── myapp-mobile.md
├── myapp-backend.md
├── linear.md
└── slack.md
```

**Bad:**
```
entities/systems/
├── applications.md    ← Three apps crammed in one file
├── linear.md
└── slack.md
```

## Templates

### Person

```markdown
# {Name}

## Identity
- Role: 
- Owns: [[entities/features/...]], [[entities/systems/...]]

## System IDs
- Linear: [ID]
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
