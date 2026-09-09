# Working Backwards PR/FAQ writing guide

Source: `Working_Backwards_Walkthrough_Deck.pdf`, `Working_Backwards_Completed_Case_Handout.pdf`, and `Digikala_Instant_Exchange_Completed_PRFAQ.pdf`.

## What the artifact is

A PR/FAQ is a decision tool, not launch copy. The press release clarifies customer value and the honest boundary. The FAQs expose the cost, risk, feasibility, failure behavior, policy implications, and evidence needed to decide.

## Recommended sections

### 1. Status, customer, and boundary

State whether the artifact is fictional, illustrative, draft, pilot, or approved. Name one specific target customer and present struggle. State the observable outcome and a concrete in-scope / out-of-scope boundary. Never let an illustrative case, target, quote, zone, volume, or economic figure read like a fact.

### 2. Future press release

Use an outcome-led headline, then answer:

- Who benefits and in what situation?
- What becomes possible or easier?
- What is the experience from request through recovery?
- What is the success signal, and what remains bounded?
- Why is the promise worth testing?

Write as a future experience. A typical narrative includes request, eligibility, confirmation only after the needed condition is secured, fulfillment or handoff, status updates, and recovery when the flow fails.

### 3. Customer experience

Make the happy path and failure path equally concrete. Show what the customer sees, what is confirmed, what is reserved or guaranteed, what happens at handoff, and how the standard or safe fallback remains available.

### 4. Hard FAQs

Organize questions by lens and answer with guardrails, evidence needs, or refusal conditions:

- Customer: eligibility, variants or substitutions, payment, timing, and recovery.
- Feasibility and architecture: source of truth, state transitions, reservation or capacity integrity, reconciliation, coupling, and the smallest technical test.
- Operations and handoff: custody, capacity, identifiers, safe handling, failure codes, and what frontline staff must not diagnose or decide.
- Quality: risk-based release evidence, realistic failure modes, accessibility, privacy, support recovery, and stop controls.
- Abuse, fairness, sellers, support, and policy: narrow transparent rules, false-positive review, data minimization, clear explanations, assisted paths, and sponsor ratification for customer-affecting policy.
- Economics and learning: incremental costs, avoided costs, denominators, comparison cohorts, selection bias, and what result expands, iterates, pauses, or stops.

Do not use FAQs to reassure readers. If an answer cannot name a control or learning step, the boundary or promise is probably premature.

### 5. Product frame

State tenets that protect the promise and explicit non-goals that prevent accidental scope expansion. Typical tenets include promise only what is observable, reduce effort rather than transfer complexity, preserve a clear fallback, let evidence outrank confidence, build quality/accessibility/safety/privacy in from the start, and keep early exposure reversible.

### 6. Evidence and assumption ledger

Use one row per material statement:

| Area | Statement | Type | Impact | Source / method | Population and date | Limitations | Owner | Exit evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |

Types are Evidence, Assumption, Experiment, and Decision. An assumption becomes evidence only when source, method, date, population, and limitations are recorded. A target is not a baseline.

### 7. Measurement, risk, and rollout

Define metric names, formulas, timestamps, inclusion rules, denominators, comparison populations, segments, and data owner before interpreting a target. Label illustrative targets. Pair each high-impact risk with consequence, mitigation or evidence, DRI, and a hard stop where appropriate.

Stage exposure: customer evidence and prototype, technical or state test, operations simulation, a tightly capped live pilot, then a written review. Each stage needs entry evidence, exit evidence, a DRI, and stop authority.

### 8. Governance and open decisions

Record DRI, contributors, ratifying sponsor, reversibility, dissent, deadline, next action, and review checkpoint. List unresolved choices (eligibility, geography, cap, payment or policy, source of truth, custody, baseline, sample decision rule, and stop authority) instead of hiding them in prose.

## Style

Use plain language, short paragraphs, compact tables, and explicit statuses. Keep recovery, accessibility, quality, safety, privacy, and economics visible. Prefer "what must be true" and "what would make us stop" over confidence statements.
