---
name: project-verify
description: Verify that an implementation or project change actually matches its user-facing specification, developer contracts, and acceptance criteria. Use after coding, before release, or for a targeted independent behavior audit.
---

# Verification

1. Determine the scope and load only relevant accepted requirements, acceptance examples, design contracts, code, and tests. If there is no formal spec, state the observable behavior being checked and the evidence source; do not manufacture earlier approval.
2. Map each in-scope requirement ID to implementation evidence, a meaningful test or manual check, and a result: PASS, FAIL, BLOCKED, or NOT TESTED. Check interaction edges, configuration defaults and validation, persistence/migration, and compatibility where relevant.
3. Run practical focused checks such as tests, build, lint, typecheck, or a reproducible manual scenario. Distinguish checks actually run from checks only proposed. A passing build alone is not proof of product behavior.
4. For failures, show expected versus observed behavior and route the defect to `project-debug`. For an impossible or changed requirement, route the product decision to `project-change`; do not quietly rewrite the spec to match code.
5. Update a concise trace in `docs/claritykit/verification.md` for substantial work, with requirement ID, evidence location, check, and status. Report uncovered requirements and environmental limits. Stop once the material risk is adequately checked; avoid repeated broad testing without a concrete reason.
