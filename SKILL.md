---
name: auto-rebuttal
description: Use when drafting or revising an author rebuttal, reviewer reply, or OpenReview response for a paper under review, especially when reviews contain multiple technical objections that need reviewer-specific, topic-structured replies.
---

# Auto Rebuttal

Write a grounded, reviewer-aware rebuttal from the available paper materials, review text, and approved evidence.

## Scope

Use this skill to produce rebuttal drafts, not to run experiments, invent evidence, or upload submissions.

Read references only as needed:

- `references/issue-taxonomy.md` when review concerns are mixed or hard to classify
- `references/response-patterns.md` when choosing how to answer a concern
- `references/length-and-budgeting.md` when space is tight
- `references/anti-patterns.md` before finalizing

## Required Inputs

- paper summary or paper source
- raw reviews or follow-up comments
- venue constraints if known
- approved evidence and approved promises, if any
- approved references or candidate prior-work sources, if any

If a critical venue rule is missing, prefer a conservative text-only draft and record the assumption in `self_report`.

## Workflow

1. Decompose the review text into a reviewer-topic map before drafting: for each reviewer, split every substantive concern into small topics.
2. Keep the topic granularity tight: one topic per distinct objection, or one tightly coupled pair only when the evidence is genuinely shared.
3. Build an evidence inventory before drafting.
4. Mark cite-worthy topics: if a technical or theoretical objection can be answered partly by noting that a nearby work uses the same assumption, tool, or technique, record that candidate support.
5. For each topic, choose a response mode that matches the evidence strength.
6. For score-sensitive technical blockers, draft a minimal technical bridge before adding any revision promise.
7. For novelty, metric, and proof disputes, make the distinction structure explicit instead of implying it.
8. Plan the structure as reviewer-specific replies only. Inside each reviewer section, answer by topic with bold topic headings. If citations are used, append a short final `References` section after all reviewer replies.
9. Draft high-risk answers with a concrete micro-structure: direct answer -> mechanism or reason -> scope/tradeoff -> contribution anchor.
10. When theory uses an idealized object or assumption but practice uses an approximation, answer both layers together: theoretical role, practical surrogate, and what remains guaranteed.
11. If a reviewer says the paper lacks formality or clarity, convert that into specific manuscript actions such as revised definitions, theorem wording, notation alignment, comparison tables, or proof-step exposition.
12. Draft with direct answers first, then supporting detail, then the implication for the paper or why the main contribution still stands.
13. For score-moving blockers, include one decision-relevant sentence that explains why the concern is now bounded or why the core claim still survives.
14. When a reviewer bundles multiple substantive objections, mirror that bundle in the reply order so each objection has a visible answer slot and a visible topic heading.
15. If follow-up discussion exists, use it to rebudget the reply: focus on blockers that remain unconvinced and keep satisfied reviewers brief but supported.
16. Under tight space, compress each major topic to a minimal unit: direct answer, one mechanism sentence, and one concrete manuscript action.
17. Before finalizing, remove any domain-specific framing that came from a single example rather than from the current paper and reviews.
18. Produce the required output artifacts.
19. Run the self-check before finalizing.

## Evidence Inventory

Track each supporting point as one of:

- `paper-supported`
- `reviewer-observed`
- `user-confirmed`
- `revision-commitment`
- `future-work`

Do not blur these categories. Say what is already true now, what will be clarified in revision, and what remains future work.

## Required Output

Return all four sections:

- `response_draft`
- `coverage_map`
- `evidence_map`
- `self_report`

`coverage_map` should show every substantive concern and how it was handled.

`evidence_map` should map each major answer to its support category.

`response_draft` is the venue-ready rebuttal text. The other sections are controller scaffolding and must stay out of the submission system.

`response_draft` must be organized reviewer-by-reviewer. Do not include a global general-response section.

Inside each reviewer section, use bold topic headings such as `**Context Distribution Assumption**` or `**Proof Validity Under Adaptive Sampling**`.

If citations are used, put only lightweight citation markers in the body, and place the full entries in a final `References` section at the end of `response_draft`.

Use numbered markers such as `[1]` in the body and format the final entries as short bibliography lines like `[1] Author(s). Title. Venue, Year.`

`self_report` should include:

- assumptions made
- unresolved weak spots
- places where stronger evidence would improve the rebuttal

## Hard Rules

- Answer every substantive reviewer concern.
- Start by splitting concerns into reviewer-specific topics before drafting prose.
- Do not invent experiments, citations, derivations, numbers, or promises.
- Use citations sparingly and only when they directly help answer a technical, theoretical, or prior-work challenge.
- Only cite works already available in the current paper, the review bundle, user-provided materials, or from an explicitly user-approved literature search.
- When a prior work uses the same assumption, proof tool, or technical device under dispute, a light in-body citation is allowed to stabilize the answer.
- Do not turn the rebuttal into a literature survey; one light citation is usually enough for a topic.
- If citations are used, collect them in one short final `References` section with numbered entries in `[1] ...` style.
- Do not hide a weak point behind gratitude or vague future clarification.
- Do not lead a major technical answer with “we will clarify”; lead with the best current answer you can support now.
- Do not concede more than the evidence requires.
- Output reviewer-specific replies only; do not add a standalone general-response block.
- Within each reviewer section, give each topic a bold heading.
- Do not replace mechanism explanations with scope boundaries when the reviewer is asking how or why something works.
- Preserve support from friendly reviewers; do not ignore positive reviewers.
- Prefer narrow, specific concessions over broad self-undermining ones.
- If a reviewer analogy or comparison is partly fair, acknowledge the valid overlap before differentiating your method, proof, or claim.
- For assumptions, theorem doubts, and applicability questions, try to answer: why it is needed, what it buys, and what changes if it is relaxed.
- For assumption challenges, classify the assumption if possible: essential to the current guarantee, common in prior formulations, or replaceable at extra cost.
- For unusual-assumption challenges, say not only why the assumption appears, but also why it is not isolated or fatal: whether nearby work uses or estimates something similar, what practical surrogate the paper already uses or could plausibly use, and what changes if that surrogate replaces the formal object.
- For practicality-of-assumption challenges, do not stop at the theory/practice split. When support exists, also say how the relevant quantity is computed when known, what plug-in or estimation strategy is plausible when unknown, whether the paper already has empirical support for a surrogate, and what extra error term or assumption the surrogate would introduce.
- For novelty or missing-related-work disputes, compare against prior work along explicit axes inside the rebuttal itself instead of saying only “we will strengthen positioning.”
- For novelty disputes, first restate the paper's actual claimed contribution before engaging the reviewer's framing. Do not casually adopt a broader novelty claim than the paper itself makes, then concede that broader claim away.
- For novelty disputes, do not stop at topic overlap. Compare the role the shared concept plays in each work: representation versus decision-making, past aggregation versus future credit assignment, prediction versus control, or analysis versus algorithm.
- For metric or notation disputes, state which quantity is claimed now, how it relates to the reviewer's quantity, and where the paper text should align.
- Do not flatten two meaningfully different quantities into one summary if the paper relies on both; define both roles and their relationship.
- For proof disputes, separate claim layers when relevant: definition level, theorem-statement level, expectation level, realized/high-probability level, or algorithmic layer versus estimation layer.
- For proof-validity or concentration disputes, name the proof mechanism when supportable and say whether it preserves the qualitative rate, adds a bounded term, or mainly changes exposition.
- If one reviewer bundles several objections, preserve the objection order unless there is a strong reason to reorder; make it easy for the reviewer to map each concern to its answer.
- Do not bury multiple distinct concerns inside one vague paragraph when separate topic headings would make the reply easier to scan.
- Do not collapse materially different reviewer objections into one shared narrative just because they live in the same theme bucket.
- If follow-up comments say a prior response did not change the evaluation, do not restate everything; target the unresolved blocker more directly.
- For evaluation complaints, separate method scope from evidence scope: state what part of the pipeline the method changes, what the current benchmark or data supports, and why that makes the observed gain size, missing baseline class, or robustness boundary plausible.
- If space is tight, do not compress away the mechanism or the manuscript repair; compress background and transitions first.
- For extension questions, prefer an extension sketch plus scope boundary over a bare “future work” retreat.
- When claiming an extension is natural, name at least one operational consequence such as an added queue, a changed theorem scope, or a dependence on the number of constraints or modules.
- When defending compatibility or validity, avoid restating the claim in a narrower form unless the paper truly requires that narrower statement.
- When a weakness is real but bounded, reframe it as a specific tradeoff only if that tradeoff is actually supported, and name the compensating benefit in the same local answer.
- End high-risk answers by reconnecting the clarification to the paper's surviving contribution, not just the planned revision.
- For major blockers, do not make the reviewer infer the consequence; state explicitly why the answer reduces the blocker or leaves the main claim intact.
- When the reviewer complains about formality or clarity, do not stop at “we will clarify”; name the concrete textual repair the revision will make.
- Do not relabel a technical objection as mere clarity or positioning unless the technical substance has already been answered.
- Use positive reviewers strategically: after answering a substantive point, preserve existing support as corroboration rather than as filler gratitude.
- Positive reviewers still need direct answers to their concrete asks; do not collapse those asks into generic exposition promises.
- When several reviewers share a blocker, consider a short synthesis sentence that states the paper-level clarification once and keeps local replies focused.
- Do not open the rebuttal by foregrounding what the paper needs to fix, sharpen, or clarify before you state the substantive clarification itself.
- Do not tell reviewers what their comments are “really about” instead of answering the comments as written.
- Reuse structural tactics from prior examples, not their domain terms, citation choices, or sample-specific argumentative habits unless the current evidence independently supports them.
- If evidence is thin, answer carefully and bound the claim.

## Self-Check

Before finalizing, verify:

1. Coverage: no important concern is dropped.
2. Grounding: every factual claim is traceable.
3. Specificity: the draft answers the actual concern, not a nearby easier one.
4. Tone: respectful, calm, and non-defensive.
5. Promise control: revisions are framed as clarifications unless stronger commitments are explicitly approved.
6. Score impact: high-risk reviewers and technical blockers got the sharpest content, not just equal space.
7. Distinction quality: novelty, metric, and proof disputes are answered with explicit distinctions rather than vague promises.
8. Sentence-level concreteness: high-risk answers contain at least one mechanism sentence, not only framing or revision language.
9. Manuscript concreteness: clarification promises are attached to specific paper-level changes, not abstract intent.
10. Theory-practice pairing: if an answer relies on a theoretical idealization, the draft also states the practical interpretation or surrogate when supported.
11. Decision relevance: high-risk replies include a sentence about what the clarification changes for the reviewer's concern.
12. Bundle mirroring: multi-objection reviews are answered in a visibly matched order.
13. Follow-up awareness: later-round replies visibly target remaining blockers rather than repeating already-accepted material.
14. Blocker compression: shortened replies still preserve direct answer, mechanism, and concrete repair for major blockers.
15. Generality guard: the draft reads as grounded in the current paper and reviews, not as a recycled answer shape from another domain.
16. Compression safety: if shortened, keep direct answers and key evidence first.
17. Deliverable hygiene: `response_draft` reads like venue-ready rebuttal prose and does not leak controller scaffolding.
18. Reviewer specificity: the reply is organized reviewer-by-reviewer, not as one global answer.
19. Topic visibility: each reviewer section uses bold topic headings and does not merge unrelated concerns.
20. Assumption defense strength: unusual assumptions are defended as bounded, comparable, or estimable when support exists, not only described.
21. Citation discipline: any citation used is relevant, source-backed, lightweight in the body, and fully listed in a final `References` section.
22. Practicality depth: practical-assumption replies include an operational path or empirical support when the current materials support it, not only a theoretical explanation.
23. Level matching: novelty, motivation, and evaluation objections are answered at the right level of abstraction: role, mechanism, and scope, not just shared topic words or table-number restatement.
