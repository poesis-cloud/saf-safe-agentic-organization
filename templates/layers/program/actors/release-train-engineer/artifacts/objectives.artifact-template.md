# Objectives Template — `art/<art-slug>/pi-<pi-slug>/objectives.md`

Authored by RTE at PI Planning. One file per product per PI.

```markdown
---
pi: M
product: <product-slug>
start_date: YYYY-MM-DD
end_date: YYYY-MM-DD
capacity_points: 0
committed_features:
  - id: F-12
    title: ...
    planned_bv: 8
    actual_bv: null           # filled at Inspect & Adapt
    status: committed          # committed | in-progress | done | blocked | cancelled
stretch_features:
  - id: F-15
    title: ...
    planned_bv: 5
    status: refined            # refined | in-progress | done | blocked | cancelled
---

# PI-M Objectives — <product>

## PI theme
One sentence framing what this PI delivers.

## Committed Features (with business value 1–10, set by Central Supervisor)

| Feature | Title | Planned BV | Actual BV (filled at I&A) | Status |
|---|---|---|---|---|
| F-12 | ... | 8 | — | committed |

## Stretch Features
| Feature | Title | Planned BV | Status |
|---|---|---|---|
| F-15 | ... | 5 | refined |

## Cross-product dependencies
List Features in other products that this PI depends on (`<other-slug>/F-N`).

## Milestones
- M+0 weeks: ...
- M+N weeks (IP): Inspect & Adapt
```

## Lifecycle

Created at PI Planning; updated at each Iteration boundary; closed at Inspect & Adapt with actual BV filled in.
