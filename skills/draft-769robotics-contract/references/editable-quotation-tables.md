# Editable quotation tables

Use a customer-specific native Google Sheet for detailed rental/sales quotations by default. This is the owner's 29 October 2026 replacement of the static-Docs-only quotation rule. Apply it to comparison quotations and ordinary detailed quotations. Contracts and acceptance minutes remain native Docs. Never promise that a Docs table, PDF, printed checkbox, or linked table recalculates automatically.

## Source and destination
- Read the verified designated quotation Doc for seller/customer fields, branding, sections and commercial terms, and both live price Sheets for current source checks. Create a separate customer calculation workbook; never turn either canonical price Sheet into a customer file or modify its data/permissions.
- Preserve the established quotation root, customer/deal folder and naming. Adapt the source's visual identity and sections to a legible Sheet. No new template binding is needed to create a customer workbook from these verified sources.
- Keep any optional Doc/PDF a clearly dated static snapshot of the Sheet's selected values. Do not claim later Sheet edits update that snapshot or an already issued contract.
- Do not widen sharing to make inputs editable: verify the owner/team's existing editor access, retain authorized viewer access for customers, and explain that viewers must request authorized edit access or make their own copy.

## Native table design
- Put price inputs and native Boolean checkbox controls in the visible quotation table beside the matching service. Use TRUE/FALSE data validation (not decorative checkbox glyphs).
- Use a separate calculation block or tab for each mutually exclusive option; label exact dates and scope. Never sum alternative options into one payable total. A comparison summary may reference each option's total.
- Provide visible columns for inclusion, product/service, charge basis (per day/per hour/per package/per booking), quantity, deployment days, billable multiplier, numeric list price, editable numeric quoted price, and formula line total. Keep the count of deployment days separate from the billable multiplier.
- Make editable inputs visually distinct with a short legend. Keep numerical prices as numbers with VND formatting, not strings containing currency symbols, units or line breaks. If a discount is confirmed, show original price struck through in its own numeric column beside the actual quoted price; this explicitly replaces the two-prices-in-one-cell rule for formula Sheets. Derive the discount from these columns; do not double-subtract it.
- Use warning-only protection for formula cells, leaving intended input/checkbox cells editable by existing authorized editors. Do not lock out the owner or grant any additional editors.
- Default mandatory services included and optional add-ons unchecked unless explicitly selected. Show both the available add-on price and its included amount (zero when unchecked). Use an independent checkbox for each add-on in each comparison option.
- A price quoted for the whole package is charged once at its supplied scope. For a package/booking add-on use multiplier 1; use quantity 1 when the package covers the entire booking, even if several robots/days are displayed elsewhere. Only multiply by robot count, days, hours or performances when the quoted basis explicitly requires it. If the basis is unclear, show the uncertainty and resolve it before presenting a committed total.
- Put incomplete logistics and other unpriced required items in a visible outstanding-items section. An incomplete total must be labelled provisional/excluding those items. Never treat an unknown amount as a confirmed free service.

## Formula pattern
Adapt cell references to the actual table; formulas below use English function names. Set/verify workbook locale and actual formula parsing. Example columns: A inclusion checkbox; B service; C charge basis; D quantity; E deployment days; F billable multiplier; G original price; H quoted price; I included net amount.
- For a confirmed daily rate set F to a reference to E. For a confirmed full-package rate set F to 1; for hourly/performance rates use their confirmed billable units. A package price is not multiplied by E.
- Net line: `=IF(A12,ROUND(D12*F12*H12,0),0)`.
- Included original value: `=IF(A12,ROUND(D12*F12*G12,0),0)`. Fill G with H where no separate original price is confirmed; do not invent a higher list price.
- Service subtotal = sum of included original values. Discount = subtotal minus sum of net line values. Net before VAT = sum of net line values.
- For a uniform verified VAT rate in an input cell: `=ROUND(NetBeforeVAT*VATRate,0)`; payable = net before VAT + VAT. For mixed VAT rates, calculate tax by line/rate group and sum it instead of applying one blanket rate.
- Rental installments: `=IF(AND(ConfirmedDeploymentDays>2,NetBeforeVAT>100000000),3,2)`. Missing day counts must produce a visible missing-input condition, not an assumed schedule. Reference an explicitly approved deal-specific exception when one exists. Do not invent the intermediate date/milestone of a qualifying three-installment schedule.
- Calculate each installment from the VAT-inclusive total. Use 50%/50% or 50%/30%/20% as applicable; make the last amount the total minus earlier rounded installments so the amounts reconcile exactly.
- For purchases use the verified purchase payment schedule, not the rental day/value trigger.
- Reference all repeated monetary values (including payment summaries and comparison totals) to their calculation cells; do not leave stale hardcoded amounts or amount-in-words text after price changes. Omit redundant amount-in-words in the editable quote unless it is kept correctly synchronized.
- Keep event dates, payment due dates and times literal and visibly qualified when unconfirmed; the permission to use monetary formulas does not permit auto-updating dates or date chips. Preserve the applicable deadlines and triggers.

## Verification
Before delivery, inspect native formulas, checkbox validation, effective values, warnings/protection, permissions and full content. Test in a temporary QA tab/copy without altering the delivered selections:
1. Edit a base price and confirm line total, subtotal, VAT, total and every installment update.
2. Toggle each add-on on/off: confirm the exact tax-inclusive difference and return to the original total; verify an unselected add-on contributes zero.
3. Increase days for a per-package charge: it must remain charged once. Confirm a per-day line scales correctly.
4. Confirm comparison options are independent and never added together. Test rental payment boundaries at 2 versus 3 days and exactly VND100m versus above it.
5. Check zero/free lines, confirmed discounts, rounding and any mixed VAT; all installment amounts must sum to the payable total.
6. Restore intended inputs/selections, remove only the QA tabs/copies created for this task, and read back live formulas and calculated values. Export and inspect the customer-facing pages to verify legibility and pagination.
Deliver the editable Sheet link with one short instruction: edit the highlighted prices and tick/untick optional rows. Disclose any unresolved input or static snapshot limitation.
