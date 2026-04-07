# Auto Rebuttal Skill

`Auto Rebuttal` is a reviewer-structured skill for drafting paper rebuttals and author responses.

It is designed for cases where:

- reviews contain several distinct technical concerns
- different reviewers need different levels of detail
- novelty, assumptions, metrics, or proof issues must be answered precisely
- the final reply should be organized reviewer-by-reviewer instead of as one generic response

## What It Enforces

- split each review into a reviewer-topic map before drafting
- reply reviewer-by-reviewer
- answer each topic under a bold heading
- open each topic with a compressed short answer before expanding into detail
- stop and consult the author before drafting any topic that requires a strategic stance or new commitment
- separate current evidence, revision commitments, and future work
- preserve distinctions in novelty, metrics, proofs, and assumptions
- allow lightweight references when they directly stabilize a technical or theoretical answer
- turn assumption-practicality objections into theory-plus-implementation answers when the evidence allows it
- answer novelty, motivation, and evaluation objections at the right level: role, mechanism, and scope
- keep replies grounded and concise under tight rebuttal budgets

## Repository Layout

- [SKILL.md](./SKILL.md): main skill definition
- [references/response-patterns.md](./references/response-patterns.md): response modes for common rebuttal situations
- [references/anti-patterns.md](./references/anti-patterns.md): failure modes to avoid
- [references/issue-taxonomy.md](./references/issue-taxonomy.md): concern decomposition guide
- [references/length-and-budgeting.md](./references/length-and-budgeting.md): compression and budgeting rules

## Expected Output Shape

The skill produces four sections:

1. `response_draft`
2. `coverage_map`
3. `evidence_map`
4. `self_report`

Only `response_draft` is meant for the submission system. The other sections are drafting scaffolding.

When helpful, `response_draft` may end with a short `References` section. The body should use citations sparingly.
Use numbered markers such as `[1]` in the body and short final entries like `[1] Author(s). Title. Venue, Year.`

## Recommended Usage

Provide:

- the paper text or a reliable paper summary
- raw review text and any follow-up comments
- venue constraints if known
- approved evidence and approved promises

The skill will:

- decompose concerns into reviewer-specific topics
- triage topics into straightforward vs author-strategy-needed before drafting
- choose a response pattern per topic
- generate reviewer-specific replies with bold topic headings
- keep unresolved claims bounded rather than overstated

## Installation

Place this folder in your local skills directory and load `SKILL.md` as `auto-rebuttal`.
