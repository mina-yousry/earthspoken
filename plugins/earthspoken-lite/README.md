# 🌍 Earthspoken Lite

**Plain-language status reports for Claude.**

Makes Claude talk like a teammate, not a terminal: clear names instead of cryptic IDs ("Test case 1: login with wrong password", never "TC-01"), and progress reports anyone can read in ten seconds.

This is the skills-only edition of [Earthspoken](https://github.com/mina-yousry/earthspoken), built for the Claude directory. It has no hooks, so the rules load when Claude picks up a skill rather than at every session start.

## Install

In Claude Code:

```
/plugin install earthspoken-lite --marketplace mina-yousry/earthspoken
```

## What it does

- **`plain-language` skill:** clear names for tasks, plan steps, helper agents and tests. Keeps the IDs your project already uses and follows your repo's branch and commit conventions. Short, but never drops risks, blockers or decisions needed. Your own CLAUDE.md or style instructions win on tone.
- **`progress` skill:** ask "where are we?" or run `/earthspoken-lite:progress` (optionally with a focus area) for a short report: Done (and how it was verified), In progress, Blocked (and who can unblock it), Risks, Next up, Decisions needed from you.

## Want the rules always on?

The full Earthspoken plugin loads the rules at every session start and gives every helper agent a short version, using two hooks. Install it from its own marketplace in Claude Code:

```
/plugin marketplace add mina-yousry/earthspoken
/plugin install earthspoken@earthspoken
```

Install only one of the two editions.

## Privacy and data

No network calls, no scripts, no hooks, and no data stored. The plugin is Markdown instructions only. Like any prompt, the instructions are sent to Claude as part of your conversation.

## License

[MIT](https://github.com/mina-yousry/earthspoken/blob/main/LICENSE)
