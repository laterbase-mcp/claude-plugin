# Laterbase for Claude Code

A shared backlog for the out-of-scope work your coding agents find. When your agent finds work outside the task, or you put something off, it pins it with enough context for someone to pick it up cold. Repeats become sightings instead of duplicates, and the next agent working on that code hears what's known about it.

This plugin connects Claude Code to Laterbase. It brings:

- **The MCP server**, which signs in with your Laterbase account.
- **Skills** that drive it:
  - `/laterbase:quick`: Pick the best small pin in this repo and fix it now, end to end. Use when the user wants a quick win, has a few minutes, or says "give me something small".
  - `/laterbase:recommend`: Recommend the three pins most worth doing next in this repo, with a reason for each. Use when the user asks what to work on, what matters most, or for a recommendation.
  - `/laterbase:nearby`: Show pins near the files changed on this branch, and which one this change could close. Use when the user asks what's known about the code they're touching, or before opening a PR.
  - `/laterbase:sweep`: Before wrapping up, pin anything this session left for later that isn't pinned yet, so nothing is lost. Use at the end of a task, before opening a PR, or when the user says sweep.
  - `/laterbase:handoff`: Release the pin you're working on with a note saying exactly where you stopped, so someone else can pick it up. Use when the user stops partway, switches tasks, or asks for a handoff.
  - `/laterbase:triage`: Check older open pins in this repo against the current code, resolving ones already fixed and correcting stale ones. Use when the user asks to clean up, triage or groom the backlog.
  - `/laterbase:epic`: Take the biggest high-payoff pin and break it into a plan of smaller linked pins instead of attempting it in one go. Use when the user wants to tackle something big or asks for an epic.
  - `/laterbase:standup`: A three-line backlog standup: what was pinned, what's in flight and what got fixed recently. Use when the user asks for a standup, a recap, or what happened in the backlog.
  - `/laterbase:random`: Surface one decent open pin at random to break decision paralysis. Use when the user says "surprise me", "random pin" or can't choose.
  - `/laterbase:roulette`: Pin roulette: commit to fixing a random small pin before seeing which one it is. Use only when the user asks for roulette.
- **A reminder** with every prompt of when to pin, so deferred work is pinned without you asking.

## Install

```sh
claude plugin marketplace add \
  https://laterbase.dev/claude-code/marketplace.json
claude plugin install laterbase@laterbase
```

Then open `/plugin`, pick the laterbase server and press Enter to sign in. A free account is created the first time you sign in.

## Learn more

- [Docs](https://laterbase.dev/docs/plugin)
- [Privacy Policy](https://laterbase.dev/privacy)
- [Terms of Service](https://laterbase.dev/terms)

## License

MIT
