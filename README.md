# 🌍 Earthspoken

**Plain-language status reports for Claude Code.**

A [Claude Code](https://code.claude.com/docs) plugin that makes Claude talk like a teammate, not a terminal.
No invented IDs, no made-up acronyms. You get clear names, and status updates anyone can read in ten seconds, whether they're a product owner or a developer.

[![Validate](https://github.com/mina-yousry/earthspoken/actions/workflows/validate.yml/badge.svg)](https://github.com/mina-yousry/earthspoken/actions/workflows/validate.yml)

---

## Before and after

| Without Earthspoken | With Earthspoken |
|---|---|
| "TC-03 failing, WS-2 blocked on T5." | "Test case 3 (login with wrong password) is failing. The checkout work is blocked until the discount fix is merged." |
| "Spawning agent_7 for phase 2b." | "Starting a helper to fix the discount not applying on the checkout page." |
| "Done. Ready for the next part?" | A short report: Done (and how it was verified), In progress, Blocked (and how to unblock it), Risks, Next up, Decisions needed from you. |

## What it does

- **🏷️ Clear names, always.** Tasks, plan steps, helper agents and tests get descriptive names you'll recognise later.
  It keeps the IDs you and your project already use (ticket keys, your own numbered lists). It also follows your repo's branch and commit conventions.
- **📋 Progress reports anyone can read.** Ask *"where are we?"* or run `/earthspoken:progress` to get:
  - ✅ **Done**: described by the result, and whether it was tested, built only, or not verified
  - 🔄 **In progress**: how far along, and what "done" looks like
  - ⛔ **Blocked**: why, how to unblock it, and *who* should do it
  - ⚠️ **Risks**: anything that could break or slip, even if it's not blocking yet
  - ⏭️ **Next up**
  - 🙋 **Decisions needed from you**: with options and a recommendation

  Small updates stay short: two to four lines, with empty sections skipped.
- **✂️ Short, never incomplete.** No filler, but risks, blockers and decisions are never cut.
- **🤝 Plays well with others.** If your CLAUDE.md or another style plugin asks for a different tone, that wins. Two rules always apply: clear names, and risks and blockers are never dropped.
- **🔁 Always on.** The rules load at every session start and again after the conversation is compacted. Helper agents get a short version too.

## Install

Inside Claude Code:

```
/plugin marketplace add mina-yousry/earthspoken
/plugin install earthspoken@earthspoken
/reload-plugins
```

Or from your terminal:

```bash
claude plugin marketplace add mina-yousry/earthspoken
```

```bash
claude plugin install earthspoken@earthspoken
```

## Try it

1. Run `/plugin` and check that **earthspoken** shows as enabled.
2. Start any task, then ask **"where are we?"** or run `/earthspoken:progress`.
3. To focus the report, add a topic: `/earthspoken:progress checkout page`.

## Update

```bash
claude plugin update earthspoken@earthspoken
```

Auto-update is off by default for community marketplaces. Turn it on for `earthspoken` in `/plugin` → Marketplaces to get new versions automatically.

## Roll it out to your team

Add this to your project's `.claude/settings.json` and commit it:

```json
{
  "extraKnownMarketplaces": {
    "earthspoken": {
      "source": { "source": "github", "repo": "mina-yousry/earthspoken" }
    }
  },
  "enabledPlugins": {
    "earthspoken@earthspoken": true
  }
}
```

This makes the marketplace known and marks the plugin as enabled for the project, but it does **not** install it.
Each teammate runs this once, after trusting the project folder:

```bash
claude plugin install earthspoken@earthspoken --scope project
```

## Pause or remove it

| To | Run |
|---|---|
| Pause it | `/plugin disable earthspoken@earthspoken` |
| Turn it back on | `/plugin enable earthspoken@earthspoken` |
| Remove it | `/plugin uninstall earthspoken@earthspoken` |
| Remove the marketplace too | `/plugin marketplace remove earthspoken` |

For team installs, also delete the `earthspoken` entries from `.claude/settings.json`.

## Make it yours

Fork this repo, then edit:

- `plugins/earthspoken/rules/plain-language.md`: the naming and brevity rules.
- `plugins/earthspoken/skills/progress/SKILL.md`: the layout of the progress report. Prefer plain-text headings? Remove the emoji there, or just tell Claude "no emoji".
- `plugins/earthspoken/rules/subagent-context.json`: the short rules given to helper agents.

Install your fork with `/plugin marketplace add <your-github-user>/earthspoken`.

## How it works

```
.claude-plugin/marketplace.json          lists the plugin so people can install it
plugins/earthspoken/
  .claude-plugin/plugin.json             plugin name, version, description
  hooks/hooks.json                       loads the rules at session start and helper-agent start
  rules/plain-language.md                the naming and brevity rules (about 280 words)
  rules/subagent-context.json            the short version for helper agents
  skills/progress/SKILL.md               the progress report (/earthspoken:progress)
tests/trigger-cases.md                   prompts to check the report triggers correctly
```

A `SessionStart` hook reads the rules file into Claude's context (on startup, resume, clear and compaction).
A `SubagentStart` hook gives every helper agent a short version.
The `progress` skill runs when you ask about status, or when you call it directly.

**Privacy:** no network calls and no scripts. The hooks only read local files with `cat`. Like any prompt, the rules are sent to Claude as part of your conversation.

## Contributing

Issues and pull requests are welcome, especially before-and-after examples where Claude still slipped into shorthand.
Check `tests/trigger-cases.md` before opening a pull request. Bump `version` in both `plugin.json` and `marketplace.json` for every release, or users won't get the update.
See [CHANGELOG.md](CHANGELOG.md) for what changed.

## License

[MIT](LICENSE)
