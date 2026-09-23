---
name: selection-gate-workflow
description: Manage a GitHub Issue feature-selection checklist for ClarityKit discovery or document-page choices. Use to publish selectable proposals, read the user's checkboxes, and freeze a confirmed selection into one execution snapshot before downstream work starts.
---

# GitHub selection gate

## Create a selection round

1. Require a known repository and GitHub Issue read/write access. If unavailable, leave this external workflow pending and explain what is missing. Do not create a second authority such as a spreadsheet.
2. Create exactly one Issue for this round (or continue an existing dedicated Issue). Give each optional candidate a stable unique ID and a separate checkbox. Describe dependencies, conflicts, and concrete consequences below each item. Requested mandatory scope is stated as mandatory, not disguised as an optional checkbox.
3. At the end, separated from all candidate groups, add exactly one unchecked gate: `- [ ] Auswahl abgeschlossen – ausgewählte Punkte umsetzen`. State once that checking this gate approves proceeding with the selected items, subject to normal tool permissions and applicable safeguards. Add the Issue URL to the work summary.
4. While the gate is unchecked, answer questions and edit candidate descriptions as needed. Individual checked candidates alone do not authorize execution. Do not claim that a skill is polling the Issue; a user message to continue causes a fresh read unless a real trigger has been configured separately.

## Consume a confirmed selection

1. Re-fetch the Issue body on resume; never rely on cached checkbox states. Parse only candidate checkboxes with recognized IDs plus the unique completion gate. If the gate is absent, duplicated, or unchecked, remain in selection mode.
2. Before downstream changes, capture the current Issue URL, `updated_at` (if available), selected IDs, dependencies, conflicts, gate state, and a content hash or exact selected checklist text. Record the snapshot in a concise Issue comment or a project document; identify a run ID and start time. Avoid overwriting the user's checklist.
3. Include an unchecked prerequisite only when technically mandatory and document why. Resolve obvious compatible conflicts; otherwise block only affected items and continue independent ones. Never include optional alternatives by implication.
4. Treat the snapshot as fixed during execution. Changes to the Issue after the snapshot belong to a new selection round or revision unless the user explicitly expands this run. GitHub's conversation lock does not make the Issue body immutable; do not present it as a checkbox lock.
5. At completion, map every selected ID to done, blocked, or skipped with a short reason; report the run result in the Issue when write access permits. Preserve the original checks. Do not change the user's gate back to unchecked automatically.

The gate is a selection approval, not a substitute for any separate permission required by a tool or an irreversible action.
