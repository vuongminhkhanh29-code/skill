# Migration review and readiness

## Scope of this pilot

Two core business workflows, one required quotation-rules dependency, and one new routing-only orchestrator. No installed workflow is revised in this preparation step.

The source main files were read fresh on 2026-10-04 and rechecked on 2026-10-06; no substantive source drift was found (only a trailing blank-line difference in the read API). Published source versions were contract v23, deal management v4, and quotation rules v4. The source package inventory was inspected, including the deal-management reference text. A bounded Drive search also located and read the acceptance/liquidation README in the approved template library. The full source binding set and live tracker were not verified, and no customer workflow was executed.

## Intentional migration adaptations

- Replace seller identity, Drive file IDs, tracker ID, working-customer document identity, and reminder identity with runtime bindings
- Keep all referenced document contents and current state out of GitHub
- Replace named-customer examples with anonymous examples
- Move the named-customer payment exception’s dependency to the current Drive customer record; do not turn it into a universal payment rule
- Preserve the representative-title correction, numerical commercial rules, date rules, safety checks, and workflow handoffs
- Preserve the existing quotation-template selection even where the two designated template filenames say they are old; a filename alone must not select a replacement
- Omit optional source UI metadata and icons from the pilot; no runtime installation or UI-fidelity claim is made
- Add explicit unactivated-pilot gates and dependency disclosures
- Convert the source's historical quotation-Sheet validity assertion into an expected type requiring live verification; retain the native-Doc customer deliverable rule

The profile carries no live values. The actual Drive business-profile document, current identifiers, primary working-document designation, and customer-specific exception record still need verified bindings. Removing those facts from repository text does not remove their functional requirement.

## Actual dependency inventory

### Drafting

- Current Google Drive / Docs / Sheets tooling and relevant authoring guidance: external runtime dependencies
- Rental README, protected templates, current quotation price Sheets, acceptance master, seller profile, and customer records: remain in Drive
- `references/README-BBNTTL.md`: absent from the published source package. A Drive acceptance/liquidation README was located in the approved template library and read; it points to the same acceptance master. Bind this verified candidate only after resolving the acceptance-default conflict below; do not silently treat the broken local reference as complete
- `manage-769robotics-deals` and `769robotics-quotation-rules`: included
- `schedule-769robotics-events`: external installed dependency, not migrated in this pilot
- GPT Workspace add-on/UI access: external dependency for the retained workspace-source-selection mode only, not ordinary drafting. The pilot neither installs it nor verifies its current capabilities; check it before that mode and stop that mode if unavailable, while reporting the access/selection limitation

### Deal management

- `references/tracker-schema.md` and `references/contract-discovery.md`: present and inspected in the source package; not copied to GitHub. Approved Drive locations are not yet bound
- Live tracker, actual customer contracts, customer folders, update history, and existing rental reminder: external live dependencies
- The reference documents contain operational instructions as well as data examples. They cannot be silently omitted. The dependent mode must stop until the approved Drive reference can be read

### Quotation rules

- No bundled reference documents in the source package
- Requires current authoritative VAT information, protected templates, current product/price sources, and relevant customer-specific instructions in Drive

## Existing source-rule conflicts, preserved for review

These were already present across the source workflows. This migration does not choose a new business policy or alter the installed versions.

1. Folder and document naming: the contract workflow prefers customer short name + product models + compact deal dates, while the quotation supplement requires customer + models and quantities + event date + purpose
2. VAT: the contract workflow defaults VAT to 8% unless overridden, while the quotation supplement requires the applicable rate to be verified from current authoritative sources
3. Rental payments: the contract workflow preserves the rental Master’s two-installment structure, while the quotation supplement has an exact 60,000,000 VND before-VAT default of three installments. Customer-specific instructions override defaults, but overlapping default scope needs an explicit resolution
4. Sharing: the contract workflow sets public-link viewer on the duplicate itself and warns against relying on copied permissions; the quotation supplement speaks of inheriting customer-folder sharing. Do not widen folder access or claim inheritance is equivalent without review
5. Missing-field presentation: the contract workflow requires the exact unresolved marker `[CHƯA CUNG CẤP]`; the quotation supplement also permits `[CHƯA XÁC NHẬN]`. Retain source text pending a deliberate policy decision
6. Acceptance outcome: the Drive acceptance/liquidation README defaults to full acceptance, no issues, and unchanged settlement when no exception is supplied. The contract skill requires verified acceptance outcomes and mutually confirmed accepted lines. Do not choose between those policies in a migration or infer actual completion, signature, or payment from document existence

The source contract’s 16:59 default payment due time and its current folder rules remain unchanged in the candidate. Any separately discussed but deferred business-rule changes are outside this migration.

## Readiness gates

Before publishing:
- Confirm the exact repository, owner, and authorized visibility. The user explicitly approved Public publication to `vuongminhkhanh29-code/skill` on 2026-10-06.
- Confirm the connected identity has the needed repository access
- Review the sanitized file list and actual diff
- Keep all source/reference/customer artifacts out of the commit

Before activation or live writes:
- Resolve the affected rule conflicts explicitly without silently editing business semantics
- Bind and verify the Drive business profile, source IDs, reference documents, customer exceptions, and external scheduler dependency
- Resolve the acceptance-default conflict and bind the located Drive guide, or keep that mode disabled pending resolution
- Verify source identities, types, permissions, and required read access
- Run a non-mutating workflow trial with synthetic inputs and current read-only sources
- Obtain explicit activation/install scope; no automatic installation is implied
- Confirm the existing workflow remains available for rollback and do not duplicate reminders

## Verification limit

Local structural and sanitization checks do not establish runtime readiness. This repository publication is a review pilot only. Drive binding verification, installation, live workflow execution, and production status changes have not been performed.
