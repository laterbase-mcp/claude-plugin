---
name: recommend
description: Recommend the three pins most worth doing next in this repo, with a reason for each. Use when the user asks what to work on, what matters most, or for a recommendation.
---

# What to do next

Recommend three pins, best first, and let the user pick.

1. Get the repo as `owner/name` from `git remote get-url origin`.
2. Call `search_pins` with that `repo`, `sort: "leverage"`, `limit: 15`.
3. Boost pins that touch what the user is working on: list files changed on this branch (`git diff --name-only $(git merge-base HEAD origin/HEAD)`, or recent commits) and call `pins_near` with them.
4. `pins_near` also returns claimed pins: drop those unless the user holds the claim. Prefer a mix: the best leverage, the riskiest open issue, and one near the current work.
5. Reply with three lines, each: key, title, scope, and one sentence on why now. End by asking which one to start; don't claim anything until they choose.
