---
name: sweep
description: Before wrapping up, turn the out-of-scope things noticed during this session into pins so nothing is lost. Use at the end of a task, before opening a PR, or when the user says sweep.
---

# Sweep the session

1. Look back over this session for things you or the user noticed but left alone: bugs, debt, flaky tests, missing tests, confusing code, TODOs you added, features asked for but deferred, "not now" decisions.
2. Leave out anything this change already fixes and anything already pinned (check with `pins_near` on the files involved).
3. List the candidates for the user in one line each and ask which to pin. If they say all, pin all.
4. Pin each with `create_pin`: the files and lines, how you found it, gotchas, and honest risk, payoff and scope: rate payoff by who feels it and how often, not by how much it bit you just now. Link it `found_in` the current branch or PR.
5. If `create_pin` reports a likely duplicate, add a sighting to the existing pin with `add_sighting` instead.
6. Reply with the new keys and the sightings added.
