---
name: handoff
description: Release the pin you're working on with a note saying exactly where you stopped, so someone else can pick it up. Use when the user stops partway, switches tasks, or asks for a handoff.
---

# Hand off a pin

1. Work out which pin this session was working on (it was claimed earlier in the session, or the branch or PR names it). If unsure, ask.
2. Summarise where things stand: what's done, what's left, the branch and any open PR, and anything learned that the pin doesn't say yet.
3. Add new traps you hit as gotchas with `update_pin`, and link the work: an open or draft PR as `fixed_in`, or a branch with no PR yet as `related` (`links: [{ relation: "related", artifact: <branch>, kind: "branch" }]`).
4. Release the claim with `set_status` `open` and a `note` holding the summary: what's done, what's next, and where the code is.
5. Reply with the pin key and the note.
