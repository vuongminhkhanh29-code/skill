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

- Before drafting or revising a rental quotation or contract, compare its payment terms and all other applicable requirements with the verified README and canonical rules. If they conflict, show the exact conflict and ask the user which terms to apply before the dependent write. Do not silently prefer an existing quotation/contract, a template, or a presumed customer exception. A current explicit user confirmation resolving that exact conflict is sufficient authority; record it for that deal and do not ask again. Never generalize an approved customer exception.
- Apply the same rental payment schedule in quotations and contracts. Use three installments (50% deposit on confirmation / 30% supplementary deposit at the confirmed rehearsal or intermediate milestone before the main performance / 20% balance after completion) ONLY when BOTH conditions hold: (1) more than 2 confirmed deployment days, including scheduled rehearsal days; AND (2) total value before VAT strictly exceeds VND 100,000,000. Otherwise use two installments: 50% deposit on confirmation / 50% balance after completion. Exactly 2 days or exactly VND 100,000,000 does not qualify. This supersedes the old OR/multiple-event trigger and abolishes the exact-VND60m exception. Do not infer missing days or values; preserve unconfirmed inputs and ask only when necessary to choose the schedule. For a qualifying three-installment case, confirm the intermediate milestone rather than inventing one. Calculate installment amounts from the VAT-inclusive total.
- Keep the current README's normal final-payment deadline unless the user explicitly approves a different term for that deal. For an approved 15-day extension, use 15 calendar days from the confirmed event-completion date, convert it to a literal due date and time, and reconcile every conflicting cap or cross-reference in that customer document. Do not turn this optional extension into a default or into 15 working days.
- Apply a confirmed exception only to its verified customer record in Drive; never publish named-customer facts in repository rules.
- Read the verified rental quotation payment README in the bound customer-quotation root and the rental contract README; keep their payment rules aligned.
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


