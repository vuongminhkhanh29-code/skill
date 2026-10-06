---
name: draft-769robotics-contract
description: Safely draft and revise 769Robotics detailed rental or sales quotations, rental or purchase contracts, and acceptance/liquidation minutes from the approved Google Drive template library; organize customer document folders and hand verified document facts to the separate deal-operations workflow. Use when the user asks to draft, create, revise, or prepare these customer documents or organize their Drive deliverables. Do not use for payment recording, stage changes, operational notes, deal closure, or dashboard-only updates.
---

# Draft 769Robotics Contract

Pilot candidate only. Do not activate or use for live writes until the readiness gates in `../../MIGRATION.md` pass. Load `../../profiles/769robotics.example.json` as the binding contract, not as live source data.

Protect the source library while creating customer-specific contracts and selecting supported workspace sources.

## Canonical seller representative

- Read the seller legal identity and representative name from the verified Drive business profile; never infer them from a previous customer file.
- Preserve the current representative title `Giám đốc`. Never reuse the former title `Giám đốc kinh doanh` from an older template, quotation, draft, or example.

## Drive locations

Resolve each source from the verified Drive business profile described in `../../profiles/769robotics.example.json`. Read back the resource's identity, type, and access before using it. Empty bindings are blockers, never permission to choose a lookalike file.

- `drive.document_root`: main business-document folder
- `drive.customer_quotation_root`: customer-quotation destination
- `drive.customer_contract_root`: customer-contract destination
- `drive.rental_template_library`: protected rental-contract template library
- `drive.rental_template_readme`: rental-template operating guide
- `drive.acceptance_template`: native acceptance/liquidation master, retained inside the rental-template library and duplicated only
- `references.acceptance_minutes_guide`: required acceptance/liquidation reference; read it before this mode

Reference contents and customer records live in Drive. This repository does not supply missing references. See `../../MIGRATION.md` for unresolved bindings and source conflicts.

## Customer subfolder organization

- Store every customer deliverable inside a customer-specific subfolder under the applicable quotation or contract destination; do not place completed customer files directly in the destination root.
- Name the subfolder so a person can recognize the customer, products, and relevant deal or event dates at a glance. Exact global uniqueness is not required; practical recognizability is the goal.
- Prefer `[CUSTOMER SHORT] - [PRODUCT MODELS] - [COMPACT DATES]`, for example `CUSTOMER - MODEL A, MODEL B - COMPACT DATES`. Use the established short customer name or abbreviation, exact recognizable product models, and only the dates that materially distinguish the deal.
- Do not use a full legal entity name such as `CÔNG TY TNHH ...` merely because it appears in the customer document. Avoid generic customer-only folders when the product or event is known.
- Keep names concise. Preserve recognizable model capitalization; omit quantity, year, location, or transaction detail when it does not improve retrieval. If dates are unknown, use `[CUSTOMER SHORT] - [PRODUCT MODELS]`; if products are unknown, use the shortest established customer identity plus another known deal cue.
- Before creating a subfolder, list the applicable destination and compare customer abbreviations, product models, and deal dates. Reuse an existing folder when it is clearly the same deal, even if its wording is not identical. Create a separate recognizable folder when the products, dates, or deal context materially differ. Do not require a globally unique folder name or expand it into a full legal name solely to force uniqueness.
- Keep the single rental Master and its README in the dedicated rental-contract template library. Keep other canonical templates, retired templates, and general product-reference material directly in the applicable destination root unless the user explicitly requests another library structure.
- A customer may have separate same-named subfolders under the quotation and contract destinations. Keep quotations in the quotation-side folder; keep contracts, appendices, handover records, and acceptance records in the contract-side folder.
- When moving an existing file, verify its current parent, add the verified customer subfolder, remove only the verified destination-root parent, preserve unrelated parents and sharing, and read back every affected folder.
- Rental quotation document template: `MẪU CŨ - KHÔNG DÙNG - BẢNG BÁO GIÁ CHO THUÊ (GOOGLE DOCS)`
  - ID: `profile.drive.rental_quotation_template.file_id`
  - Type: native Google Doc
  - Despite its retained filename, treat this file as the canonical rental-quotation document template until the user identifies a replacement.
- Sales quotation document template: `MẪU CŨ - KHÔNG DÙNG - BẢNG BÁO GIÁ BÁN CHI TIẾT (GOOGLE DOCS)`
  - ID: `profile.drive.sales_quotation_template.file_id`
  - Type: native Google Doc
  - Despite its retained filename, treat this file as the canonical sales-quotation document template until the user identifies a replacement.
- Rental quotation price source: `MẪU - BẢNG BÁO GIÁ CHI TIẾT - CHO THUÊ ROBOT - 769 ROBOTICS`
  - ID: `profile.drive.rental_price_sheet.file_id`
  - Type: native Google Sheet
- Sales quotation canonical price source: `MẪU - BẢNG BÁO GIÁ CHI TIẾT - BÁN ROBOT - 769 ROBOTICS`
  - ID: `profile.drive.sales_price_sheet.file_id`
  - URL: `profile.drive.sales_price_sheet.url`
  - Price-list tab GID: `profile.drive.sales_price_sheet.price_tab_gid`
  - Type: native Google Sheet
- Rental contract Master: `MẪU MASTER - HỢP ĐỒNG CHO THUÊ ROBOT VÀ DỊCH VỤ KỸ THUẬT - 769 ROBOTICS`
  - ID: `profile.drive.rental_contract_master.file_id`
  - URL: `profile.drive.rental_contract_master.url`
  - This is the only rental-contract template. Never select a rental template based on the robot's supplier, owner, or source.
- Purchase contract template: `MẪU - HỢP ĐỒNG - MUA BÁN ROBOT - 769 ROBOTICS`
  - ID: `profile.drive.purchase_contract_template.file_id`
  - Type: native Google Doc

## Canonical template routing and names

Use the two quotation templates, the purchase-contract template, and the single rental-contract Master:

1. Call `bảng báo giá chi tiết cho thuê` -> duplicate the canonical rental quotation document template as a native Google Doc.
2. Call `bảng báo giá chi tiết bán` or `bảng báo giá chi tiết mua` -> duplicate the canonical sales quotation document template as a native Google Doc.
3. Call `hợp đồng cho thuê` or `hợp đồng thuê` -> read the rental README, then duplicate the single approved rental Master as a native Google Doc. Do not ask who owns or supplies the robot and do not route by source.
4. Call `hợp đồng mua bán` or `hợp đồng bán` -> duplicate `MẪU - HỢP ĐỒNG - MUA BÁN ROBOT - 769 ROBOTICS` as a native Google Doc.
5. Call `biên bản nghiệm thu`, `biên bản thanh lý`, or `biên bản nghiệm thu và thanh lý` -> read the Drive reference bound by `profile.references.acceptance_minutes_guide`, then duplicate the approved acceptance/liquidation template as a native Google Doc. Keep the master unchanged.

Always deliver a newly requested customer `bảng báo giá chi tiết` as a native Google Doc. Use the two designated quotation Docs above even though their current Drive filenames begin with `MẪU CŨ - KHÔNG DÙNG`; that filename prefix does not disqualify these two specifically identified canonical quotation templates. Continue using both quotation Sheets only as current product and price sources, never as the customer-facing quotation deliverable.

Name customer deliverables consistently:

- Rental quotation: `BÁO GIÁ CHI TIẾT - CHO THUÊ - [KHÁCH HÀNG] - [SỐ LƯỢNG + SẢN PHẨM] - [DD.MM.YYYY]`
- Sales quotation: `BÁO GIÁ CHI TIẾT - BÁN - [KHÁCH HÀNG] - [SỐ LƯỢNG + SẢN PHẨM] - [DD.MM.YYYY]`
- Rental contract: `HỢP ĐỒNG - CHO THUÊ - [KHÁCH HÀNG] - [SỐ LƯỢNG + SẢN PHẨM] - [DD.MM.YYYY]`
- Purchase contract: `HỢP ĐỒNG - MUA BÁN - [KHÁCH HÀNG] - [SỐ LƯỢNG + SẢN PHẨM] - [DD.MM.YYYY]`

Use uppercase customer and product names in filenames. Use a two-digit quantity such as `01` or `02`. Omit the product segment only when no product has been identified.

## Single rental Master rule

- Use only the rental Master identified above for every customer rental contract.
- Do not identify, ask for, validate, record, or disclose the robot's supplier, owner, source partner, upstream price, or upstream payment obligation as part of this drafting workflow.
- Do not use historical supplier-specific contracts to select or alter the customer template.
- Treat the Master and README as protected sources. Duplicate only; never edit them while creating a customer contract.

## Mandatory real-time product information check

- Before drafting or revising any contract or quotation containing product information, read both canonical quotation Sheets on the same calendar day as the draft, using the user's local timezone. Do not rely on a prior read, cached value, older contract, customer quotation, example, or memory.
- Match the exact product and variant, including model suffixes and editions such as `G1 U2 Plus`. Do not substitute data from a similar model.
- Verify every applicable product field available in either sheet, including product name, model/variant, purchase price, rental price, discount or promotional price, warranty period, VAT treatment, included accessories or services, and other commercial terms.
- Use the purchase sheet as authoritative for purchase pricing and purchase terms, and the rental sheet as authoritative for rental pricing and rental terms. Use the most specific current entry for the exact product variant.
- Cross-check shared product attributes, especially the warranty period, across both sheets. For example, when the current source specifies a warranty period for the exact variant, reproduce that period exactly.
- Record the source file, tab or range, and check date for the values used. Read back the relevant cells before writing them into the duplicate.
- If either sheet cannot be read that day, the exact product is absent, a required value is blank, or the sheets conflict, do not guess or silently reuse older information. Keep the field as `[CHƯA CUNG CẤP]` when appropriate and report the missing or conflicting source data to the user before finalizing the draft.
- When the exact product and price are present in the current canonical Sheet, use them directly. Do not ask the user to reconfirm or approve the price, VAT calculation, or total before drafting; the team will review commercial values later if needed.

## Customer working documents

Resolve an existing customer working document from the exact user-provided link or the verified Drive customer-document registry. Preserve the registry's primary-document designation until the user identifies a replacement. Do not infer document identity from a filename alone. Customer names, working-document links, and record-specific exceptions are not stored in this repository.

## Detailed quotation workflow

1. Ground the customer-quotation folder and the exact canonical rental or sales quotation Doc with Drive metadata before any write.
2. Read both canonical quotation Sheets for the mandatory real-time product check.
3. Duplicate the selected canonical quotation Doc. Never use a Google Sheet as the customer-facing detailed quotation.
4. Give the duplicate its customer filename using the canonical naming convention.
5. Find or create the recognizable customer/deal subfolder inside `Bảng báo giá cho Khách hàng` using the customer-short + products + compact-dates rule, then move the duplicate into it. Add the verified destination parent and remove only the duplicate's verified previous parent. Preserve unrelated parents.
6. Verify the duplicate is a native Google Doc inside the intended recognizable customer/deal subfolder before editing its content.
7. Edit only the duplicate. Preserve its tables, paragraphs, images, headers, footers, formatting, and print layout unless the user's requested content requires a scoped change.
8. Set the duplicate's link access to `Anyone with the link` and role to `Viewer`.
9. Read back the complete document, Drive metadata, file type, destination parent, and sharing state before reporting completion.

## Contract drafting workflow

1. Ground the customer-contract folder and the exact purchase contract or single rental Master Doc with Drive metadata before any write. For a rental, also ground the rental-template library and README.
2. Read the template and collect the customer-specific facts needed for the draft. Do not modify the template.
3. Duplicate the template. Give the copy a customer-specific draft title.
4. Find or create the recognizable customer/deal subfolder inside `Hợp đồng cho Khách hàng` using the customer-short + products + compact-dates rule, then move the duplicate into it. Add the verified destination parent and remove only the duplicate's verified previous parent. Preserve unrelated parents.
5. Verify that the duplicate is a native Google Doc inside the intended recognizable customer/deal subfolder before editing contract content.
6. Edit only the duplicate. Preserve the source template and every other item in the main folder.
7. Set the duplicate's link access to `Anyone with the link` and role to `Viewer`. Apply this permission to the duplicate itself; do not rely on template permissions being copied.
8. Verify the duplicate's effective link access is public-link viewer. Domain-only access such as `Anyone at company` is not equivalent and must not be reported as public-link access.
9. Run the mandatory placeholder audit below and resolve every field supported by the available facts.
10. Run the mandatory final error scan below, repair every deterministic in-scope error, and scan the settled document again.
11. Read back the duplicate, its Drive metadata, and its sharing state. Report the verified document URL, destination folder, link-access status, every repaired error, every unresolved risk or missing item, and whether the final scan passed.

## Acceptance and liquidation minutes workflow

1. Read the Drive reference bound by `profile.references.acceptance_minutes_guide` and the current native Google Docs master before drafting.
2. Read the exact customer contract and any confirmed change documents. Use only verified parties, event scope, date/time, location, price lines, tax rate, payment terms, and acceptance outcome. Never infer that services were completed, accepted, paid, or signed from the event schedule or document existence.
3. Duplicate the master as a native Google Doc. Keep the master and its reusable Word copy unchanged while preparing customer-specific minutes.
4. Fill the minutes date with `now()` using the user's local timezone, then write that date as literal plain text in the customer copy. Do not leave the `now()` token or a date/time chip in the customer copy.
5. Use native Google Docs numbered lists for numbered clauses under each article. Do not type numeric prefixes into clause paragraph text. Restart each article's list at 1 and verify list indentation/hanging alignment after edits. Article headings and price-table STT cells remain headings/table values, not clause lists.
6. Do not include a personal-deposit section or deposit discussion in this template. Reconcile company payments only.
7. Preserve the full contract price table. Mark each line accepted or excluded; calculate the final settlement only from mutually confirmed accepted lines. If the settlement changes the signed contract value, state that both parties agree to the adjustment and show the excluded amount and tax effect.
8. Keep the complete signature area indivisible on one page. If the space is insufficient, move the whole signature block to the next page. After every adjustment export to PDF, inspect every affected page, and verify the signature block and native list layout.
9. Audit the complete customer copy for placeholders, arithmetic, words for amounts, cross-references, party identities, dates, and internal consistency. Do not leave unsupported blanks or stale sample facts.

## Event calendar handoff

- After a rental customer contract passes the document verification and final scan, use `schedule-769robotics-events` to prepare the linked Google Calendar draft. Do not limit this handoff to dashboard synchronization or a payment schedule.
- Pass the exact current customer contract ID/URL, customer folder name, customer short name, exact robot models/quantities, purpose, venue, actual event and rehearsal start/end times, and script deadline. Keep the contract as the internal schedule source; do not disclose its link to attendees without explicit authorization.
- Use the scheduler's complete reminder sequence: three days before, two days before, one day before, and the session day at 08:00 local, plus two hours before each actual event/rehearsal start. Omit passed reminder times independently and do not move a passed 08:00 reminder to another hour. Preserve actual operational hours.
- Present the calendar draft and the three default internal recipients for user approval. Contract creation or revision alone authorizes preparing the calendar draft, not writing Calendar entries or sending invitations. Once that exact draft is approved, continue without requesting the same permission again.
- After changes to verified contract event/rehearsal dates, times, location, models, or purpose, invoke the scheduler to propose reconciliation of existing entries instead of duplicating them. Report the contract outcome and calendar outcome separately.

## Post-document handoff

- Keep drafting as this skill’s primary task. Do not perform an operational database write until the customer duplicate passes Drive readback, sharing verification, the placeholder audit, and the final error scan.
- After verification, prepare a structured handoff containing the customer identity, transaction type, product, quantity, verified values, dates, document metadata, contract number, payment terms, and unresolved operational facts.
- For a rental, include the Master ID, verified customer values, event scope, commercial values, dates, payment schedule, and unresolved customer-facing facts. Do not include or request robot-source facts.
- Then use the separate `manage-769robotics-deals` skill to synchronize the deal and generate the payment schedule.
- Treat the document result and dashboard synchronization as separately verifiable outcomes. A successful document followed by a synchronization failure is partial completion and must be reported without changing the document result.
- A created contract is a draft or document record only. Never infer signing, payment, handover, acceptance, completion, cancellation, or loss from file existence.

## Mandatory placeholder audit

Run this audit before finalizing or reporting any customer contract or quotation.

1. Inventory every unresolved marker throughout the full document or workbook, including `[CHƯA CUNG CẤP]`, blank value cells, dotted or underscored blanks, incomplete labels, and formula-like template placeholders.
2. Compare each marker against all authoritative facts already available in the current request, prior confirmed user instructions, the customer quotation, the customer contract, and the canonical price sources. Do not ask again for information that has already been supplied.
3. Replace every supported placeholder everywhere it is repeated. Propagate unambiguous dependent facts consistently. For example, a confirmed contract-signing date must fill the contract date and the `DDMMYY` portion of the contract number; a confirmed representative title must fill both the party-information table and signature block.
4. Do not leave a placeholder, blank field, or old dependent value when the answer can be derived unambiguously from an authoritative confirmed fact. Do not infer uncertain legal or customer facts.
5. Re-read the complete deliverable after all edits and run the inventory again. Confirm that every remaining placeholder is genuinely unresolved and uses the exact bracketed form `[CHƯA CUNG CẤP]`.
6. In the final handoff, explicitly list each remaining missing item and where it appears so the user knows what must replace the brackets. If none remain, state that no unresolved placeholders remain.
7. Keep intentional placeholders in reusable templates, but audit completed customer duplicates independently; a template placeholder is not a reason to leave a known customer value unresolved.

## Mandatory final error scan

Run this scan after the placeholder audit and before every final handoff of a customer contract or quotation.

1. Re-read the complete settled deliverable, including every tab, table, signature block, appendix, header, and footer. Do not scan only the paragraphs edited in the current turn.
2. Recalculate and reconcile all commercial figures: quantity × unit price, line totals, discounts, pre-VAT total, VAT rate and amount, VAT-inclusive total, installment percentages, installment amounts, and Vietnamese amounts in words. Payment percentages must total 100%, and payment amounts must total the contract value.
3. Cross-check repeated identities and dependent facts: customer and seller names, tax codes, representatives and titles, product/model, quantity, event or delivery dates, contract date, contract number, filename date, locations, times, and selected service scope. Inspect the full native document structure and reject any date or time represented by a `dateElement`, smart date/time chip, formula, or auto-updating field; replace it with literal plain text before handoff.
4. Check internal legal and operational consistency: chronological dates, payment triggers, cancellation terms, delivery or collection obligations, article and appendix references, defined party names, and whether later clauses contradict earlier instructions.
5. Check language and drafting quality: spelling, Vietnamese diacritics, capitalization of `Bên A` and `Bên B`, punctuation, duplicated words or sentences, malformed ellipses, inconsistent terminology, accidental template text, and awkward or ambiguous wording that changes meaning.
6. Check structural completeness: no missing or duplicated articles, rows, products, payment installments, signature details, requested tables, appendices, or feature selections; no stale customer data from a prior document.
7. Check native and rendered quality in proportion to the deliverable: preserve table/list structure and formatting, then use PDF export and page inspection for final contracts or layout-sensitive quotations to detect clipping, overlap, broken tables, orphaned headings, or unintended blank pages.
8. Repair deterministic errors automatically when they are inside the authorized customer duplicate and supported by confirmed facts. Do not guess uncertain legal, commercial, or customer information; report it instead.
9. After every repair, re-read the affected region and rerun the complete scan until no known deterministic errors remain.
10. In the final handoff, show every repair as a concise diff using `Before → After`, including enough exact text or field context for the user to understand what was wrong. For deletions, show `Before → [removed/blank]`; for formatting-only repairs, name the affected element and property. Then list any remaining unresolved errors, risks, or missing facts. If none remain, explicitly state that the final error scan passed with no known unresolved errors.

## Redline recoloring

When the user asks to show contract updates in red:

1. Record the exact text that will be newly inserted or replaced. Do not classify unchanged surrounding text as updated.
2. Recolor all editable contract text to black before applying the requested content changes. Preserve non-color formatting, native controls, links, tables, headers, footers, and document structure.
3. Apply only the requested content changes.
4. Resolve the final live ranges of the newly inserted or replaced text after all index-shifting edits are complete, then color only those exact ranges red.
5. Keep unchanged text black, including text that was already red before this run. If only part of a paragraph or table cell changed, color only that changed substring red.
6. Read back every changed range and representative unchanged anchors. Verify that all requested updates are red, unchanged text is black, and no unrelated formatting or structure changed.

When the user explicitly authorizes the same update for both an existing customer contract and its reusable template, apply this workflow independently to each authorized document: recolor all editable text in that document black, make the requested edits, and color only the newly inserted or replaced text red. Removed rows or deleted text have no redline; do not color neighboring unchanged content red. Verify both documents separately after all index-shifting edits.

Use direct edits only on an existing customer document that the user explicitly identifies and authorizes for in-place editing. This does not authorize edits to a reusable template, source library item, folder, or any other contract.

## Signature-area pagination invariant

- Treat the complete signature area as one indivisible rendered block, including the signature headings, representative titles, signature space, representative names, and the containing signature table or equivalent structure.
- Never allow the signature area to split across two pages or leave only part of it at the bottom of one page.
- If the remaining space on the current page cannot contain the complete signature area, insert or preserve a page break immediately before the signature area so the entire block begins together on the next page.
- Do not shrink text below the template baseline, compress the signature space unreasonably, delete content, or distort the signature table merely to keep the block on the current page.
- After every adjustment to a customer contract, export the settled document to PDF, rasterize and visually inspect every affected page, and explicitly verify that the complete signature area remains together on one page. If it is split or crowded, repair the pagination and repeat the check before handoff.

## Duplicate sharing

- Default every newly drafted customer contract or quotation duplicate to `Anyone with the link - Viewer`.
- Use a Drive sharing action that creates an `anyone` + `reader` permission. If the connector cannot create public-link permissions but an authenticated Google Drive sharing dialog is available, use it to select `Anyone with the link` and `Viewer`, then verify the result.
- Never substitute domain-wide sharing for public-link sharing.
- Never grant editor or commenter access unless the user explicitly requests it.
- Do not make the source template public as a workaround. File-level permissions on a source are not a reliable inheritance mechanism for copies.
- Do not make the customer-contract destination folder public; that could expose unrelated customer documents.
- If public-link viewer access cannot be verified, keep the draft private, report the limitation, and do not claim that sharing succeeded.

## Contract defaults

- Write every date and time as literal plain text. Use Vietnamese numeric date text such as `30/07/2026` and time text such as `08:00`; use the exact user-confirmed format when one is specified.
- Unless the user states a contract-signing date, set it to the user's current local calendar date plus 01 calendar day. Use that derived date consistently in the contract date, contract number, filename when applicable, every repeated signing-date field, and the first rental-payment deadline without asking for confirmation.
- Never insert or retain Google Docs date chips, time chips, `dateElement` controls, formulas, timestamps, smart fields, or auto-updating date/time controls in a customer quotation or contract. This prohibition applies to contract dates, payment dates, event dates, delivery dates, collection dates, rehearsal dates, deadlines, filenames, headers, footers, tables, and signature blocks.
- When revising a copied or existing customer document, inspect the full Google Docs element structure for every `dateElement` or equivalent date/time control. Delete each control and insert its intended displayed value as ordinary text, preserving the surrounding text style.
- Do not treat a text export as proof that dates and times are plain text because exports can flatten native controls. Before handoff, verify through full native-document readback that no date/time chips or `dateElement` objects remain and verify the literal date/time strings through a separate text readback.
- Write every genuinely unresolved field as the exact placeholder `[CHƯA CUNG CẤP]`. Never use unbracketed `Chưa cung cấp`, `CHƯA CUNG CẤP`, or similar wording for a placeholder. Preserve brackets only until authoritative information replaces the entire placeholder, and always apply the mandatory placeholder audit before handoff.
- Omit the Party A rows `Tài khoản số` and `Ngân hàng` from rental contracts unless the user or an authoritative source specifically requires the customer's banking information.
- Use three mutually exclusive rental-service choices:
  - `Không`: no additional technical setup.
  - `Cấu hình`: use manufacturer-provided settings and built-in features.
  - `Lập trình`: develop additional functions through the robot SDK/API.
- In customer rental contracts and detailed rental or sales quotations, check exactly one of `Không`, `Cấu hình`, or `Lập trình` according to the confirmed scope.
- When the user or authoritative scope does not specify a choice, default to `Cấu hình`.
- In reusable detailed rental and sales quotation templates, preselect `Cấu hình` and leave `Không` and `Lập trình` unchecked so new customer quotations inherit the default.
- In a completed customer document, show only the selected choice and its short matching description. Do not display the unselected choices or descriptions for other levels.
- Default `Nội dung hiển thị và kịch bản chi tiết` to `Theo thỏa thuận` unless the user provides specific content.
- Keep the Article 3 title, but leave its body completely blank when the scope is not mentioned or when `Không` or `Cấu hình` is selected. Do not write `KHÔNG ÁP DỤNG`, a description, or a placeholder in the blank Article 3 body, and do not treat this intentional blank as an error during placeholder or final scans. Populate Article 3 only when `Lập trình` is selected or the user explicitly requests additional programming content for that article.
- Format every contract number as `DDMMYY-769Robotics-CUSTOMERSHORT`, where `DDMMYY` is the contract-signing date and `CUSTOMERSHORT` is a short unique customer identifier such as a customer’s established uppercase abbreviation.
- Keep `CUSTOMERSHORT` concise, recognizable, and unique within the customer-contract folder. Prefer the customer's established abbreviation; otherwise derive a short uppercase identifier from the customer name.
- Unless the user states different purchase-contract terms, use three payment installments based on the VAT-inclusive contract total:
  - Installment 1: 30%, payable within 3 working days after contract signing so the seller can proceed with the order. Treat this amount as a non-refundable deposit if the buyer unilaterally cancels the order.
  - Installment 2: 60%, payable within 7 days after the seller photographs the arrived product and sends the photos to the buyer by email, Zalo, or another communication method agreed by both parties.
  - Installment 3: 10%, payable within 7 days after both parties sign the goods handover record.
- Calculate and fill the amount and Vietnamese amount-in-words for every payment installment.
- Default the delivery time to 50 days from the seller's receipt of installment 1, excluding Saturdays, Sundays, public holidays, and force-majeure delays already stated in the purchase-contract template. After installment 2 is paid, require the parties to agree separately on the delivery time.
- Keep the delivery address as an explicit bracketed placeholder until the customer provides it.
- State concisely that the seller bears delivery, transport, and unloading costs within Ho Chi Minh City or inner Hanoi, depending on the buyer's delivery location. Do not imply free delivery outside those areas.
- For rental contracts, use the exact duration and unit basis confirmed by the current customer scope. If the scope does not state a duration, use the duration shown for the exact product in the current rental price source; if it is still unavailable, keep `[CHƯA CUNG CẤP]` instead of asking about robot ownership or supplier.
- Calculate the robot collection time as the stated start time plus the rental duration. Keep the same event date unless the calculation crosses midnight.
- Treat early arrival for rental setup, checks, and trial runs as optional, never a default commitment. Use: `Bên A có thể đến sớm để setup, kiểm tra và chạy thử tùy điều kiện thực tế; việc đến sớm không phải là cam kết có mặt trước giờ vận hành hoặc vào một giờ cụ thể, trừ khi hai bên có thỏa thuận riêng bằng văn bản. Bên A vẫn phải bảo đảm thời gian vận hành đã thỏa thuận.` Never calculate arrival by subtracting one/two hours from an event or rehearsal start, or convert `có thể đến sớm` into `phải đến`, `sẽ đến`, or `có mặt lúc`. Include a specific arrival commitment only when the user explicitly confirms it for that booking. A separately scheduled rehearsal does not itself authorise an early-arrival promise. Preparation does not reduce agreed operating time. Before handoff, check every article, schedule table, and appendix for unsupported arrival/setup times and reconcile them with this rule.
- For rental payment terms, preserve the settled two-installment structure in the single rental Master. Unless the user states different deadlines, set installment 1 to the user's current local calendar date plus 01 calendar day, which is also the default signing date, and set installment 2 to the event date plus 03 calendar days. Count every calendar day consecutively; never skip or adjust for Saturdays, Sundays, or public holidays. Do not calculate installment 1 as signing date plus another day.
- Every payment due time in a rental contract must be before 17:00. If the customer has not specified a different time, use 16:59; never write 17:00 or later as a payment deadline. Keep any user-confirmed earlier time.
- Include the confidentiality clause: “Hai bên bảo mật thông tin kỹ thuật, tài chính và tài liệu không công khai.” For advertising/portfolio use of event photos or video, state “Quyền Bên A sử dụng hình ảnh/video sự kiện cho quảng cáo/portfolio: Hai bên thỏa thuận sau.” when the parties have agreed to settle permission later; do not leave `[CHƯA CUNG CẤP]` for that decision.
- Default VAT to 8% unless the user states a different rate or explicitly says VAT is excluded.
- Calculate and fill the pre-VAT total, VAT amount, and VAT-inclusive total.
- When a quotation includes both an original price and a lower discounted or promotional price, show both prices in the same unit-price cell: put the original price on the first line with strikethrough, then put the discounted price directly below it in bold without strikethrough.
- Use only the discounted price to calculate line totals, pre-VAT totals, VAT, and the VAT-inclusive total. Do not apply this two-line treatment when no discount is confirmed by the user or an authoritative current price source.
- Put each product on its own table row. Insert additional product rows as needed; never place multiple products in one cell.
- Use sequential values in the `STT` column and put the corresponding product, quantity, rental-day count, and price on the same row.
- In the `Thời gian thuê (ngày)` column, enter only the numeric value such as `1`; do not repeat `ngày` because it is already present in the column label.
- Treat a time stated as `9h`, `09h`, or `09:00` as a start time unless the user explicitly describes it as a duration.
- Preserve the template's table formatting when inserting product rows, then verify row count, column count, and every cell through connector readback.

## Non-negotiable write safety

- Never edit, rename, move, delete, replace, or change sharing on the main folder, either destination folder, any canonical template, or any other source item unless the user explicitly instructs that exact change.
- Public-link sharing is authorized only for the newly created duplicate under this workflow, not for the template, folders, or existing customer files.
- Treat requests such as “draft a detailed quotation,” “prepare a contract,” or “make a customer contract” as authorization to create and edit a duplicate only.
- Do not interpret requested changes to the draft as permission to update the template.
- If duplication or moving fails, stop before editing. Do not fall back to editing the source.
- Preserve existing folder organization and permissions unless the user explicitly asks to change them.

## Workspace source selection

- Add actual Google Docs, Sheets, Slides, or supported files as sources.
- Do not add a folder object as a source. Open the folder, list its contents, and select the actual child documents instead.
- For `Bảng báo giá cho Khách hàng` or `Hợp đồng cho Khách hàng`, use contained customer files as sources, not the folder object itself.
- Do not add a Drive shortcut as a source. Resolve the shortcut and select the original file. If the original cannot be accessed, create or request an accessible real copy; never claim the shortcut was added successfully.
- Prefer native Google files. Add sources in smaller batches if the GPT Workspace add-on returns a deployment error.
- Verify the add-on's selected-file count and final source list after refreshing or reopening the panel; do not rely on a stale count.

## Current known valid source types

- Native Google Docs
- Native Google Sheets

Known invalid inputs for this workflow:

- Google Drive folders as source objects
- Google Drive shortcuts when the add-on cannot resolve the target

Expect the rental quotation price source to be a native Google Sheet rather than a shortcut. Confirm the bound file's live MIME type and source eligibility before selecting it. This source-type expectation does not change the rule that customer-facing detailed quotation deliverables are native Google Docs.
