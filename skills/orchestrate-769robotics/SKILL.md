---
name: orchestrate-769robotics
description: Route a 769 Robotics request among rental deal status, quotation and contract drafting, and the separate event-scheduling workflow. Use for cross-workflow requests or when the appropriate business workflow needs to be selected; do not replace the selected workflow’s own rules.
---

# 769 Robotics business orchestrator

Apply the mode-specific readiness gates in `../../MIGRATION.md`. This routing file does not activate the GitHub deal-management pilot. For rental status grounding use the existing installed manage-769robotics-deals workflow until its separate migration is verified.

## Resolve the request

1. Identify the requested outcome: status/payment update, document deliverable, Calendar draft/change, or a combination.
2. Load the verified Drive business profile through the runtime binding described in `../../profiles/769robotics.example.json`. Resolve relevant source IDs and reference documents there. Leave customer data, templates, product/price data, tracker rows, payment evidence, and audit history in Drive.
3. Use the current user request and verified sources to resolve customer, deal, date, and document identity. Ask one focused question if a consequential ambiguity remains.
4. Apply the reconciled precedence in `../../MIGRATION.md`; stop only for material unresolved task-specific conflicts.

## Route by outcome

- First ground live rental status through the existing installed `manage-769robotics-deals` workflow for in-scope rental deal requests, including new/revised customer rental contracts and event/rehearsal planning. This preserves deal management’s first-routing rule. It does not enroll a quotation or sync unverified facts from a customer document still being drafted; apply the verified post-document handoff below before syncing those new facts.
- Rental status, preparation, signing, deposits, balances, completion, or reminder decisions: use the existing installed `manage-769robotics-deals` workflow first. Read the live tracker and required Drive references before interpreting or changing operational state.
- Quotation, rental/purchase contract, acceptance/liquidation minutes, or customer document organization: use `../draft-769robotics-contract/SKILL.md`. Apply `../769robotics-quotation-rules/SKILL.md` where relevant. Read the exact source templates and current price sources; create or edit only the authorized customer deliverable.
- Event/rehearsal schedule or team Calendar request: use the separately installed `schedule-769robotics-events` workflow. It is an external dependency, not included in this pilot. If it is unavailable, report that blocker; do not invent a replacement scheduling policy.

For an employee with draft-only access, a missing status/scheduler skill blocks only its operational reads/writes or handoff. Independently verified document drafting may proceed with explicit disclosure of unavailable handoffs; never simulate tracker state or schedules.

## Preserve handoff boundaries

- For a verified customer rental contract, finish document readback, placeholder/error scans, and required layout/sharing checks before passing verified contract facts to deal management.
- Preserve the verified contract identity, customer/deal identity, source version, scope, totals/basis, payment terms, event dates/times, and unresolved facts in the handoff. Keep the handoff data in the authorized Drive workflow; do not commit it to this repository.
- Preserve the required scheduler handoff after a verified rental contract. Preparing its Calendar draft is separate from approval to create events or invite recipients.
- A document’s existence does not prove signing, payment, preparation, acceptance, or completion. A project-status update does not authorize document changes, payments, customer outreach, sharing changes, or Calendar writes.
- Do not treat migration, publication, or a workflow name as permission to create schedules, install skills, connect accounts, or expand access.

## Report the result

Report each requested outcome separately: completed and verified, already recorded/no change, partially complete, or blocked with the smallest missing input. Link only verified customer-facing sources. Do not report an unperformed handoff or unresolved dependency as complete.

