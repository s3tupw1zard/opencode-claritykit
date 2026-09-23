---
name: project-debug
description: Reproduce, diagnose, and fix a software defect against the intended or documented behavior. Use for crashes, regressions, unexpected output, data loss, incompatible integrations, and user reports that something works differently than specified.
---

# Debugging

1. Collect the symptom, environment, version, reproduction steps, expected result, and actual result. Inspect logs and the smallest relevant code path. When the expected behavior is already in `docs/user/`, use that rule; when it is genuinely unclear, ask a product-level question before assuming the desired result.
2. Reproduce or build the smallest credible failing case. Trace the cause, distinguish product change requests from defects, and check whether related data or integrations are affected. Do not hide a design or spec mismatch behind a local patch.
3. Apply a focused fix within intended behavior. Add a regression check for a meaningful repeatable failure. Run the relevant checks and state what was actually observed.
4. Update implementation or developer documentation if its explanation was wrong; do not change the user-facing behavior contract merely to make a failing test pass. Route intentional behavior changes through `project-change`.
5. Report cause, fix, verification, and any remaining uncertainty in plain language. For a tiny obvious typo or one-line defect, keep the work proportional.
