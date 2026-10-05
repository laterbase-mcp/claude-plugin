---
name: random
description: Surface one decent open pin at random to break decision paralysis. Use when the user says "surprise me", "random pin" or can't choose.
---

# Random pin

1. Get the repo as `owner/name` from `git remote get-url origin`.
2. Call `search_pins` with that `repo`, `min_leverage: "medium"`, `limit: 30`. If that returns nothing, retry without `min_leverage`.
3. Pick one at random (for example `shuf -n1` over the keys, so it really is random).
4. Call `get_pin` and present it in a few lines: title, why it matters, scope, and the first gotcha.
5. Ask whether to start it. Claim it only if the user says yes.
