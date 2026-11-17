---
name: progress
description: Progress report on ongoing work, written so a product owner can read it in ten seconds. Use when the user asks for progress or status ("where are we", "what's left", "status update", "what's blocked"). Do not use for updating code or dependencies, or for summarising a single file or document.
argument-hint: "[focus area]"
---

# Progress report

Collect the state of all current work, including every helper agent or parallel task.
If a focus area is given, report only on that: $ARGUMENTS

Use descriptive names for every item, never invented IDs. Keep IDs the user or project already uses,
with the plain name next to them. Link pull requests, files and tickets next to each item.
Use the emoji in the headings below unless the user asked for plain text.

For small or single-task work, give two to four lines and skip empty sections,
but always say if something is blocked or a decision is needed.

## Overall
Start with the main goal in one line (from `FOCUS.md` if there is one), then one or two sentences: are we on track, and what is the most important thing to know?
If there was an earlier report, start with what changed since then.

## ✅ Done
- What was finished, described by its result for the user or the product.
- Say how it was verified: tested, built only, or not verified.

## 🔄 In progress
- What is being worked on, how far along, and what "done" will look like.

## ⛔ Blocked
For each blocker:
- **What is stuck:** plain description.
- **Why:** the cause in plain words.
- **How to unblock:** a concrete action and who should do it (the user, Claude, someone else).

If nothing is blocked, write "Nothing is blocked."

## ⚠️ Risks
- Anything that could break, slip or cost more, even if it is not blocking yet.

## ⏭️ Next up
- The next few items toward the main goal, in order.

## 🅿️ Parked
- Side tasks set aside for later, each with one line of context. Skip if none.

## 🙋 Decisions needed from you
- Questions only the user can answer, each with the options and a recommendation.
  If none, write "No decisions needed right now."

Lead with outcomes and impact, not technical steps. One line per item where possible.
