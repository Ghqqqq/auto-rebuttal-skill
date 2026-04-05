# OpenReview-Style Sample Response

This sample shows the expected `response_draft` style: reviewer-specific sections, bold topic headings, and topic-level answers.

## Reviewer p36P

**Look-ahead vs. MPC, and k-step variants.** The overlap with one-step MPC/receding-horizon control is real at the level of “evaluate a short-horizon surrogate before acting,” but our look-ahead is specifically over the virtual queues and rectified constraint penalties, not a full state-trajectory planner. That difference matters because the guarantee is tied to queue evolution and estimator-error terms, so the present one-step version is the minimal modular control layer we can analyze cleanly. A `k`-step version looks natural as an extension, but it would require additional predicted future queue states and stronger prediction/control-error control; we will note that boundary explicitly.

**Known context distribution.** The distributional context object is essential to the current mean-field theorem because the budget/constraint terms are defined in expectation over the context marginal. The paper’s practical variant already uses the current observed context directly, so we will state that theory/practice split explicitly. If the distribution is only approximate or noisy, the right reading is that an extra approximation term would enter; that is a plausible extension, not part of the current guarantee.

**Multiple constraints and scope.** The current statement is for one budget queue and one long-term constraint queue, but the control layer is modular: an additional hard constraint would correspond to one additional virtual queue and one extra term in the potential. We will say this explicitly so the extension path is clear, while keeping the theorem as stated for the current constraint set.

## Reviewer sRuk

**Missing related work and positioning.** We agree that this part needs a more explicit comparison. The revision will add a compact related-work discussion that separates the closest constrained online-learning formulations from our setting along three axes: contextual vs. non-contextual actions, the control mechanism, and the guarantee type. That should make the remaining contribution of the paper easy to see.

**Metric terminology.** The quantity intended in the theorem should be aligned explicitly with the theorem-level notation; if the prose elsewhere suggests a different quantity, that is a notation mismatch rather than a different guarantee. We will align the terminology and theorem statement so the same metric is used throughout.

**Proof step and concentration.** The reviewer’s concern is well placed: the stochastic-feedback term should be isolated explicitly before applying the concentration argument. The missing piece is a standard martingale-concentration step on that term, which preserves the qualitative form of the bound and only affects constants or lower-order terms.

## Reviewer mJ77

**Oracle compatibility under partial-information sampling.** The strongest claim we can make is that the oracle assumption is stated at the interface level and is uniform over admissible action-selection rules, so the theorem is meant to apply to the policy-induced sampling process rather than ignore it. We will clarify that interface and the sampling requirement directly.

**Multiple budget constraints.** The extension is natural in this framework: one extra hard budget simply adds one more virtual queue and one more penalty term. The present theorem is written for the current constraint set, but the modular structure is exactly what makes the multi-constraint extension straightforward.

## Reviewer 3r7f

**Positioning and related work.** We agree that the comparison to nearby methods should be sharper. The revision will add a comparison table and a short positioning paragraph that explains how the look-ahead queue update, rectified penalties, and estimator-error-adaptive guarantee differ from the closest baselines.

**Expectation computation in practice.** The expectation over the context marginal is part of the theory-level formulation; the practical variant already uses the observed current context directly. We will state that split explicitly so the paper does not read as if it requires exact online integration in implementation.
