---
name: quick
description: Pick the best small pin in this repo and fix it now, end to end. Use when the user wants a quick win, has a few minutes, or says "give me something small".
---

# Quick win

Find one small, worthwhile pin in this repo and ship the fix.

1. Get the repo as `owner/name` from `git remote get-url origin`.
2. Call `search_pins` with that `repo`, `max_scope: "small"`, `sort: "leverage"`, `limit: 5`.
3. Take the first one whose files still exist (search only returns open pins, so none are claimed). If none qualify, say so in one line and stop.
4. Call `get_pin` on it and read the files, gotchas, approach and done-when. If the code has moved on and the pin is already fixed, find the commit that fixed it (`git log` on the file, or `git log -S` with the snippet) and `set_status` it `resolved` with that commit as `fixed_in`. Only if it was fixed with no trace, `dismissed` with a note saying so. Then take the next one.
5. Tell the user in one line which pin you picked and why, then `set_status` it `claimed`.
6. Make the fix on a new branch, keeping to what the pin describes. Run the repo's checks.
7. Open a PR, link it to the pin with `update_pin` (`links: [{ relation: "fixed_in", artifact: <PR URL> }]`), and give the user the link. Once it merges, `set_status` it `resolved`.

Anything else you notice along the way becomes its own pin, not part of this fix.
