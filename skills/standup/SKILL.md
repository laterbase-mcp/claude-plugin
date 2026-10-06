---
name: standup
description: "A three-line backlog standup: what was pinned, what's in flight and what got fixed recently. Use when the user asks for a standup, a recap, or what happened in the backlog."
---

# Backlog standup

1. Work out "since": yesterday at this time unless the user says otherwise, as an ISO date-time with offset.
2. Get the repo as `owner/name` from `git remote get-url origin`.
3. Call `search_pins` three times with `workspace` set to the one listing that repo (the field's description lists each workspace's repos) and no `repo`, so it covers the whole workspace:
   - New: `status: ["open", "claimed"]`, `created_after: <since>`, `sort: "recent"`.
   - In flight: `status: ["claimed"]`, `sort: "recent"`.
   - Fixed: `status: ["resolved"]`, `sort: "recent"`, `limit: 10`, keeping those resolved since then (check with `get_pin` when the summary doesn't say).
4. Reply with three lines, one per group: a count, then the top few keys with short titles. Add one line calling out anything high risk that's new or unclaimed.
