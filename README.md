# nope

An agent skill that keeps you in charge of your own thinking. Before the agent acts, nope sorts each request into one of five routes: do it, grill you on what you want, tell you to do it yourself, guide you with questions, or gate a change until you can defend it. An action guard stops for your yes before anything risky, even when nope is off.

`nope-off` pauses nope until you run `/nope` again.

## Contents

| Path | What it is |
|---|---|
| `skills/nope/` | The nope skill and its references (routing, question banks, LOD) |
| `skills/nope-off/` | The off switch |
| `rules/nope.mdc` | Always-on rule so nope runs on every request |
| `templates/` | Starting files: state, learner profile, LOD map, decision log |
| `GLOSSARY.md` | The terms nope uses |
| `CREDITS.md` | The skills and ideas nope is built on |

## Install (Cursor)

1. Copy `skills/nope` and `skills/nope-off` into `~/.cursor/skills/`.
2. Pick where your state file and learner profile live (somewhere private, outside any repo). Copy `templates/nope-state.md` and `templates/learner-profile.md` there.
3. Fill in the learner profile. How I made mine: a `/grill-me` session on the project, then asked the agent to diagnose my strengths and weaknesses.
4. Replace `<STATE_FILE>` and `<LEARNER_PROFILE>` with those two paths in `skills/nope/SKILL.md`, `skills/nope-off/SKILL.md` and `rules/nope.mdc`.
5. Copy `rules/nope.mdc` into each project's `.cursor/rules/`.
6. On the first request in a project, nope creates `docs/lod-map.md` and `docs/decision-log.md` and asks you to set a target LOD for each component.

## Use

- `/nope`: switch nope on.
- `/nope-off`: switch it off. The action guard and decision log stay on.

Keep your state file, learner profile, LOD maps and decision logs out of this repo.

## Licence

CC BY-NC-SA 4.0, because nope adapts material from HKUSTDial/Supervisor-Skills. See `LICENSE` and `CREDITS.md`.
