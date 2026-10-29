# 769 Robotics shared business skills

GitHub is the canonical instruction source. Google Drive holds templates, references, customer documents, prices, project state and private business-profile values.

## Workflows

- [Contract and quotation drafting](skills/draft-769robotics-contract/SKILL.md)
- [Quotation rules](skills/769robotics-quotation-rules/SKILL.md)
- [Business orchestrator](skills/orchestrate-769robotics/SKILL.md)
- [Deal-management pilot](skills/manage-769robotics-deals/SKILL.md), not activated by contract setup

Contract rules are reconciled; each runtime must bind its own private Drive profile and pass the [mode-specific checks](MIGRATION.md). The [example profile](profiles/769robotics.example.json) is a schema, not working data.

Customer document filenames and Drive titles must omit `DỰ THẢO` / `draft` labels, including during preparation. Use the canonical customer/model/date naming pattern in the contract skill. Keep draft and signing status in the operational records; naming does not prove approval, signing, payment, or completion.

## Editable quotations

Create detailed rental/sales and comparison quotations as separate customer-specific native Google Sheets with editable prices, native optional-add-on checkboxes, and formulas for totals, VAT and installments. Apply the [editable quotation table rules](skills/draft-769robotics-contract/references/editable-quotation-tables.md). Package charges apply once at their confirmed scope; each alternative option has its own total. Keep source templates and price Sheets unchanged. Docs/PDFs are static snapshots; contracts and acceptance minutes remain native Docs.

## Rental payment schedule

Apply the same rental payment schedule in quotations and contracts. Use three installments (50% deposit on confirmation / 30% supplementary deposit at the confirmed rehearsal or intermediate milestone before the main performance / 20% balance after completion) ONLY when BOTH conditions hold: (1) more than 2 confirmed deployment days, including scheduled rehearsal days; AND (2) total value before VAT strictly exceeds VND 100,000,000. Otherwise use two installments: 50% deposit on confirmation / 50% balance after completion. Exactly 2 days or exactly VND 100,000,000 does not qualify. This supersedes the old OR/multiple-event trigger and abolishes the exact-VND60m exception. Do not infer missing days or values; preserve unconfirmed inputs and ask only when necessary to choose the schedule. For a qualifying three-installment case, confirm the intermediate milestone rather than inventing one. Calculate installment amounts from the VAT-inclusive total.

## Onboard an agent using this repository

Give your agent this prompt together with this repository URL:

> Set up the 769 Robotics contract skill from this repository in my current agent environment. First read README.md, MIGRATION.md, the profile schema, and skills/draft-769robotics-contract/SKILL.md. Inspect the current supported skill-installation mechanism for this environment. Show the exact local/cloud destination and the files you propose to change; preserve existing customizations and obtain any required installation approval. Install a small GitHub-first routing entry, not a disconnected copy of the drafting rules. On every contract task, retrieve the approved GitHub version, check the current default-branch changes, and identify the revision used. Do not silently fall back to an older local copy if GitHub is unavailable. Do not run repository scripts without inspection and the necessary authorization. Connect my own authorized Google Drive account, then ask my administrator for the approved private business-profile link and only the specific template/customer-folder access needed for my role. Never put profile values, customer records, source references, prices, payments, credentials, or private notes in this repository. Check all required bindings and business-rule decisions for the requested mode. Run a read-only trial with synthetic inputs. Report installation, GitHub retrieval, Drive access and drafting readiness separately, including anything still blocked. Do not create a customer document, change sharing, send documents, or install unrelated skills during onboarding.

A repository link alone does not install a skill, grant Drive access, or override the agent platform's confirmation requirements. The agent must support repository reads and an installation mechanism. Chat-only environments may be able to retrieve instructions for the current task without persistent installation; report that accurately. Installing a routing entry does not automatically synchronize every device.

Use each employee's own accounts. Department repositories and least-privilege Drive access can be added later; no department-level permissions are established by this README.

The owner's cloud entry and each employee/device are separate installations. Report current runtime verification honestly; a README alone is not proof of installation. Never publish private profile values or source IDs here.
