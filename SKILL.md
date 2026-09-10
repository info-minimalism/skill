---
name: info-minimalism-evaluation-skill
description: Evaluate or revise social, news, and educational posts, threads, and channels for avoidable attention cost. Support publisher self-certification and community checks under the pinned Info-Minimalism Standard. Excludes entertainment, fact-checking, and overall quality scores.
---

# Info-Minimalism Evaluation

Use Info-Minimalism Standard v1.0.0.

## Choose the task

Read [the Standard](references/standard-v1.0.0.md) and the relevant [mode procedure](references/mode-procedures.md) before evaluating. Use message, sequence, or channel mode; these are content boundaries, not separate quality ratings.

- **Reader check:** give a brief result by default.
- **Revision:** show the revised content first.
- **Publisher pre-publication check, declaration, or community challenge:** also read [publisher self-certification](references/publisher-self-certification.md).
- **Exact measurements or JSON:** read [metric definitions](references/metric-definitions.md), and use [the result schema](references/evaluation-result.schema.json) for JSON. The [counting rule](references/text-counting-rule.md) and `scripts/count_text_cost.js` provide reproducible text counts.
- **Evaluator testing:** also read [calibration](references/calibration-method.md).

## Evaluate without adding reader homework

1. Inspect the content or supplied link. Record what was actually accessible, the boundary, audience, encounter, context, language/accessibility needs, and date. For a channel, choose a disclosed sample before judging it. Unknown content is not zero burden.
2. Map meaning, qualifications, and necessary functions before cutting. Start context at zero; preserve only what the actual audience needs. Don't invent an uninformed reader to justify full names, recaps, or introductory padding.
3. Produce a practical lower-cost rendering where possible. Keep natural language, meaning, qualifications, accessibility, and necessary local context. An already efficient original may be its own best rendering.
4. Identify only supported lower-cost alternatives, using the [burden taxonomy](references/burden-taxonomy.md). Record the affected meaning and any plausible necessity. Exclude low-confidence and contested removals from conservative savings. Keep needed context repairs separate.
5. Check fidelity and material uncertainty. Keep different encounter assumptions and renderings separate. Never sum words, seconds, screens, or actions, infer creator effort, or manufacture an overall score.
6. Keep enough supporting evidence to explain the decision: inspected material, context, meaning map, rendering/fidelity, findings, repairs, and limits. For saved or machine-readable records use the full schema; don't claim a file exists unless it was created. Counting is optional unless a number is useful or requested.

Entertainment content is entirely outside this method. Evaluate only the in-scope portion of mixed sources. Do not turn leisure into an audit.

The method does not assess truth, safety, importance, morality, or general editorial quality. A loud or vague headline can be an attention finding when the accessible content demonstrates an unnecessarily delayed main point; do not infer dishonesty or invent the hidden answer from a headline alone.

## Keep the response short

For an ordinary check, give the main finding, a useful rewrite or one concrete example, and any limit that changes the decision. Mention the pinned version unobtrusively. Don't dump the meaning ledger, taxonomy, every metric, or a certification disclaimer into a short reader answer. Provide them if requested or needed to explain uncertainty.

For revisions, lead with the revision and flag only consequential changes or unresolved meaning risks. A proposed revision is not automatically a completed P1 check of the final publication.

For unavailable material, say what you couldn't inspect and request the content or accessible link if needed. Don't invent a rendering, fabricate measurements, or call the content compliant. For entertainment, explain the exclusion briefly and stop.

## Publisher feedback

Evaluate first; draft the shortest civil feedback supported by one clear finding and one practical change. Include https://github.com/info-minimalism/skill when useful. A demonstrated unnecessary delay or repetition can be described as an attention-contract problem; this does not establish creator intent, truth, or a whole source's behavior.

If no problem is demonstrated, say so instead of fabricating a complaint. Show drafted feedback for review. An evaluation request does not authorize posting, changing a bio, contacting a publisher, or publishing a mark. Don't promise search demotion or exclusion from AI citations, or organize mass complaints.

## Publisher outcomes

P1 concerns a complete check of the exact final content, not a passing score. Follow the publisher reference for release verification, every-publication checks, declaration wording, and objections. Do not turn sample evaluations into source-wide approval or claim that multiple agents used by one publisher are independent certification.

A complete P1 check may establish that the exact final content meets v1.0.0. Confirm the latest published version separately before recommending it for the publisher's every-publication commitment. The publisher may self-certify using the declaration; the agent does not issue a certificate. Do not automatically upgrade the skill, install remote code, or publish anything as a side effect of evaluation.
