# Info-Minimalism Standard

**Version:** 1.0.0  
**Status:** stable  
**Primary domain:** informational social posts, messages, sequences, and recurring channels

## 1. Purpose

This standard evaluates the observable attention-cost optimization of an expression. It asks:

> How much of the attention imposed by this expression was necessary to communicate its expressed meaning in the declared context?

It does not infer how much effort the creator made. It examines the result available to a consumer.

## 2. Non-claims

An evaluation under this version is not a judgment of truth, evidence quality, safety, legality, morality, importance, artistic merit, creator intent, or overall content quality. An item evaluation is not a publisher declaration or a guarantee about future publications. A pinned evaluation alone does not establish that the latest published Standard was used; verify the release separately.

A compact message may be false, harmful, or useless. A long message may be well optimized because its complexity is necessary. The method evaluates neither proposition as good merely because it is short.

## 3. Evaluation units

Choose exactly one mode:

- **message:** one bounded post, message, caption, email item, or equivalent expression;
- **sequence:** an ordered multipart expression such as a thread, carousel, or intentionally linked post series;
- **channel:** a disclosed sample window from a recurring source.

A title is never required. The evaluator must not invent a promise from a title when the evaluated surface has none.

Entertainment content is outside this method, regardless of length or quality. For mixed sources, declare and inspect only the social, news, educational, or other in-scope non-entertainment content. Return `out_of_scope` for entertainment-only requests without assigning burden scores.

See [mode procedures](mode-procedures.md).

## 4. Required context record

Every evaluation must disclose:

1. the exact evaluated boundary;
2. the platform or delivery surface;
3. the assumed encounter mode: `isolated`, `in_sequence`, `subscriber_timeline`, or `other`;
4. the supplied surrounding context;
5. the intended or reasonably apparent audience assumption;
6. the language and accessibility assumptions;
7. the attention-cost measurement method.

Start with no added context, then retain only what the declared audience needs. For readers who already know who Trump is, “Trump” is sufficient; a full name and office need a concrete reason. Do not invent an uninformed audience to preserve routine padding. Equally, do not assume unavailable facts merely because a reader could search for them. Keep context needed to understand the stated meaning in the actual encounter. Evaluations made under different encounter assumptions are not directly comparable.

If material context is unavailable and reasonable alternatives would change the result, return `insufficient_context` or a bounded `partial` result. Do not choose the interpretation that makes the content appear most bloated.

Every admitted context claim must identify its tier:

- `C0_artifact`: present inside the evaluated unit;
- `C1_encounter`: visible in the same screen, parent, thread, or attached material;
- `C2_audience`: stable knowledge reasonably attributable to the declared audience and explicitly documented;
- `C3_external`: supplied interpretation or background not ordinarily available at encounter.

C0–C2 may support the primary result. C3 may support a labeled sensitivity case but must not silently excuse opacity or create redundancy. The evaluated relation is:

`artifact × boundary × audience × admitted context × encounter model`

## 5. Expressed payload and meaning ledger

Before identifying burden, record the expression's payload as one or more meaning units. A meaning unit is a proposition, instruction, distinction, question, or functional communicative effect that would materially change the expression if removed.

Record material qualifications with the unit they constrain. Do not decide whether a meaning unit is true, important, or well supported. Do not upgrade implications into facts the expression did not state.

Each meaning-ledger entry records its type, evidence location, context tier, role (`core`, `supporting`, or `incidental`), confidence, and dependencies. Meaning can be propositional, directive, qualifying, relational, affective, aesthetic, navigational, or accessibility-related. `Incidental` does not mean removable.

Before counterfactual search, also record **preservation constraints** that a rendering must satisfy but that should not be converted into a fabricated common cost unit. Examples include independent shareability, local readability, search retrieval, accessibility equivalence, and ordered pedagogical dependence.

## 6. Minimal adequate rendering

Construct a **minimal adequate rendering (MAR)**: the most attention-economical practical rendering the evaluator can produce while preserving, for the declared context:

- every expressed meaning unit;
- stance, modality, and material qualifications;
- referents and transitions required for comprehension;
- accessibility or safety language that performs a necessary function;
- rhetorical, emotional, pedagogical, or social effects when they are part of the expression's apparent communicative function;
- format elements required by the delivery surface.

The MAR is a documented counterfactual, not a uniquely correct rewrite. It must read as usable content, not telegraphic notes. Personal stylistic preference is not evidence of removable burden. It must remain feasible within the original medium's ordinary capabilities; cross-medium alternatives are labeled separately.

If one alternative reduces words but increases decoding, navigation, or another cost, report both as a Pareto set rather than pretending unlike burdens cancel each other. “Publish nothing” is outside the MAR search because the method evaluates how economically the expressed meaning is communicated, not whether it should exist.

Set MAR fidelity to `confirmed`, `uncertain`, or `failed` and explain any disputed loss. If fidelity is `failed`, do not calculate savings-based metrics.

## 7. Burden annotation

Annotate observed spans or sequence events only when a concrete alternative preserves function with lower attention cost. Each finding must include:

- the observed span or event;
- burden category;
- proposed treatment: delete, replace, merge, move, or consolidate;
- the lower-cost alternative;
- why expressed meaning and function are preserved;
- estimated removable attention units;
- confidence: `high`, `medium`, or `low`;
- any plausible reason the material may be necessary.

Low-confidence findings remain visible but are excluded from the conservative removable-cost total. See the [burden taxonomy](burden-taxonomy.md).

## 8. Adequacy gaps

Record an **adequacy gap** when the observed expression is so compressed or context-dependent that a consumer in the declared encounter context needs added words, labels, or links to identify its expressed payload reliably. This is not a general completeness or safety audit.

Examples include an unresolved pronoun in an isolated post, an unlabeled number, or a sequence part that cannot be understood without an undisclosed earlier item.

Estimate the attention units needed to repair the communicative gap. If repair would require guessing an unstated substantive claim, return `insufficient_context` rather than inventing it.

## 9. Metrics

Report the required descriptive metrics and only the applicable diagnostic metrics defined in [metric definitions](metric-definitions.md). All values are estimates tied to the disclosed cost method and context.

The cost ledger may contain lexical units, grapheme clusters, media seconds, screens or panels, required actions, and content transitions. Do not add unlike units into a single quantity. Savings ratios are calculated within one disclosed cost base.

No metric is an overall score or a passing threshold. In particular, Retained Attention Share must never be shown without the adequacy-gap result, MAR, and annotated findings.

## 10. Mode extensions

Sequence mode additionally evaluates fragmentation overhead, repeated orientation, suspense withholding, and cross-part duplication.

Channel mode additionally evaluates cross-item duplication and update yield within a disclosed sample. It must distinguish continuous subscriber consumption from isolated algorithmic encounter, because recap can be necessary in one and redundant in the other.

## 11. Required output

A conforming record contains:

1. standard version, release status, and evaluation date;
2. mode and evaluation status;
3. boundary, context, audience, and cost method;
4. payload map;
5. preservation constraints;
6. MAR and fidelity assessment;
7. burden findings and adequacy gaps;
8. required and applicable metrics;
9. sequence or channel findings when applicable;
10. uncertainty, limitations, and plausible counterinterpretations;
11. qualification, if requested, limited to the actual final content and pinned version; separately identify any publisher declaration.

Uncertainty is reported separately for evidence completeness, meaning recovery, MAR fidelity, and—where relevant—exposure assumptions. Do not average these axes into one confidence score.

The [JSON Schema](evaluation-result.schema.json) defines the machine-readable record.

## 12. P1: qualification of final content

Content meets the requirements only after a complete evaluation of the final version establishes all of the following:

- Every demonstrated high- or medium-confidence finding of avoidable attention cost is resolved.
- Meaning and function are preserved.
- No needed local-context repair remains.
- No unresolved uncertainty or material dispute could change the outcome.

A demonstrated finding needs an observed span or event and a practical, lower-cost alternative that preserves meaning and function. A publisher may reject a suggested edit with concrete evidence that it removes necessary meaning or function. Preference, inconvenience, or an agent majority is not resolution. Retain disputed and excluded findings with reasons; exclude them from conservative savings, but an unresolved material dispute still blocks qualification.

Use `meets_requirements`, `revision_needed`, `undetermined`, or `out_of_scope`, and state the reason. These outcomes concern the exact evaluated content, not a whole source's reliability. Partial access, uncertain preservation that affects the outcome, or an unknown needed repair requires `undetermined`. Efficient unchanged content can meet P1: do not invent cuts to demonstrate work.

Recheck the final version after edits. A diagnosis that the original needs revision and a promising proposed rewrite do not constitute a completed evaluation of that rewrite.

## 13. The publisher's checkmark

A checkmark on a website or channel profile is an honest public commitment to evaluate **every new in-scope publication before release**, using the **latest published Standard at that time**, and resolve findings under P1. It starts on the declared adoption date. A past sample is supporting evidence, not a replacement for that continuing routine.

The publisher self-certifies; no central permission, registry, independent reviewer, appeal system, or renewal schedule is required. Readers can inspect evidence or raise concrete objections through an ordinary feedback route. Optional independent review must be described accurately. The expected benefit is greater loyalty from existing and potential consumers, not guaranteed growth or a duty to trust.

Read [publisher self-certification](publisher-self-certification.md) for the declaration and workflow. Distinguish:
1. a version-pinned evaluation of specific content;
2. a publisher's continuing declaration;
3. evidence about whether the publisher has kept that declaration.

None of these is a truth or safety certificate. Absence of the mark is not evidence of waste. Self-certification rests on good faith and scrutiny; dishonest use is possible.

## 14. Version and output rules

Use “Evaluated under Info-Minimalism Standard v1.0.0” for this package. A latest-version claim requires the separate release check. Test declarations must be labeled “TEST ONLY — not a live certification.”

A publisher may use “Info-Minimalism — publisher self-certified” with the ongoing declaration. Avoid “independently certified,” “proof,” or unqualified “verified” when only self-evaluation exists.

For ordinary readers, lead with the useful conclusion or revision, one supported example, and any material limit. Keep the supporting record available in the evaluation session; do not imply it has been saved or publicly linked unless it has. Full JSON is optional unless requested. In a publisher workflow, retain a dated, version-pinned evaluation record with the final content and relevant context before recommending P1 qualification.

Prefer inspectable findings over numerical neatness. The Standard evaluates unnecessary work imposed by expression, not whether a reader ought to care about the topic.
