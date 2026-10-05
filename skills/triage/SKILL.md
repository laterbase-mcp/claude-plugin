---
name: triage
description: Check older open pins in this repo against the current code, resolving ones already fixed and correcting stale ones. Use when the user asks to clean up, triage or groom the backlog.
---

# Triage the backlog

1. Get the repo as `owner/name` from `git remote get-url origin`.
2. Call `search_pins` with that `repo`, `sort: "recent"`, `order: "asc"`, `limit: 15`, so the oldest come first.
3. For each pin, `get_pin` and check its files and snippets against the code as it is now.
   - Already fixed: find the commit that fixed it (`git log` on the file, or `git log -S` with the snippet) and `set_status` it `resolved` with that commit as `fixed_in`. Only if it was fixed with no trace, `dismissed` with a note saying so.
   - Code moved: `update_pin` with the new path, lines or symbol.
   - Ratings look wrong now: `update_pin` risk, payoff or scope, with a `reason`.
   - Same issue as another pin: dismiss it with `duplicate_of`.
4. Search returns only open pins. To spot abandoned claims, search again with `status: ["claimed"]` and mention any whose `claimed_at` (from `get_pin`) looks stale; leave them claimed.
5. Finish with a short tally: resolved, dismissed, updated, untouched.
