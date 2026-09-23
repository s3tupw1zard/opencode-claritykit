---
name: project-implement
description: Implement an accepted product specification and technical design in a bounded, verifiable sequence. Use when coding a planned feature, wiring configuration and integrations, or completing already agreed behavior without inventing product rules.
---

# Implementation

1. Identify the accepted spec and design revisions and the in-scope requirement IDs. If no such artifacts exist for a small fix, use the relevant observable requirement and keep the process proportional. For a substantial new feature with missing product behavior, return to `project-spec`.
2. Inspect existing code and tests before editing. Implement in small coherent slices, including meaningful configuration, validation, data migration, and integration behavior actually required by the accepted scope. Do not turn implementation constants into arbitrary admin settings.
3. Make technical choices within the accepted behavior. If a missing product rule changes the outcome, label it `SPEC GAP`, give understandable choices, and pause dependent work for the user's decision. Do not silently invent a default or replace a selected feature with an optional alternative.
4. Add focused tests for behavior and important edge cases rather than tests that merely repeat internal structure. Run appropriate build, lint, and test checks. Record which requirement IDs were covered and which remain.
5. Hand off to `project-verify` for a comparison of behavior against the spec. Update user documentation only to clarify the agreed behavior; route a desired behavior change through `project-change`.

If OpenCode Conductor is active, its root session owns task/decision state. Do not create a second task list or edit `.conductor/` from a worker.
