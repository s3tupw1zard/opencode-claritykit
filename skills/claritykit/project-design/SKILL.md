---
name: project-design
description: Check feasibility of an accepted product specification and design its architecture, data and configuration contracts, and public developer API before implementation. Use for technical planning, API skeletons, Javadocs or equivalent contracts, and design revisions.
---

# Technical design

1. Read the accepted product spec, relevant acceptance examples, and project context. Verify version-sensitive platform claims with official documentation or a small isolated experiment; cite evidence and mark unknowns. If a requirement cannot be met as written, present the product-visible tradeoff and return it to `project-spec` instead of quietly substituting behavior.
2. Keep a concise design under `docs/design/`: component responsibilities, data ownership and persistence, lifecycle, integration points, concurrency where relevant, error handling, upgrades/migrations, configuration validation, and compatibility. Link design decisions to requirement IDs. Prefer the least complicated structure that covers the agreed behavior.
3. Produce language-appropriate developer contracts before logic: Java interfaces/Javadocs, Python protocols/docstrings, TypeScript types/TSDoc, C# interfaces/XML docs, OpenAPI, CLI command contracts, or configuration schemas. Define inputs, outputs, invariants, errors, and observable side effects. Do not create a public API merely because the language supports one.
4. For configurable behavior, define keys, types, defaults, validation, precedence, and migration of old values. Reconcile each option with the user-facing configuration description.
5. Write a small implementation sequence with verification points, but do not implement business logic in this phase. Review the design against every in-scope requirement and show material technical consequences in plain language. Record the accepted design revision before `project-implement` relies on it.

Treat a revised product spec as a reason to recheck affected design sections; an old approval does not automatically cover new behavior.
