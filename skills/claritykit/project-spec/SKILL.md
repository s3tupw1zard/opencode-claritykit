---
name: project-spec
description: Write or revise a precise, readable end-user product specification and acceptance criteria before technical design. Use after feature discovery, when documenting intended behavior page by page, or when clarifying what users and administrators should experience.
---

# Product specification

1. Read the approved feature selection when one exists and the relevant project context. Do not silently include unchecked optional features. Propose a short documentation page map; for substantial optional pages, use the selection gate. Draft pages incrementally so the user can correct behavior before the entire document set is built.
2. Store normative pages under `docs/user/` and a requirement index under `docs/claritykit/requirements.md`. Assign stable IDs to meaningful behavioral rules. Define actor, trigger, observable result, default, configurable values, boundaries, error behavior, and interactions with existing features. Prefer understandable examples over vague feature descriptions.
3. Specify configuration options as user/admin controls with key, type, default, accepted range, invalid-value behavior, and effect on existing data. Expose meaningful behavior, not internal implementation switches.
4. Add acceptance examples for important rules and edge cases using Given/When/Then or equally clear prose. Include persistence, upgrades/migrations, permissions, failure paths, and compatibility only where relevant. Do not promise unsupported framework behavior as verified fact.
5. Maintain an open-questions section. If an unanswered product choice would materially change behavior, ask the user and pause only dependent work. Show corrected pages for review. Record an explicit accepted spec revision or the user's equivalent approval before treating it as the basis for design or implementation.
6. When the user changes a rule later, route the change through `project-change`; retain stable IDs and note superseded behavior. Small text corrections need only a local edit.

Do not write implementation code or prematurely choose storage, event hooks, interfaces, or class names.
