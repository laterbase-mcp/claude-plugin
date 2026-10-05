---
name: epic
description: Take the biggest high-payoff pin and break it into a plan of smaller linked pins instead of attempting it in one go. Use when the user wants to tackle something big or asks for an epic.
---

# Break down an epic

1. Get the repo as `owner/name` from `git remote get-url origin`.
2. Call `search_pins` with that `repo`, `min_payoff: "high"`, `sort: "scope"`, `order: "desc"`, `limit: 5`, and take the largest. If the user named a pin, use that one.
3. Call `get_pin`, read its files, and work out a plan of steps that can each ship as their own PR.
4. Show the plan to the user as a short numbered list (title and scope per step) and ask before creating anything.
5. Once they agree, create a pin per step with `create_pin`, each with its files, a precise done-when and `links: [{ relation: "blocks", pin: <epic key> }]`. A step that must come first also blocks the steps after it; add those links with `update_pin` once their keys exist.
6. The `blocks` links are the plan, so the epic needs no extra note. If its `approach` no longer fits, rewrite it with `update_pin` as the steps in order by key. Reply with the step keys in order and offer to start the first one.
