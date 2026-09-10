# Metric Definitions

**Applies to:** Info-Minimalism Standard v1.0.0

## 1. Measurement basis

Every record declares one attention-cost method. For plain text, the default is a disclosed word-count method. URLs count as one unit unless reading the destination is part of the evaluated boundary; emoji clusters and standalone meaningful symbols count as one unit. For languages without whitespace-delimited words, disclose the tokenizer or segmentation method.

Maintain a cost ledger where applicable:

- `L`: visible lexical units;
- `G`: visible Unicode grapheme clusters;
- `V`: required audio/video seconds;
- `S`: screens or panels traversed;
- `A`: required actions such as expand, swipe, or click;
- `X`: post or channel transitions.

For mixed media, disclose playback speed, inspection assumptions, and whether captions or linked material are included. Do not compare records that use incompatible units. Never sum unlike bases into one attention number.

Exact counts do not imply exact human cost. Layout, familiarity, language, disability, and cognitive complexity remain limitations.

## 2. Required descriptive metrics

### Observed Attention Cost (OAC)

The measured cost of the evaluated boundary in one named cost base.

Report OAC only when the total for the evaluated boundary in that cost base is known. A measurable fragment is not the total for a larger requested boundary: record its count in measurement.boundary_rules, and withhold the whole-boundary OAC. A caveat in a metric's reason does not change its boundary. Partial access can still support an independently observable whole-boundary cost, such as the duration of a complete media file; do not withhold that merely because some meaning cannot be inspected.

`OAC = observed attention units`

### Minimal Adequate Rendering Cost (MARC)

The measured cost of the MAR in the same named cost base. Report when fidelity is confirmed. An uncertain rendering may have its raw count reported with an explicit caveat, but do not present disputed reductions as confirmed savings.

`MARC = MAR attention units`

MARC is evaluator- and context-dependent. It is not a theoretical lower bound.

### Conservative Removable Attention Cost (CRAC)

The sum of non-overlapping, high- or medium-confidence removable units whose lower-cost alternatives preserve meaning and function. If a replacement costs attention units, count only the net reduction.

`CRAC = Σ max(0, observed span cost − replacement cost)`

Do not include low-confidence, contested, or excluded findings. Link each cost row to exactly one scenario and rendering. Allocate net savings to explicit non-overlapping units; the same removal cannot be credited twice within a row. CRAC can differ from `OAC − MARC` because the MAR may reorganize content and repair adequacy gaps.

Canonical display: `CRAC = 7 L (7/16 of OAC)`. Do not write `CRAC = 7/16 L`, which can be mistaken for either a quantity or a ratio.

### Adequacy Repair Cost (ARC)

The estimated new attention units needed to repair reference, labeling, or local-context gaps for the declared encounter context without adding new substantive claims.

`ARC = Σ repair units`

ARC is a non-negative reported estimate (including a demonstrated zero), or withheld with a reason when indeterminate. It is not a safety- or factual-completeness measure.

## 3. Derived metric

### Retained Attention Share (RAS)

The share of observed cost not conservatively identified as removable.

`RAS = (OAC − CRAC) / OAC`

Range: `0–1`; higher means less observed removable burden in the named cost base, not better, truer, safer, or more valuable content.

RAS must be suppressed when OAC is zero, MAR fidelity is `failed`, or the evaluation status is `insufficient_context`. It must be accompanied by ARC. A high RAS with a positive or indeterminate ARC may describe an under-contextualized expression and must not be celebrated as optimized.

No numerical threshold qualifies content. Qualification follows P1 in the Standard; RAS is not a passing score.

Do not produce one RAS across words, seconds, screens, actions, and transitions. A vector of base-specific values is allowed when each numerator and denominator is shown.

## 4. Diagnostic metrics

### Payload Latency (PL)

The cost of complete non-payload segments before the first segment that contributes to a principal payload unit, divided by OAC.

`PL = pre-payload attention units / OAC`

Segment the expression before calculating PL. The first token of the first segment labeled as contributing to principal payload marks onset; do not wait until its complete proposition has been read, and do not treat a topic-only teaser as payload merely because it names the subject. Use PL only when a principal payload is identifiable and early disclosure is functionally appropriate. Mark `not_applicable` for suspense, narrative, humor, pedagogy, or other forms where ordering performs a documented function.

Canonical display: `PL = 3 L (3/25 of OAC)`. Do not write `PL = 3/25 L`.

### Repetition Burden (RB)

The CRAC attributable to same-function restatement, unnecessary recap, or duplicate unchanged propositions.

`RB = removable repetition units`

### Context Overhead (CO)

The CRAC attributable to context that the declared encounter already supplies, including over-specified referents.

`CO = removable contextual units`

### Capture Overhead (CAO)

The CRAC attributable to attention capture or continuation prompts that add no preserved payload or necessary navigation.

`CAO = removable capture units`

### Fragmentation Overhead (FO)

Sequence-only cost created by splitting material across parts: repeated orientation, navigation, connective text, and interaction needed solely because of the split.

`FO = removable split-caused units or estimated attentive seconds`

Do not count a split that is required by platform limits, accessibility, progressive instruction, or distinct update timing.

### Cross-Item Duplication (CID)

Channel-only cost spent restating unchanged propositions beyond the recurrence needed for the declared encounter mode.

`CID = removable duplicate units / OAC across the sample`

Report the numerator and denominator. Exclude genuinely new deltas, necessary standalone orientation, spaced-learning repetition, and required reminders.

CID describes publication-corpus duplication, not duplicated audience exposure. If audience overlap is unknown, say so. Do not multiply speculative audience counts into a headline attention total.

### Update Yield (UY)

For update-oriented channels, the share of sampled attention cost that communicates new or materially changed payload.

`UY = new-or-changed payload units / OAC across the sample`

Use only when the source represents itself as providing updates. Disclose how propositions were matched across items.

Allocate units through annotated spans. Count a span only when it first introduces or materially changes a meaning-ledger entry in the sample. Include the minimum grammar needed to render that delta; exclude stable identity, recap, navigation, and unchanged qualification spans. When a span mixes delta and stable context and cannot be segmented defensibly, mark its allocation uncertain and report a range.

## 5. Uncertainty

Each metric receives confidence `high`, `medium`, or `low` plus a short rationale. Provide a range when two reasonable MARs or context assumptions produce materially different values. Do not average incompatible contexts into one number.

## 6. Anti-gaming rules

- Removing necessary qualifications increases ARC or breaks MAR fidelity; it does not improve the result.
- Replacing readable prose with unexplained abbreviations, dense notation, or link dumping is not valid compression.
- Moving burden outside the boundary requires expanding the boundary or declaring the dependency.
- Splitting one message into many posts does not erase cost; sequence mode includes the full path.
- Repeating content for reach is still attention cost, though encounter mode may make some orientation necessary.
- Fabricated certainty about payload or audience requires abstention, not a favorable estimate.
- A platform constraint may make a cost unavoidable, but does not make it nonexistent; record it as present and constraint-bound.

## 7. Honest structured measurements

Use `reported` with a measured numeric value, or `withheld` / `not_applicable` with `null` and a reason, for each cost metric. Unknown is not zero. Report known whole-boundary OAC even if savings must be withheld. Withhold CRAC and RAS when content cannot be inspected or the linked rendering fails fidelity. Withhold savings affected by unresolved fidelity uncertainty; unaffected demonstrated removals can remain a bounded partial result. Empty meaning and rendering ledgers are correct when nothing can be inspected. No metric is required merely to fill a report.

A row identifies its scenario and rendering, cost basis, and allocation IDs. Repairs are reported separately, not deducted invisibly from savings. Diagnostics identify their numerator, denominator where applicable, and annotated source spans. Arithmetic validation cannot establish semantic preservation or actual audience exposure.
