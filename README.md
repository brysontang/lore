# Lore

Tribal knowledge system for AI agents. Obsidian for agents.

The graph grows through use. Mistakes become patterns. The system learns.

## What This Is

A drop-in knowledge system for Claude Code. Instead of re-explaining your codebase every session, Lore captures:

- **Entities** — People, systems, features, concepts (with IDs for fast MCP lookups)
- **Processes** — How to do things (discovered through use, not pre-defined)
- **Decisions** — Why we do it this way (the "we do it weird because..." stuff)
- **Patterns** — What good/bad looks like (learned from mistakes)

Everything links together with `[[wiki-links]]`. Query with grep. Navigate by following links.

## Installation

```bash
claude plugin install lore
```

Or manually:

1. Copy this repo to your plugins directory
2. Add to your `CLAUDE.md`:
   ```markdown
   ## Knowledge System
   Your second brain is `_LORE/`. Read the README and use the lore skills.
   ```
3. Ask Claude to "onboard to this codebase"

## The Loop

```
Notice → Resolve → Work → Accrete
```

1. **Notice** — Names, systems, concepts are entities
2. **Resolve** — Check `_LORE/entities/` for what you know
3. **Work** — Use that context
4. **Accrete** — Update entities with what you learned

## The Learning Loop

```
Do thing → Outcome → "Would repeat?" 
                          ↓
                    If no → Pattern
                          ↓
                    Next time → Avoided
```

Decisions capture outcomes. Bad outcomes become patterns. Patterns prevent repeat mistakes.

## Structure

```
_LORE/
├── README.md              # Principles
├── entities/
│   ├── people/            # Who's who
│   ├── systems/           # ClickUp, GitLab, Slack, etc.
│   ├── features/          # What you're building
│   └── concepts/          # Ideas worth tracking
├── processes/             # How to do things
├── decisions/             # Why we do it this way
└── patterns/
    ├── good/              # Do it like this
    └── bad/               # Don't do this
```

## Skills

| Skill | Trigger |
|-------|---------|
| `onboard` | Empty context, new codebase, "get up to speed" |
| `add-entity` | Encounter something new worth remembering |
| `search-process` | Before complex work |
| `log-process` | After novel workflow succeeds |
| `record-decision` | Judgment call made |

## How It Connects

- **Entities** are anchors. Everything links to them.
- **Processes** describe *how*. They reference entities.
- **Decisions** describe *why we deviate*. They override processes.
- **Patterns** describe *what good/bad looks like*. They calibrate behavior.

## Philosophy

This isn't a database. It's a wiki that grows through work.

You don't architect it. You accumulate it.

The human does what they'd do with any new hire: show them around, answer questions, give examples. Claude writes the documentation they never got around to writing.

## License

MIT

## Author

Bryson Tang
