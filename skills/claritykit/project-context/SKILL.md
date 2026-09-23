---
name: project-context
description: Initialize or update a project's technology profile, platforms, frameworks, build system, supported versions, configuration policy, and constraints. Use for a new project setup, adopting an existing project, or changing project technology or compatibility targets.
---

# Project context

1. Locate the project root and existing profile. Ask what the user wants to create when no goal is given; accept an initial plain-language description. For an existing repository, inspect build files and relevant documentation before asking for facts already visible.
2. Record a small, durable project profile at `docs/claritykit/project-context.md`: name and purpose; language and runtime; platforms/frameworks and pinned or supported versions; build/package system; distribution and target environment; important integrations and constraints; policy that meaningful user/admin behavior is configurable. Use `unknown` for unresolved facts; mark inferred values as inferred. Do not invent version numbers or put feature-specific defaults here.
3. On adoption, distinguish observed behavior, documented claims, inferred intent, and unknowns. Surface contradictions in terms of user-visible effects. Never silently replace an existing product decision with inferred code behavior.
4. On update, make a focused impact map listing affected specifications, design contracts, dependencies, tests, and implementation. Check changing ecosystem/version claims against official sources before relying on them. Update only verified project facts and affected documents within the user's requested scope.
5. Summarize the profile and outstanding product choices in ordinary language. For a material choice that changes the result, obtain the user's answer before dependent work.

Keep the profile independent of OpenCode Conductor. If Conductor is active, leave its own `.conductor/` state to the plugin and the root session.
