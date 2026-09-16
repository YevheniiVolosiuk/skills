# skills

Personal agent skills. Source of truth for the skill files themselves; the catalog that indexes and installs them is [`web-developmet-registry`](https://github.com/YevheniiVolosiuk/web-developmet-registry).

## Layout

```
skills/       one folder per skill, folder name == frontmatter name
references/   shared knowledge, pointed at by skills
templates/    output formats the skills fill in
```

Flat. No category folders — the name carries the domain, and a sorted listing reads as the lifecycle.

## Naming

Lowercase kebab-case, domain first: `idea-grill`, `idea-research`, `project-brief`.

Domain first rather than action first because the domain word groups the folder into a readable sequence, and the frontmatter `description` — not the name — is what actually triggers a skill. No `product-` prefix: the repo is already the category, and every prefix character is paid for in context on every turn.

## What is here

A product discovery chain. Three skills, deliberately — validate on a real idea before adding a fourth.

```
idea-grill        →  idea-decision.md
idea-research     →  research-questions.md  →  research/
project-brief     →  project-description.md
```

| Skill | Does | Leans on |
|---|---|---|
| `idea-grill` | Raw idea → written verdict | `mattpocock-skills:grilling` |
| `idea-research` | Open assumptions → ranked questions, dispatched | `mattpocock-skills:research` |
| `project-brief` | PROCEED verdict → project definition | — |

`idea-grill` does not re-implement grilling. It wraps it with a workspace, an assumption ledger, and a verdict that survives the conversation.

## Where artifacts go

Not here. Skills are reusable behaviour; idea and project documents are project memory, with a different lifecycle. See [`references/idea-workspace.md`](references/idea-workspace.md).

## Deliberately absent

- **`registry.yaml`** — the registry repo holds the catalog. A second copy here would be a stale duplicate of it.
- **`workflows/*.yaml`** — nothing executes YAML steps. Sequencing lives in each skill's closing section, which an agent actually reads.
- **`category:` frontmatter** — Claude Code reads `name`, `description`, `allowed-tools`. A category field changes no behaviour.

## Install

Via the registry skill:

```
/registry add skill:idea-grill https://github.com/YevheniiVolosiuk/skills/blob/main/skills/idea-grill/SKILL.md
/registry install skill:idea-grill
```

Or directly, for local iteration:

```sh
ln -s "$PWD/skills/idea-grill" ~/.claude/skills/idea-grill
```

The symlink is the better loop while a skill is still being tuned — edit, run it on a real idea, edit again.

## Adding a skill

1. It earns a slot by failing in practice first. Write the skill after you have watched the gap, not before.
2. One folder, one `SKILL.md`, folder name matching frontmatter `name`.
3. Shared knowledge goes in `references/`, output shapes in `templates/` — never restated inside a skill.
4. Register it in the catalog repo.
