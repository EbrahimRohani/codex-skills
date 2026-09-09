# Completed case pattern: Digikala Instant Exchange

Source: `Working_Backwards_Completed_Case_Handout.pdf` and `Digikala_Instant_Exchange_Completed_PRFAQ.pdf`.

This is a fictional illustrative case study. Use it to understand how the artifacts connect, not as a real Digikala service, policy, target, quote, geography, volume, or economic baseline.

## Promise and boundary

An eligible customer can replace a defective or incorrect same-SKU item in one scheduled courier visit, with the standard return path preserved if the swap fails. The model boundary is Digikala-fulfilled, in-stock, non-heavy products, selected reasons, same SKU, and three selected Tehran zones. It excludes different products, colors, or sizes; seller-fulfilled or heavy items; general returns redesign; instant refund or open substitution; and national or permanent launch.

## Experience pattern

1. Open the order and choose Request exchange for an eligible reason.
2. Review eligibility, same-SKU replacement, handoff conditions, and fallback.
3. Confirm only after the replacement is reserved.
4. Choose an exchange window and receive status updates.
5. Hand the original item to the courier and receive the replacement.
6. See completion; if the visit fails, use the standard return path without penalty.

## What the hard FAQs reveal

The promise requires reservation integrity, observable state transitions across order / returns, inventory, courier tasking, app, support, risk, and analytics, two-asset custody checks, safe failure codes, accessible and assisted paths, transparent misuse controls, support recovery, and validated economics. The courier does not diagnose defects. The fallback stays open. Serious safety incidents, privacy or policy breaches, uncontrolled reservation inconsistency, sustained failed-swap or support breaches, or unreconciled custody are stop conditions.

## Illustrative assumption ledger

High-impact assumptions include customer demand for speed and certainty, enough eligible volume, fewer than 3% broken reservations, safe two-asset courier handling, one-visit handoff completion, no more than 10% support contact, fair misuse controls, and positive unit economics. The model pairs them with interviews or concept tests, eligibility analysis, shadow reservation, operations simulation, usability and dry runs, instrumented pilot analysis, false-positive review, and unit-economics validation.

## Illustrative metrics and risks

The case uses targets such as at least 80% of confirmed exchanges completing within 48 hours, at least 20% lower effort than baseline, fewer than 3% lost reservations, fewer than 5% avoidable failed swaps, no more than 10% support contact, and zero serious safety incidents. These are illustrative until Data defines baseline, denominator, segments, timestamps, and validity. Key risks are broken reservation, failed handoff, state inconsistency, accessibility gap, courier safety or custody, quality escape, misuse or unfair exclusion, and poor learning validity.

## Staged recommendation and governance

The model recommends customer evidence, a state prototype, shadow reservation, and operations simulation before any live promise. A capped live pilot (illustratively up to 500 invitations in three zones for four weeks or 300 completed exchanges) requires entry evidence and sponsor ratification. The decision rule is expand, iterate, pause, or stop. A worked conflict chooses shadow reservation first because it is reversible while a live promise and inventory investment are not. The Product Manager owns the outcome narrative and recommendation; Design, EM, Tech Lead, Engineers, QA, Data, Operations, Risk or policy, and a named sponsor own their respective evidence or ratification.
