# Changelog

## earthspoken-lite 1.0.0 (2026-11-17)

- New skills-only edition in `plugins/earthspoken-lite`, for the Claude directory, which accepts hooks only from Verified organizations.
- The plain-language rules are a `plain-language` skill instead of a session-start hook. Helper-agent rules are part of that skill.
- Same `progress` skill, run as `/earthspoken-lite:progress`.
- Adds a listing icon. The full `earthspoken` plugin is unchanged.

## 1.1.0 (2026-11-17)

- Rules now work for developers too, not only product owners. Standard terms like PR, CI and API are no longer explained.
- Keeps IDs you and your project already use, and follows your repo's branch and commit conventions.
- Quotes errors, commands and file paths exactly. Replies in your language.
- Your own CLAUDE.md or style plugin wins on tone. Clear names and risks or blockers always stay.
- Helper agents now get a short version of the rules through a new `SubagentStart` hook.
- Progress report: shows how each item was verified, adds a Risks section, keeps small updates to two to four lines, and supports a focus area (`/earthspoken:progress checkout`).
- The report no longer triggers on "update the dependency" or "summarise this file".
- `/progress` command merged into the `progress` skill. Run it as `/earthspoken:progress`.
- Rules cut from about 420 words to about 280, so they cost fewer tokens each session.
- README: corrected the command name, the team install steps and the privacy note. Added Try it, Update, and Pause or remove sections.
- Added homepage, repository and description fields, a validation workflow, and trigger test cases.

## 1.0.0 (2026-11-17)

- First release: plain-language naming rules, progress report skill, `/progress` command.
