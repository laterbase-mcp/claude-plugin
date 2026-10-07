---
name: nearby
description: Show pins near the files changed on this branch, and which one this change could close. Use when the user asks what's known about the code they're touching, or before opening a PR.
---

# Pins near this change

1. Get the repo as `owner/name` from `git remote get-url origin`.
2. List the files changed on this branch and in the working tree: `git diff --name-only $(git merge-base HEAD origin/HEAD)` plus `git status --porcelain`. Use repo-relative paths.
3. Call `pins_near` with them (`limit: 10`).
4. For each pin, say in one line what it is and whether this change touches it: fixes it, makes it worse, or just sits nearby. Read it with `get_pin` when you need its details to judge.
5. If the change fixes one, link the PR to it with `update_pin` (`links: [{ relation: "fixed_in", artifact: <PR URL> }]`) as soon as the PR is open. If one is close but not part of the task, say so; folding it in is the user's call.
