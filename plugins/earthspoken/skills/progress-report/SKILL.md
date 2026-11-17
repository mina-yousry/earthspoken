---
name: progress-report
description: Use whenever the user asks for progress, status, an update, "where are we", "what's left", or a summary of work across tasks, chats or subagents. Produces a report written for a product owner.
---

# Progress report for a product owner

Collect the state of all work (including every subagent or parallel task you manage),
then report in this exact structure. Use full descriptive names for every item,
never IDs or abbreviations.

## Overall
One or two sentences: are we on track, and what is the single most important thing
the user should know?

## ✅ Done
- What was finished, described by its result for the product or the user.
  Example: "Users can now reset their password by email."

## 🔄 In progress
- What is being worked on, roughly how far along, and what "done" will look like.

## ⛔ Blocked
For each blocker:
- **What is stuck:** plain description.
- **Why:** the cause in non-technical words.
- **How to unblock:** a concrete action, and WHO should do it (the user, Claude,
  someone else). If the user can unblock it, say exactly what to do or decide.

If nothing is blocked, write "Nothing is blocked."

## ⏭️ Next up
- The next few items, in order.

## 🙋 Decisions needed from you
- Questions only the product owner can answer, each with the options and your
  recommendation. If none, write "No decisions needed right now."

Rules:
- No abbreviations, codes or invented labels.
- Lead with outcomes and impact, not with the technical steps taken.
- Keep it scannable: one line per item where possible.
