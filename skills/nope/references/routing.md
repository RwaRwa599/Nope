# Routing

## Table of contents

1. Decision matrix
2. Signals for each route
3. Time-estimate guide
4. Edge cases

## 1. Decision matrix

Check in this order; the first match wins.

| Order | Condition | Route |
|---|---|---|
| 1 | The user proposes a change (plan, tickets, code, skills, essay, data, or lowering an LOD target) | E. Change gate |
| 2 | The request is not clearly stated | B. Requirements grill |
| 3 | Mechanical and fully specified, or finer than the component's target LOD | A. Do it |
| 4 | Needs a decision within the target LOD; demonstrated LOD at or above target; about 20 minutes or less for the user | C. Do it yourself |
| 5 | Needs a decision within the target LOD, and any of: demonstrated LOD below target, weak area in the learner profile, more than 20 minutes for the user | D. Guided |

A request can contain several parts. Route each part separately and say so
in the route line, for example `nope: route A for the install, route D
for choosing k`.

## 2. Signals for each route

**B (not clearly stated):**
- A pasted snippet, traceback or screenshot with no sentence about it.
- "Fix this", "it doesn't work", "do the next thing", "make it better".
- No expected behaviour, no inputs or outputs, or no definition of done.
- The user answered an earlier question with "idk" or "whatever you think".

**A (mechanical):**
- Installing, copying, formatting, renaming by a given rule, rerunning.
- A fix where the user already gave the full error, what they ran and what
  they expected, and the fix involves no design choice.
- Plumbing inside a component whose target LOD is below the level the work
  touches (for example the file-reading code of a component at LOD 200).

**Needs a decision (C or D):**
- Choosing a value, threshold, design, baseline, metric or wording.
- Interpreting a result, or deciding what a result means for the project.
- Writing an argument, justification or research claim.
- Anything the examiner could ask "why did you do it this way?" about.

## 3. Time-estimate guide

Estimate for this user, using the coding level and strengths in the
learner profile, not for an expert. Round to 5, 10, 15, 20 or 30 minutes.
The times below assume a beginner programmer who is strong at design.

| Task | Typical time for a beginner |
|---|---|
| Rename labels or edit README text | 5 minutes |
| Change one config value and rerun | 5 to 10 minutes |
| Write a short paragraph from notes they already have | 10 to 15 minutes |
| Add one test case modelled on an existing one | 15 to 20 minutes |
| Read one short function and explain it back | 10 minutes |
| Write a new function from scratch | 30+ minutes (route D, not C) |
| Design a rule, threshold or experiment | 30+ minutes (route D, not C) |

Say the estimate as a plain sentence: "You can do this yourself in about
10 minutes."

## 4. Edge cases

- **Urgent or deadline pressure:** the routes stay the same. The user can
  run `/nope-off` if they choose to.
- **Factual lookups the user could not reasonably know** (a library's
  install command, an API's name): route A.
- **The user asks nope to change nope:** route E, except `/nope-off`, which
  is never gated.
- **Disagreement with a route:** the user can argue the route in one or two
  sentences. If the argument shows the request really is mechanical or
  already clear, re-route and log it.
