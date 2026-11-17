---
name: plain-language
description: Plain-language naming and reporting rules. Use whenever you name tasks, plan steps, helper agents or tests; write a plan, a summary or a final report; or brief a helper agent. Also use when the user asks for clearer names, less jargon, or "no cryptic IDs".
---

# Earthspoken: plain-language rules

Write so anyone who just walked in can follow: a product owner, or a developer back from a break.
Assume they know common industry terms, but not the labels made up in this session.

## Names
- Give every task, plan step, helper agent and test a descriptive name that says what it is about.
  Good: "Test case 1: login with wrong password". Bad: "TC-01", "WS-2", "agent_7", "Phase 2b".
- Never invent abbreviations, codes or numbers as names. When you refer back to something, repeat its name.
- Standard terms (PR, CI, API, URL, JSON, SQL) need no explanation. If the user says they are
  non-technical, explain a term the first time it appears.
- Keep IDs the user or project already uses (their numbered list, ticket keys, test names in code).
  Add the plain name the first time one appears.
- Branch names, commit messages and pull request titles follow the repository's own conventions.
- Quote error messages, commands and file paths exactly, in code formatting. Explain them after the quote.

## Brief, never incomplete
- Start with the answer or the result. No filler, no restating the request, no closing recap.
- Never drop risks, blockers, costs, deadlines, decisions needed, anything that broke,
  or anything the user must act on.
- Shorten by removing words, never by turning words into codes.
- Reply in the user's language. Keep code, commands and identifiers unchanged.

## Helper agents
When you start a helper agent, add this to its prompt: give every task, step and test a descriptive name,
never invented codes; keep IDs the project already uses; quote errors, commands and file paths exactly;
in the final report, start with the result, say how it was verified (tested, built only, or not verified),
and always list risks, blockers and decisions needed.

## Progress
For status questions, use the `progress` skill in this plugin (`/earthspoken-lite:progress`).

## Priority
If the user or the project's instructions ask for a different style or level of terseness, follow them.
Two rules still apply: name things clearly, and never drop risks or blockers.
