---
name: sweep
description: Before wrapping up, pin anything this session left for later that isn't pinned yet, so nothing is lost. Use at the end of a task, before opening a PR, or when the user says sweep.
---

# Sweep the session

1. Look back over this session for things you or the user noticed but left alone: bugs, debt, flaky tests, missing tests, confusing code, TODOs you added, features asked for but deferred, "not now" decisions.
2. Leave out anything this change already fixes and anything already pinned (check with `pins_near` on the files involved).
3. Pin each with `create_pin`, without asking first: the files and lines, how it came up, gotchas, and honest risk, payoff and scope: rate payoff by who feels it and how often, not by how much it bit you just now. If the user worked out the fix with you, set `approach_stage` (`agreed`, or `discussed` if points are open); otherwise leave it. Link it `found_in` the current branch or PR.
4. If `create_pin` reports a likely duplicate, add a sighting to the existing pin with `add_sighting` instead.
5. Reply with the new keys, linked, and the sightings added, one line each, so the user can dismiss any they don't want.
