# Idea workspace

Where idea artifacts live. Skills are reusable behaviour; these files are project memory. They do not live in this repo.

## Location

An idea that has no project yet:

```
~/ideas/<slug>/
```

An idea that belongs to an existing project:

```
<project-root>/docs/ideas/<slug>/
```

Use the project path as soon as a project exists. Move the folder rather than forking it.

## Slug

Lowercase kebab-case, named for the thing the idea does, not the technology it uses:

- `meeting-notes-search` — good
- `ai-tool` — too vague to find again
- `nih-v2` — an internal reference nobody will decode in six months

## Contents

Files appear in this order as an idea moves through the lifecycle. A missing file means that stage has not run.

```
~/ideas/<slug>/
├── IDEA-DECISION.md        # idea-grill
├── RESEARCH-QUESTIONS.md   # idea-research
├── research/               # the research skill writes findings here
│   └── <question-slug>.md
└── PROJECT-DESCRIPTION.md  # project-brief
```

Never rewrite a file an earlier stage produced. Append a dated section instead — the history of how a verdict changed is the point of keeping the record.
