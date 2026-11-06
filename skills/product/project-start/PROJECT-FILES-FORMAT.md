# Project files

The files `project-start` writes at the root of a project repo. `PROJECT.md` follows ADR 0003 and the agent rules follow ADR 0004, both in `stubbornweb/studio`.

## PROJECT.md

```markdown
# <Project name>

**Format:** 1
**Stage:** <idea | design | prototype | build | live | closed>
**Client:** <client-slug>
```

- Write the `**Client:**` line only for a client project.
- Write no slug line. The repo name is the slug.

## README.md

```markdown
# <Project name>

The project repo of <Project name>. `PROJECT.md` names its stage.

This project joined the studio at the `<stage>` stage on YYYY-MM-DD. The stages before it have no folder here.
```

- The last line is the entry note. Write it only when the stage is not `idea`. The date is today's date.
- In an adopted repo, keep the old `README.md` and add only the entry note under its title.

## AGENTS.md

```markdown
# <Project name> — agent rules

This repository is the project repo of <Project name>. `PROJECT.md` names its stage, and its client if it has one.

## Shared rules

1. Work on a branch and open a pull request. Never push to `main`.
2. Write a failing test first for any code with logic.
3. This repo has no check yet. Read the full diff before you open a pull request.
4. Write all text in plain English (Simplified Technical English style, CEFR B1).

## Repo rules

- Each stage writes into its own folder: `1-idea/`, `2-design/`, `3-prototype/` and `5-live/`. The product code takes the repo root.
- Only the owner sets the stage to `build`, `live` or `closed` in `PROJECT.md`.
```

- When the repo already has a check, such as `npm run check`, rule 3 reads "Run `<check>` before you open a pull request."

## CLAUDE.md

```markdown
@AGENTS.md
```

## .gitignore

```
node_modules/
dist/
```
