# Feasibility Review Template — `products/<product-slug>/.../reviews/<subject>-feasibility-review.md`

Authored by `@developer`. The implementation-feasibility verdict on a subject (a Feature, Story, or enabler) — technical risk, effort realism, dependency exposure, and build viability. One review per subject per attempt; a `fail` records blocking `openItems`.

```markdown
---
id: <subject>-feasibility-review
subject: <artifact-id-or-path under review>
reviewer: '@developer'
verdict: pass            # pass | concerns | fail
created: YYYY-MM-DD
findings: []
openItems: []
---

# Feasibility Review — <subject>

## Subject under review
Link / id. Restate the scope, the proposed approach, and the dependencies under review.

## Findings
| id | severity | finding | recommendation |
|---|---|---|---|
| F-01 | high | ... | ... |

## Verdict
**PASS** — implementation feasible as scoped.
*(or)* **CONCERNS** — non-blocking risks recorded as `openItems`.
*(or)* **FAIL** — blocking feasibility defect; subject returns to its owner.

## Recommendations
Remediation guidance, owner, and target.
```

## Lifecycle
One review per subject per attempt. A `fail` lists blocking `openItems`; the next attempt produces `<subject>-feasibility-review-2.md`.
