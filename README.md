# OpenCode ClarityKit

Specification-first development skills for OpenCode. The skills guide product discovery, user-facing behavior, technical contracts, implementation, verification, debugging, and controlled changes. OpenCode Conductor is optional and works independently.

## Install

From the target project, list the skills:

```sh
npx skills add s3tupw1zard/opencode-claritykit --list
```

Install all skills for OpenCode in the current project:

```sh
npx skills add s3tupw1zard/opencode-claritykit --skill '*' --agent opencode
```

Add `--global` to install them for all your OpenCode projects. The CLI installs each discovered skill into an OpenCode-compatible skill directory. The repository source layout is `skills/claritykit/<skill-name>/SKILL.md`; that source directory itself is not an OpenCode discovery path.

## Skills

| Skill | Purpose |
| --- | --- |
| `project-context` | Set up or update the project's technology and constraints. |
| `project-discovery` | Explore the idea and choose features. |
| `selection-gate-workflow` | Collect feature selections in one GitHub Issue and snapshot the confirmed selection. |
| `project-spec` | Write precise user-facing behavior and acceptance criteria. |
| `project-design` | Check feasibility and define architecture, schemas, and developer contracts. |
| `project-implement` | Implement the agreed behavior in bounded steps. |
| `project-verify` | Compare the product with its requirements and run relevant checks. |
| `project-debug` | Reproduce and fix defects against expected behavior. |
| `project-change` | Propagate a requested behavior change through affected layers. |

Use a normal prompt or load a skill explicitly. A GitHub Issue gate requires a repository and GitHub access; when those are unavailable, discuss the selection in the conversation and do not claim that an external gate was created. Checking the completion box does not trigger a running OpenCode session by itself; ask OpenCode to continue so it can re-read the Issue.

## Principles

- Ask users about observable behavior and meaningful choices, not internal classes or storage APIs.
- Treat user-facing documentation as a behavior contract, with concrete defaults, edge cases, and acceptance examples.
- Make meaningful user/admin behavior configurable; keep internal invariants out of configuration.
- Check changing framework APIs against primary documentation. Separate verified facts from assumptions.
- Keep small edits small. Use the full phase sequence for new behavior or architecture, and apply only the parts needed for a trivial correction.
- Keep each skill usable without Conductor. If Conductor is active, let it own its task and decision state; skills do not create a competing task system.
