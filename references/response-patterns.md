# Response Patterns

Choose the weakest pattern that still answers the concern honestly.

Default opening rule:

- The first sentence or two of any topic should function as a compressed answer preview.
- Put the core answer before the explanation, not after it.
- If the concern is score-moving, let the opening also signal the consequence: what is clarified, what remains valid, or why the blocker is now narrower.

## Direct Clarification

Use when the paper already contains the answer or the reviewer has misunderstood something.

Pattern:

1. Answer directly.
2. Point to the relevant concept, result, or distinction.
3. State what will be clarified in revision if useful.

For major technical blockers, do not stop at “we will clarify.” The clarification promise comes after the substantive answer.

## Technical Bridge

Use when a reviewer is challenging a proof step, oracle assumption, non-standard assumption, or applicability claim.

Pattern:

1. State the shortest defensible technical answer now.
2. Explain why the questioned ingredient is needed or what guarantee it enables.
3. If relevant, explain what changes under a relaxed version.
4. Only then say how the paper text will make this clearer.

If the reviewer is asking “why is this assumption there?” or “why does this bound still hold?”, the response should contain an actual mechanism explanation, not just a scope statement.

For proof-validity, adaptive-sampling, or concentration objections, add one more sentence:

5. Name the proof mechanism or tool class when supportable and state whether it preserves the qualitative rate or only adds a bounded correction term.

If the same assumption or tool already appears in nearby work and that fact is available in the current materials, a light citation can be added to stabilize the answer.

## Assumption Framing

Use when the reviewer questions a non-standard or potentially unrealistic assumption.

Pattern:

1. State whether the assumption is essential to the current guarantee, common in nearby formulations, or replaceable at extra analytical or statistical cost.
2. Explain what the assumption enables.
3. Explain what changes if the assumption is relaxed or estimated.
4. Bound the conclusion: current result, plausible extension, or future work.

When support exists, include at least one stabilizer: nearby precedent, estimability, or an already-used practical surrogate.

If nearby precedent is the strongest stabilizer, mention it briefly in the body and place the full citation in the final `References` section.

## Practicality of Assumptions

Use when the reviewer is not only questioning whether an assumption is theoretically needed, but also whether it is operationally realistic or deployable.

Pattern:

1. State the theoretical role of the assumption or idealized quantity.
2. Say how the needed quantity is computed or approximated when it is known.
3. Say what plug-in estimate, surrogate, or current-context variant is plausible when it is unknown.
4. If supported by the current materials, mention whether experiments or implementation notes already show that the surrogate works well in practice.
5. State the clean theoretical consequence of replacing the idealized object, such as an added estimation-error term or an extra regularity condition.

Preferred content when support exists:

- exact computation or numerical integration when tractable
- Monte Carlo approximation when the expectation is the bottleneck
- estimate-from-data or plug-in distribution strategies when the object is unknown
- one light precedent citation if nearby work estimates the same kind of quantity
- one sentence that the controller logic survives even if the analysis picks up extra error terms

Do not pad this pattern with generic “practicality” language. The answer should make the reviewer feel that the implementation path is concrete.

## Prior-Work Delta

Use when a reviewer claims missing related work or weak novelty positioning.

Pattern:

1. Acknowledge the missing or relevant prior work, or the real overlap the reviewer is pointing to.
2. Gently clarify if the reviewer's framing is broader than the paper's actual claim.
3. State the paper's actual novelty claim at the right scope.
4. Compare along 2-3 explicit axes.
5. State the paper's remaining contribution after the comparison.
6. Then mention the revision action, such as a comparison table or added discussion.

If a genuinely relevant paper or analogy was omitted, say so plainly before moving to the distinctions.

Good comparison axes include:

- setting or problem class
- assumptions or margin conditions
- optimization/control mechanism
- guarantee type
- terminal versus anytime guarantees

When a single cited paper is enough to ground one of the comparison axes, prefer one precise citation over a long citation list.

When overlap is real but the reviewer is over-collapsing the contribution, compare the role of the shared idea in each work, not just whether both papers mention the same topic.

Do not begin with “we agree this is not novel” unless that broad concession is exactly what the paper already claims. Prefer: acknowledge the relevant connection, clarify the scope of the claim without sounding corrective, then state what the paper actually contributes.

## Evidence Reinforcement

Use when the claim is supportable now and the reviewer needs more concrete backing.

Pattern:

1. Direct answer.
2. Concrete evidence.
3. Why that evidence matters for the paper's claim.

## Narrow Concession

Use when the reviewer is partly right.

Pattern:

1. Admit the exact limited point.
2. Bound the damage.
3. Re-state what still holds.
4. If justified, name the tradeoff rather than leaving the weakness unstructured.

## Boundary Setting

Use when the reviewer asks for an extension beyond current scope.

Pattern:

1. Acknowledge the value of the suggestion.
2. Give the shortest credible extension sketch, if one is available from the current framework.
3. State the current scope boundary.
4. Explain what the present results still establish.

If possible, add one operational consequence of the extension, such as one extra queue, an added dependence in the bound, or a theorem that would need re-proving.

## Revision Framing

Use when a point is fixable through exposition, comparison, or added discussion.

Pattern:

1. Give the present answer now.
2. Name the concrete clarification or addition planned in revision.

Prefer manuscript-facing actions over abstract promises. Good revision actions include:

- a comparison table
- a revised definition or theorem statement
- notation alignment between sections
- an added proof sketch step or concentration argument
- a paragraph clarifying the theory/practice split

## Light Citation Support

Use when a technical or theoretical objection becomes easier to answer by noting that a nearby work also uses the same assumption, proof tool, or modeling device.

Pattern:

1. Answer the objection directly.
2. State the role of the disputed assumption or tool.
3. Briefly note that nearby work also uses it, with a lightweight citation marker if supported.
4. Put the full bibliographic entry in a final `References` section.

This pattern is for stabilization, not for literature dumping.

Preferred form:

- In body: `A similar assumption also appears in nearby work [1].`
- At end: `[1] Author(s). Title. Venue, Year.`

## Metric Clarification

Use when the reviewer says the paper mixes up metrics, notation, or theorem claims.

Pattern:

1. State the quantity currently intended.
2. State how it differs from the nearby alternative quantity.
3. Explain which theorem, definition, or notation should align with which quantity.
4. Name the revision that will remove the mismatch.

If the paper uses one quantity operationally inside the algorithm and another at theorem level, preserve that distinction and explain the relationship instead of collapsing them.

## Friendly Reviewer Reinforcement

Use when the reviewer is broadly positive but requests refinement.

Pattern:

1. Preserve alignment.
2. Address the request concretely.
3. Add a concrete reassurance or practical clarification when available.
4. Reinforce the paper's contribution without overselling.

## Scope and Magnitude Interpretation

Use when a reviewer says the baseline set is weak, the gains are small, or the evaluation seems incomplete.

Pattern:

1. State what the current evaluation already covers.
2. State the relevant benchmark, simulator, data, or interface boundary without sounding evasive.
3. Explain why the observed gain size should be concentrated, modest, or heterogeneous based on what part of the pipeline the method actually changes.
4. Then name the clarifying manuscript change or bounded additional evaluation if supported.

This pattern should explain both the evidence boundary and the mechanism-level reason behind the result size.

## Analogy Acknowledge and Differentiate

Use when the reviewer compares the method to a known framework such as MPC, primal-dual control, or a nearby baseline family.

Pattern:

1. Acknowledge the legitimate overlap.
2. State the concrete mechanism that differs.
3. Explain why that difference matters for the paper's guarantee or scope.
4. Then name any clarifying revision.

## Contribution Anchor

Use at the end of a high-risk response when the reviewer could otherwise read the clarification as a concession that collapses the paper.

Pattern:

1. After the technical clarification, name the surviving contribution.
2. Keep it narrow and specific.
3. Avoid turning it into generic self-praise.

## Decision-Relevance Sentence

Use when a reviewer has raised a score-moving blocker and the draft needs to help them update, not just understand.

Pattern:

1. State the technical answer.
2. State the bounded manuscript repair if needed.
3. Add one sentence explaining what this means for the blocker: what no longer fails, what remains valid, or why the contribution still stands.

## Tradeoff Defense

Use when the reviewer points out a real drawback that is tied to a conscious design choice.

Pattern:

1. Admit the drawback precisely.
2. State the benefit or flexibility that comes with it.
3. Bound the tradeoff so it does not swallow the paper.
4. Reconnect to what the paper still establishes.

## Compatibility Defense

Use when a reviewer worries that an oracle, estimator, or subroutine may not remain valid under the paper's sampling or control process.

Pattern:

1. State the strongest defensible compatibility claim.
2. Name the condition under which the compatibility holds.
3. Avoid weakening the claim more than the paper requires.
4. Then explain what proof or exposition will be added.

## Theory-Practice Pairing

Use when the theory relies on an idealized quantity, oracle, or known distribution, but the implementation or experiments use a practical surrogate.

Pattern:

1. State the theoretical role of the idealized quantity.
2. State the practical surrogate or approximation.
3. Explain what remains empirically or theoretically supported under that surrogate.
4. Name the paper text that should make this split explicit.

When the reviewer is explicitly asking whether the assumption is practical, prefer `Practicality of Assumptions` over this shorter pattern.

## Formality Repair

Use when a reviewer says the paper is informal, unclear, or under-specified.

Pattern:

1. State the exact place where the current text is underspecified.
2. Give the missing formal distinction, definition, theorem-layer split, or notation alignment now.
3. Name the concrete manuscript repair.
4. Explain why that repair resolves the reviewer's concern without changing the paper's main claim.

## Bundle Mirroring

Use when one reviewer message contains several substantive objections or numbered items.

Pattern:

1. Keep the reply order aligned with the reviewer order.
2. Give each objection a visible answer slot, even if the answers are concise.
3. Merge only when two objections truly share the same evidence.
4. Preserve scanability over stylistic smoothness.

## Follow-Up Recovery

Use when a reviewer posts a follow-up saying the previous answer did not change the evaluation, or when later-thread context shows which concerns remain active.

Pattern:

1. Name the remaining blocker directly.
2. Give the sharpest available answer to that blocker first.
3. Mention only the minimal supporting repairs needed for context.
4. Keep already-satisfied reviewers brief and supportive.

## Blocker Compression Unit

Use when space is too tight for a full paragraph but the concern is still score-moving.

Pattern:

1. Direct answer in one sentence.
2. One mechanism or reason sentence.
3. One concrete manuscript-action sentence.

Do not spend scarce words on scene-setting if this unit has not yet been delivered.

## Cross-Reviewer Synthesis

Use when several reviewers press on the same blocker or when a short AC-facing synthesis would make the rebuttal easier to trust.

Pattern:

1. State the shared issue in one sentence.
2. State the paper-level clarification or repair in one sentence.
3. Keep reviewer-specific details in the local replies rather than repeating the full synthesis everywhere.

This pattern supplements reviewer-local answers; it does not replace them.

Lead with the clarified claim or surviving contribution, not with a weakness inventory or revision laundry list.

## Positive Support Echo

Use when one or more reviewers are already supportive and that support can reinforce credibility after a substantive answer.

Pattern:

1. Answer the substantive concern first.
2. Briefly note the aspect already recognized positively by another reviewer or by the same reviewer.
3. Use that support as corroboration of value or practicality, not as a substitute for the answer.

If the positive reviewer asked for something concrete, name the concrete addition rather than collapsing it into a generic “we will clarify.”

## Weakness-to-Tradeoff Pivot

Use when you must concede a bounded weakness such as non-zero violation, incomplete extension coverage, or an idealized assumption.

Pattern:

1. State the exact bounded weakness.
2. Name the compensating benefit or flexibility in the same answer.
3. State what core result still stands.
4. Only then mention any clarifying manuscript change.
