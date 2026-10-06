# 769 Robotics skill migration pilot

This is a reviewable, unactivated pilot package for the user-approved public GitHub repository.

## Included

- Contract and quotation drafting workflow
- Rental deal-management workflow
- Quotation-rules dependency
- A small business-workflow orchestrator
- An empty profile binding contract and a migration manifest

The three existing workflows are adapted from the current user-owned skills. Existing business rules are retained, with customer-specific facts removed from repository text and routed to Drive. The orchestrator is new routing glue.

## Storage boundary

GitHub holds workflow instructions and configuration structure. Google Drive remains the source for references, templates, current product/price facts, seller/customer records, customer-specific exceptions, project status, payments, and audit history.

The profile is deliberately empty. It describes the runtime bindings needed from a verified Drive business profile. No private customer document, tracker snapshot, price-sheet export, credential, or reference document is included.

## Status

Repository review pilot. Publication to `vuongminhkhanh29-code/skill` was authorized on 2026-10-06 with its Public visibility explicitly accepted. No installed skill has changed, and no runtime or reminder has been altered.

This is not yet a complete runnable migration. Read [MIGRATION.md](MIGRATION.md) for missing references, unresolved source-rule conflicts, and readiness gates. The existing installed workflows remain in place.

## Layout

- `skills/draft-769robotics-contract/SKILL.md`
- `skills/manage-769robotics-deals/SKILL.md`
- `skills/769robotics-quotation-rules/SKILL.md`
- `skills/orchestrate-769robotics/SKILL.md`
- `profiles/769robotics.example.json`
- `migration-manifest.json`

Publishing these files does not automatically install or activate them. The pilot preserves business workflow content; it does not grant new permissions to an executor. Use only the user-authorized task and the relevant connected services’ current access.

