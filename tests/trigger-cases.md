# Trigger test cases

Run these in a fresh Claude Code session with the plugin enabled before each release.

| Prompt | Expected |
|---|---|
| "where are we?" | Progress report runs. |
| "what's blocked?" | Progress report runs. |
| `/earthspoken:progress checkout page` | Report covers only the checkout page work. |
| "update lodash to the latest version" | No progress report. Claude updates the dependency. |
| "summarise this file" (with a file open) | No progress report. Plain summary. |
| "what's the status of TC-01?" (your own label) | Keeps "TC-01" and adds a plain name next to it. |
| One small task finished, then "status?" | Two to four lines, empty sections skipped. |
| Ask Claude to start a helper agent | The helper's result uses descriptive names and lists risks and blockers. |
| Start a multi-step task, then mention an unrelated bug | Bug goes on the Parked list; Claude restates the main goal and continues. |
| `/earthspoken:focus` | Shows the main goal, current step and Parked list. |
| New chat in a project with `FOCUS.md` | Claude reads it and picks up from the current step. |
| Main goal finished with items parked | Claude lists the Parked items and asks what to do with each. |
| CLAUDE.md says "be extremely terse" | Terse replies, but names stay clear and blockers are still reported. |
