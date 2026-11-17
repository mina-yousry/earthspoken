---
name: focus
description: Keeps work on the main task without dropping side work. Use at the start of multi-step work, when a side task, bug or idea comes up mid-task, when resuming work started in another chat, or when the user says "focus", "what's the main task", "we're getting lost" or "park that". Run directly to set or show the main goal and parked items.
argument-hint: "[main goal, or 'park <item>']"
---

# Focus on the main task

Set or update from the user's words if given: $ARGUMENTS

## Know the main goal
- Hold one main goal in one sentence, in the user's words, with what "done" looks like.
- If the project has a `FOCUS.md`, or the user points to a handoff or plan file, read it before starting.
- If the goal is unclear, ask once. Don't guess.

## Side work: park it, never drop it
When something comes up that isn't the next step toward the main goal (a bug you noticed, a refactor idea,
a question, a follow-up request):
- If it blocks the main goal, or takes a minute and touches the same files, do it now and say so in one line.
- Otherwise, add it to the **Parked** list with a descriptive name and one line of context, and keep going.
- Never silently skip, delete or undo work, whether finished or half done. If you stop something midway,
  park it with where it stopped.
- The user decides what gets dropped. You only park.

## Come back after every detour
After each side task or answer, say in one line what the main goal is and what the next step toward it is,
then do that step.

## Work spread across chats
- When work spans several chats, offer once to keep `FOCUS.md` in the project root: the main goal, done when,
  the current step, and the Parked list. Write it only after the user agrees.
- Once it exists, update it when the goal, the current step or the Parked list changes,
  so the next chat starts from the same place.

## Finish
When the main goal is done, show the Parked list and ask which items to do next, park for later, or drop.

## Format
```
Main goal: <one sentence> (done when: <check>)
Now: <current step>
Parked:
- <descriptive name>: <one line of context>
```
