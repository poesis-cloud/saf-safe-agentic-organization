# Security Review Template — `products/<product-slug>/.../reviews/<subject>-security-review.md`

Authored by `@security-expert`. The security verdict on a subject (a Story, Feature, ADR, runway item, or PR). One review per subject per attempt; a `fail` records blocking `openItems` the owning step must clear.

```markdown
---
id: <subject>-security-review
subject: <artifact-id-or-path under review>
reviewer: '@security-expert'
verdict: pass            # pass | concerns | fail
created: YYYY-MM-DD
findings: []
openItems: []
---

# Security Review — <subject>

## Subject under review
Link / id. Restate the trust boundary, surface, or change under review.

## Findings
| id | severity | finding | recommendation |
|---|---|---|---|
| F-01 | high | ... | ... |

## Verdict
**PASS** — no blocking security concerns.
*(or)* **CONCERNS** — non-blocking issues recorded as `openItems`.
*(or)* **FAIL** — blocking security defect; subject returns to its owner.

## Recommendations
Remediation guidance, owner, and target.
```

## Lifecycle
One sign-off per subject per attempt. A `fail` lists blocking `openItems`; the next attempt produces `<subject>-security-review-2.md`.
