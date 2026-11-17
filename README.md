# 🌍 Earthspoken

**Claude, in Earth language.**

A [Claude Code](https://docs.claude.com/en/docs/claude-code) plugin that makes Claude talk like a teammate, not a terminal.
No cryptic IDs, no invented acronyms, no wall of jargon — just clear names and status updates a product owner can read in ten seconds.

---

## Before and after

| Without Earthspoken | With Earthspoken |
|---|---|
| "TC-03 failing, WS-2 blocked on T5." | "Test case 3 (login with wrong password) is failing. The checkout work is blocked until the discount fix is merged." |
| "Spawning agent_7 for phase 2b." | "Starting a helper to fix the discount not applying on the checkout page." |
| "Done. Ready for the next part?" | A structured report: Done, In progress, Blocked (and how to unblock it), Next up, Decisions needed from you. |

## What it does

- **🏷️ Clear names, always.** Tasks, subagents, plan steps and tests get descriptive names you'll recognise later.
  "Test case 1: login with wrong password", never "TC-01".
- **📋 Product-owner progress reports.** Ask *"where are we?"* or run `/progress` and get:
  - ✅ **Done** — described by the result for the user
  - 🔄 **In progress** — how far along, and what "done" looks like
  - ⛔ **Blocked** — why, how to unblock it, and *who* should do it
  - ⏭️ **Next up**
  - 🙋 **Decisions needed from you** — with options and a recommendation
- **✂️ Short, never incomplete.** No filler or repetition, but risks, blockers, costs and decisions are never cut.
- **🔁 Always on.** The rules load at the start of every session and again after the conversation is compacted, so Claude doesn't drift back into shorthand.

## Install

Inside Claude Code:

```
/plugin marketplace add mina-yousry/earthspoken
/plugin install earthspoken@earthspoken
```

Then restart Claude Code.

Or from your terminal:

```bash
claude plugin marketplace add mina-yousry/earthspoken
claude plugin install earthspoken@earthspoken
```

## Use it

| You type | You get |
|---|---|
| `/progress` | A full product-owner progress report on all current work, including subagents. |
| `/progress checkout only` | The same report, focused on what you asked about. |
| "where are we?" / "what's left?" | The report kicks in automatically. |
| Anything else | Plain-language answers with clear names — no setup needed. |

## Roll it out to your whole team

Add this to your project's `.claude/settings.json` and commit it.
Teammates who trust the project folder are prompted to install it automatically:

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

## Make it yours

Fork this repo, then edit:

- `plugins/earthspoken/rules/plain-language.md` — the naming, tone and brevity rules.
- `plugins/earthspoken/skills/progress-report/SKILL.md` — the layout of the progress report.

Install your fork with `/plugin marketplace add <your-github-user>/earthspoken`.

## How it works

```
.claude-plugin/marketplace.json        lists the plugin so people can install it
plugins/earthspoken/
  .claude-plugin/plugin.json           plugin name, version, description
  hooks/hooks.json                     loads the rules at every session start
  rules/plain-language.md              the naming and tone rules
  skills/progress-report/SKILL.md      the product-owner report format
  commands/progress.md                 the /progress command
```

A `SessionStart` hook prints the rules into Claude's context when a session starts (and after compaction).
The `progress-report` skill triggers on status questions, and `/progress` asks for the report directly.
No scripts run beyond a single `cat` of the rules file, and nothing leaves your machine.

## Uninstall

```
/plugin uninstall earthspoken@earthspoken
```

## Contributing

Issues and pull requests are welcome — especially before/after examples where Claude still slipped into shorthand.

## License

[MIT](LICENSE)
