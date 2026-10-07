---
name: 769robotics-quotation-rules
description: Apply the user's standing price, payment, naming and folder rules when creating or updating detailed 769 Robotics rental quotations and contracts, including work with Draft 769Robotics Contract.
---

# 769 Robotics quotation rules

Use the reconciled mode-specific readiness rules in `../../MIGRATION.md`. Customer-specific exceptions remain in Drive and must be resolved from the relevant verified customer record before use.

Use these standing user preferences alongside the original contract workflow when available. This supplementary skill does not replace missing templates or invent previous workflow instructions.

## Price and VAT

- Always treat every price and total supplied by the user as BEFORE VAT. Do not ask whether VAT is included. Override only when the user explicitly specifies another basis.
- Show the service subtotal, discount, net before VAT, VAT rate and amount, and total payable separately. Verify the applicable VAT rate from current authoritative sources; do not turn a template's rate into a permanent assumption.
- When the user authorizes allocating a discount to reach a target, distribute the discount across each product. In each product's unit-price cell show the old price with native strikethrough on the first line and the new discounted price below it. Use the discounted price for that product's line total. Do not add a separate package-discount row. Use grounded base prices, do not invent unsupported logistics charges or durations, and check every sum.

## Payment

- For a user-supplied total value of 60,000,000 VND before VAT, default to three installments: 50% deposit on confirmation; 30% after rehearsal and before the main performance; 20% remaining. Preserve a missing final due date as unconfirmed. Do not broaden this exact-value rule into an unconfirmed threshold.
- Explicit payment instructions for the current customer always override defaults. Read the verified customer-specific payment exception from the Drive customer records; do not put named-customer exceptions in repository rules or generalize them to other deals.
- Calculate installment amounts from the total payable including VAT and show the before-VAT/VAT split when helpful. Make all installment percentages total 100% and amounts reconcile exactly.

## Names and location

- Preserve established destination roots, matching existing customer/event folders and document naming. For new folders use a concise recognizable customer, models and dates; add quantities/purpose/place only when needed for retrieval. Do not globally migrate folders. Name the chat session like the selected folder when supported. Preserve unconfirmed date precision; do not invent a day.
- Use an exposed session-title tool when available. If no such capability exists, disclose that the title was not changed and provide the exact desired title. Do not claim success.
- Name each document using its document type plus the same customer/model/date/purpose tokens.
- Keep templates unchanged. Place customer copies in the corresponding authorized folder; verify actual parent and permissions. Do not assume permissions copy or expand sharing without applicable user authorization. Keep new owner drafts private if no audience is authorized.

## Source and template fidelity

- Verify customer details from the supplied source and current document contents. Use the exact [CHƯA CUNG CẤP] marker for missing information; qualify known but unconfirmed facts explicitly without asserting confirmation. Do not guess facts.
- Read and copy the authoritative template, preserving native Google Docs structure, styles, tables and automatic numbering. Adapt all previous-customer facts before delivery.
- Leave unconfirmed exact dates, duration, venue, contacts, final payment deadline, logistics scope and technical choreography visibly unconfirmed. Do not promise unsupported synchronized motions.
- Verify content, arithmetic, sharing, and rendered page layout before handing over the document.


