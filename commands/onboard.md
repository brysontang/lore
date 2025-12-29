---
description: Bootstrap knowledge for a new codebase. Creates _LORE/ structure and runs onboarding interview.
---

# Onboard

You're a new hire. The human is your onboarding buddy. Your job: ask questions, document what you learn, build the knowledge base that helps you work independently.

## First: Check Structure

Verify `_LORE/` exists with this structure:

```
_LORE/
├── README.md
├── entities/
│   ├── people/
│   ├── systems/
│   ├── features/
│   └── concepts/
├── processes/
├── decisions/
└── patterns/
    ├── good/
    └── bad/
```

Create any missing folders. If README.md doesn't exist, create it with:

```markdown
# Lore

## The Loop

1. **Notice** — Names, systems, concepts are entities
2. **Resolve** — Check `entities/` for what you know
3. **Work** — Use that context
4. **Accrete** — Update entities with what you learned

## Structure

- `entities/` — Who/what exists (with IDs for MCP lookup)
- `processes/` — How to do things (link entities, link other processes)
- `decisions/` — Why we do it this way (overrides processes)
- `patterns/` — What good/bad looks like (calibration)

The graph grows by accretion. Decisions override processes. Patterns calibrate everything.
```

## Then: Interview

Work through these sections. Ask one question at a time. Write answers to files immediately.

### 1. Systems → `_LORE/entities/systems/`

Ask: "What systems does this project use?"

For each system mentioned:
- Try the MCP tools to see what's available
- Document query patterns that work
- Capture IDs (workspace, project, channel IDs)

Then ask: "Show me how you'd find a task / a person's work / recent activity."

Do it together. Document what worked.

### 2. People → `_LORE/entities/people/`

Ask: "Who works on this? What do they own?"

For each person:
- Name, role, responsibilities
- IDs across systems (Linear ID, GitLab username, Slack handle)
- Any working patterns worth noting

Then ask: "Who do I go to for X? Who should I NOT bother for Y?"

### 3. Features → `_LORE/entities/features/`

Ask: "What are you building right now?"

For active work:
- Name and current status
- Who owns it
- Related systems

### 4. Patterns → `_LORE/patterns/good/`, `_LORE/patterns/bad/`

Ask: "Show me a good [ticket/MR/decision]. Now show me a bad one."

For each example:
- Capture the actual content
- Document WHY it's good or bad
- Note what to do when you see similar

Then ask: "What are your pet peeves? What slows everything down?"

### 5. Existing Processes

Ask: "Walk me through how a feature goes from idea to shipped."

Document in `_LORE/processes/` if it's repeatable.

## Finally: Confirm

When the human says "that's enough":

1. Read back a summary of what you learned
2. Ask: "What did I miss?"
3. Update files with any additions
4. Confirm: "Ready. What should I work on first?"
