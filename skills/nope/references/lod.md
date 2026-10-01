# Level of detail (LOD)

## Table of contents

1. Where the idea comes from
2. The levels
3. How LOD drives nope
4. LOD map template
5. First-run setup

## 1. Where the idea comes from

Adapted from the BIMForum Level of Development scale, as described in
"What Is LOD, or Level of Detail?" (engineering.com, 2022). Two ideas carry
over:

- The level is set **per object**, not for the whole model. Here: per
  component or topic of the project.
- The level measures **how far something can be relied on**, not just how
  much detail exists. Here: how deeply the user must understand and own
  that part.

## 2. The levels

| LOD | BIM meaning | The user can... |
|---|---|---|
| 100 | Symbol, generic placeholder | say its purpose in one sentence |
| 200 | Approximate, generic object | explain what it does and its inputs and outputs, roughly |
| 300 | Specific, measured, located accurately | explain how it works, its key parameters, and why those values |
| 350 | Connections between elements | explain how it connects to other parts, and what breaks if it changes |
| 400 | Detail sufficient to fabricate | build or modify it themselves; line-level understanding |
| 500 | Field verified | show they checked it themselves on real runs (tests, measurements) |

Each level includes everything below it.

## 3. How LOD drives nope

- **Routing:** work finer than a component's target LOD is route A. Work
  within the target is the user's: route C if demonstrated LOD reaches the
  target, otherwise route D.
- **Grilling depth:** routes D and E ask down to the target level and no
  further.
- **Clear answers:** an answer must meet the target level's definition.
- **Explanations:** pitch them at the target level.
- **Raising a target:** free; just update the map and log it.
- **Lowering a target:** route E; log the reason.
- **Demonstrated LOD:** rises only when the user answers at that level in a
  grill or quiz; never lower it without evidence. Mirror changes in the
  learner profile.
- **Unlisted components:** target 200, demonstrated 100.

## 4. LOD map template

`docs/lod-map.md` in the project:

```markdown
# LOD map

| Component | Target LOD | Demonstrated LOD | By (milestone) | Notes |
|---|---|---|---|---|
| Component A | | 100 | | |
| Component B | | 100 | | |
| Component C | | 100 | | |

## History
- <date>: created
```

Replace the placeholder rows with the project's components.

## 5. First-run setup

If the map does not exist:

1. Create it from the template with the targets blank, replacing the
   placeholder rows with the project's components. If they are not
   clear from the project, ask the user to name them.
2. Ask the user to set every target with `AskQuestion`, one question per
   component, options `100, 200, 300, 350, 400, 500`, plus Other. Show the
   level table first. **Give no suggested values.**
3. Ask one follow-up round only for any target set at 400 or above: "By
   which milestone?"
4. Write the answers, log "LOD targets set by user" in the decision log,
   and continue routing the original request.
