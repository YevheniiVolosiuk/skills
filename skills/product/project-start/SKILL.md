---
name: project-start
description: Start the project repo stubbornweb/<slug> - make it or adopt it, then move the idea folder and the quick experiment into it. Use when an idea gets PROCEED, or when an existing project joins the studio.
---

# Project start

Turns a PROCEED verdict, or an existing project, into a project repo: `stubbornweb/<slug>` with `PROJECT.md` at its root. Every later skill and engine finds the project through that file.

Ask every question through `AskUserQuestion`, as `idea-grill` does.

## 1. Check the slug

Agree the slug with the user. Check it against the slug rule in [`WORKSPACE.md`](../idea-grill/WORKSPACE.md). If the slug breaks the rule, reject it, show the rule and ask for a new slug. Never change the slug yourself.

The slug is the repo name. For an idea, it is also the name of the idea folder.

**Done when:** the slug follows the rule.

## 2. Collect the facts

Look for the idea folder at `~/www/idea-workspace/ideas/<slug>/`. If it exists, its `IDEA-DECISION.md` must have the line `**Verdict:** PROCEED`. If it does not, say so and stop.

Ask the user:

- **The stage the project enters at:** `idea`, `design`, `prototype`, `build`, `live` or `closed`. After a PROCEED, the stage is usually `idea`, because `project-brief` runs next.
- **The client:** the client slug, or none. A client slug follows the same slug rule. If `~/www/idea-workspace/clients/<client-slug>/` does not exist, stop and tell the user to run `client-intake` first.
- **The project name:** a short name for the title of `PROJECT.md`. Offer the title of `IDEA-DECISION.md` first, if it exists.

**Done when:** the verdict is PROCEED or there is no idea folder, and you know the stage, the client or none, and the project name.

## 3. Get the repo

Run `gh repo view stubbornweb/<slug>`.

- **The repo does not exist:** tell the user that you will make the private repo `stubbornweb/<slug>`, and wait for a "yes". Then run `gh repo create stubbornweb/<slug> --private --add-readme`. The first README commit gives the repo a `main` branch, so all other changes can go through a pull request.
- **The repo exists:** this is an adoption. If it has `PROJECT.md` at its root, the project has already started: say so and stop. If the project has a client and the repo is public, stop and tell the user: a client project repo is private.

The local clone is `~/www/<slug>/`. If that folder does not exist, run `gh repo clone stubbornweb/<slug> ~/www/<slug>`. If it exists but is not a clone of `stubbornweb/<slug>`, stop and tell the user.

In the clone, make the branch `project-start` from the latest default branch.

**Done when:** `~/www/<slug>/` is a clone of `stubbornweb/<slug>` on the branch `project-start`.

## 4. Copy the work in

- **The idea folder:** if `~/www/idea-workspace/ideas/<slug>/` exists, pull the latest `main` in `~/www/idea-workspace/` first. If `git status` then shows changes in `ideas/<slug>/`, stop and tell the user: the folder must be on `main`, because step 6 deletes it there. Copy the contents of the folder, with their subfolders, into `1-idea/`.
- **The quick experiment:** if `~/www/prototypes/<slug>/` exists, copy its contents, with their subfolders, into `3-prototype/`. Leave out every `node_modules/` and `dist/` folder, at any depth.

Keep the old folders until step 6.

**Done when:** for each old folder that exists, every file in it, except `node_modules/` and `dist/`, is in the repo at the same path under its new folder.

## 5. Write the project files

Fill [`PROJECT-FILES-FORMAT.md`](PROJECT-FILES-FORMAT.md) into the repo root.

In a new repo, replace the `README.md` that `gh repo create` made. In an adopted repo, keep each file that already exists, except `README.md`: add the entry note under its title. Tell the user which files the adopted repo already had.

Commit, push the branch, and open a pull request to the default branch.

**Done when:** the pull request is open, it has each file from `PROJECT-FILES-FORMAT.md` or the user knows that the repo kept its own, and `PROJECT.md` names the stage the user gave.

## 6. Clean up the old folders

Ask the user to merge the project repo pull request, and wait until it is merged. Then:

- **The idea folder:** in `~/www/idea-workspace/`, make a branch from the latest `main`, delete `ideas/<slug>/`, commit, push and open a pull request. Its body links to the project repo.
- **The quick experiment:** tell the user that you will delete `~/www/prototypes/<slug>/`, and wait for a "yes". It has no git, so the copy in `3-prototype/` becomes the only one.

**Done when:** each old folder that existed is deleted, or has an open pull request that deletes it.

## Where it goes next

Tell the user which skill runs next:

- No `1-idea/PROJECT-DESCRIPTION.md` yet → `project-brief`
- A brief and no prototype → the Prototype Engine, run inside `~/www/<slug>/`
