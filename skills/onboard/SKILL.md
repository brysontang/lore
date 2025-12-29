---
name: onboard
description: Bootstrap knowledge for a new codebase. Use when _LORE/ is empty or sparse, or when asked to "onboard", "learn this codebase", "get up to speed", "set up context".
---

# Onboard

You're a new hire. The human is your onboarding buddy. Ask questions, document what you learn.

## Check Structure

First, verify structure exists:

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

Create any missing folders. Create README.md with:

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

## Interview

Work through these. One question at a time. Write to files immediately.

### 1. Systems → `entities/systems/`

"What systems does this project use?"

For each system:
- Try the MCP tools to see what's available
- Document query patterns that work
- Capture IDs (workspace, project, channel IDs)

Ask: "Show me how you'd find a task / a person's work / recent activity."

Do it together. Document what worked.

### 2. People → `entities/people/`

"Who works on this? What do they own?"

For each person:
- Name, role, responsibilities
- IDs across systems (Linear ID, GitLab username, Slack handle)
- Any working patterns worth noting

Ask: "Who do I go to for X? Who should I not bother for Y?"

### 3. Features → `entities/features/`

"What are you building right now?"

For active work:
- Name and current status
- Who owns it
- Related systems

### 4. Patterns → `patterns/good/`, `patterns/bad/`

"Show me a good [ticket/MR/decision]. Now show me a bad one."

For each example:
- Capture the actual content
- Document WHY it's good or bad
- Note what to do when you see similar

Ask: "What are your pet peeves? What slows everything down?"

### 5. Existing Processes

"Walk me through how a feature goes from idea to shipped."

Document in `processes/` if it's repeatable.

## Exit

When human says "that's enough":

1. Read back summary of what you learned
2. Ask: "What did I miss?"
3. Update files with additions
4. Confirm: "Ready. What should I work on first?"
