# Pain Point Template — `art/<art-slug>/improvement-backlog/<pp-slug>/<pain-point-slug>.pain-point.md`

Authored by `@release-train-engineer` (or any agent observing systemic friction). A pain point is a raw, append-only input to the Inspect & Adapt problem-solving workshop. It is triaged there and either resolved as a workflow improvement or converted into a product improvement (Feature / Story).

```markdown
---
id: PP-YYYYMMDD-NN
title: <short symptom statement>
status: open                 # open | triaged | resolved | converted | accepted | duplicate
origin: iteration            # iteration | pi | workflow | cross-product | metrics-review
layer: program               # portfolio | program | team
symptom: <one-sentence observable friction>
impact: <who is affected and how much>
root_cause: null             # filled during I&A problem-solving
resolution: null             # workflow-improvement | product-improvement | accepted | duplicate
target_artifact: null        # file/artifact for workflow improvements
derived_features: []         # filled when resolution = product-improvement
derived_stories: []          # filled when resolution = product-improvement
related_pain_points: []
owner: @release-train-engineer
created: YYYY-MM-DD
---

# PP-YYYYMMDD-NN — <title>

## Symptom
What exactly was observed? Be specific and avoid solution language.

## Impact
- Affected roles:
- Frequency:
- Cost (time, quality, morale):

## Root cause
Filled during the Inspect & Adapt problem-solving workshop (five-whys / fishbone).

## Resolution
- `workflow-improvement` — change a skill / instruction / prompt / orchestrator / template.
- `product-improvement` — create a Feature or Story in the appropriate backlog.
- `accepted` — acknowledged as inherent constraint, no action.
- `duplicate` — superseded by another pain point.

## Target artifact
For workflow improvements: the concrete file or artifact id to change.

## Derived backlog items
For product improvements: links to the created Feature / Story artifacts.

## Related pain points
- PP-...
```

## Lifecycle

1. **Capture** — anyone may append a pain point the moment friction is observed.
2. **Triage** — `@release-train-engineer` triages at Inspect & Adapt, setting `resolution` and `root_cause`.
3. **Resolve or convert** — workflow improvements are implemented and marked `resolved`; product improvements spawn Features/Stories and are marked `converted`.
