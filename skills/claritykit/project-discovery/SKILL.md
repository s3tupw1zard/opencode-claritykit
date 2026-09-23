---
name: project-discovery
description: Turn an early software idea into a manageable set of optional capabilities and product decisions before writing a specification or code. Use when exploring a new project or feature, comparing possible behavior, or preparing a feature checklist for the user to select.
---

# Project discovery

1. Start from the user's plain-language goal. If missing, ask what they want to create. Read the project context if one exists. Separate requirements already requested from optional ideas; do not treat suggestions as selected.
2. Describe candidate features in terms of what users and administrators can observe. Use short stable IDs, category, one-sentence benefit, and clear dependencies/conflicts. Include the real-world edge cases that materially change behavior. Avoid deciding APIs, classes, databases, or plugin events here.
3. Group related decisions so the user can reason about them without a huge questionnaire. Explain a recommendation briefly when useful. Ask about meaningful product differences rather than technical implementation preferences.
4. When GitHub access and a repository are available, load `selection-gate-workflow` and create one GitHub Issue for this selection round. Keep the checklist as the sole authoritative selection source. If no GitHub repository/access exists, provide a provisional list in the conversation and explicitly leave the GitHub selection gate pending; do not pretend a checkbox was created.
5. While the gate is unchecked, refine descriptions and answer questions; do not implement optional candidates. Once the user asks to continue, re-read the Issue and follow the gate skill's snapshot procedure. Deliver selected behavior to `project-spec` with IDs and unresolved questions.

For a clearly requested fix or tiny edit, do not impose a feature-selection round.
