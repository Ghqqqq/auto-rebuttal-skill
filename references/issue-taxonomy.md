# Issue Taxonomy

Use this file when reviews mix several concern types in one paragraph.

Common categories:

- `novelty`: overlap with prior work, missing related work, unclear delta
- `assumptions`: unrealistic assumptions, hidden requirements, scope limits
- `theory-rigor`: proof gaps, theorem conditions, notation mismatch, missing derivation detail
- `empirical-support`: missing experiments, weak ablations, unsupported claims
- `baseline-comparison`: unfair or incomplete comparisons, missing settings, weak positioning
- `clarity`: unclear definitions, hard-to-follow writing, vague section transitions
- `significance`: limited impact, narrow applicability, unclear practical value
- `reproducibility`: omitted implementation details, ambiguous setup, unavailable artifacts
- `scope`: concern about generalization, limitations, or unsupported extensions

For each concern, also tag:

- reviewer stance: `positive`, `mixed`, `skeptical`, `negative`
- response priority: `must-answer`, `important`, `nice-to-address`

When a concern spans multiple types, choose the primary type by asking:

1. What would most likely change the reviewer score?
2. What evidence would best resolve the concern?

Do not over-split trivial wording comments, but do split bundled substantive objections.
