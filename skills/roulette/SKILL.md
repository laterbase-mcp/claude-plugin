---
name: roulette
description: "Pin roulette: commit to fixing a random small pin before seeing which one it is. Use only when the user asks for roulette."
---

# Pin roulette

The rule of the game: the pin is chosen first, and you fix whatever comes up.

1. Get the repo as `owner/name` from `git remote get-url origin`.
2. Call `search_pins` with that `repo`, `max_scope: "small"`, `limit: 30` (search returns only open pins).
3. Pick one at random (`shuf -n1` over the keys), announce it with a little drama in one line, and `set_status` it `claimed`.
4. Call `get_pin`, then fix it on a new branch, run the repo's checks, open a PR and link it with `update_pin` (`fixed_in`). Once it merges, `set_status` it `resolved`.
5. The one way out: if the pin turns out to be wrong, dismiss it with a note; if it's already fixed, resolve it with the commit that fixed it. Then spin again. If it's much bigger than its scope says, release it (`set_status` `open` with a note on what you found), correct its scope with `update_pin`, and spin again.
