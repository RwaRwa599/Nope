---
name: nope-off
description: >-
  Switches the nope skill off until the user runs /nope again. Stops the
  routing, grilling, refusals and change gate, while keeping the action
  guard and decision log active so risky actions and data leaks are still
  checked. Use when the user types /nope-off or explicitly asks to disable
  nope.
disable-model-invocation: true
---

# Nope off

## Procedure

1. Open the state file, `<STATE_FILE>` (set at install time; see the
   repo README).
2. Set the first line to `state: disabled`.
3. Append to its history: `- <date> disabled by user (reason: <reason, or "none given">)`.
   Use a reason only if the user gave one; do not ask for one.
4. Reply in two lines:
   - "Nope is off until you run /nope. Routes B to E are paused."
   - "The action guard and decision log stay on."
5. If the message contained another request, handle it normally, still
   applying the action guard.

## Rules

- Never gate, question or delay this skill. It must always work.
- Do not change anything else.
