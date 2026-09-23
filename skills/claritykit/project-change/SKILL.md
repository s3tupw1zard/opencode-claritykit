---
name: project-change
description: Propagate an intentional change to existing product behavior, project context, configuration, or compatibility through affected specification, design, code, and tests. Use for new features in an established project, changed rules, changed defaults, and framework or platform changes.
---

# Controlled change

1. Classify the request as TRIVIAL (wording/format), LOCAL (contained default or text), BEHAVIORAL (user-visible rule), or ARCHITECTURAL (new dependency, persistence, public API, platform). Use the smallest process that keeps documents and code aligned. Do not force a full discovery round for a typo.
2. Establish current behavior from the accepted spec and, for an adopted project, code evidence. Describe the desired observable difference and affected users/admins. Ask the user only about material alternatives; decide routine technical details yourself.
3. For meaningful optional extensions, use `project-discovery` and its GitHub selection gate. For a direct, specific requested change, treat the request as selected; do not turn it into an optional checklist merely to delay work.
4. Update the relevant `docs/user/` pages and acceptance criteria first, retaining requirement IDs or explicitly superseding them. Check effects on configuration, persisted data, permissions, integration, and compatibility. Then revise affected `docs/design/` contracts and code, followed by focused tests and `project-verify`.
5. Record the change's scope and affected revisions in `docs/claritykit/changes.md` for substantial work. Mark downstream material stale when its upstream behavior changed; do not claim an old design or implementation proves a new requirement. Preserve unrelated approved behavior.
6. If the request is limited to documentation, stop at documentation. If it requests the behavior implemented, complete the affected code and checks within the authorized scope.
