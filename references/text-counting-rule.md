# Text-Counting Rule

Use `scripts/count_text_cost.js` when an exact lexical-unit count is needed for a plain-text case.

```text
node scripts/count_text_cost.js "Text to count"
```

The script normalizes text to Unicode NFC and counts:

- contiguous letter/number expressions as one unit;
- internal apostrophes and hyphen/colon-linked expressions as part of that unit;
- each displayed HTTP(S) URL or bare domain/path such as `example.org/path` as one unit;
- each matched emoji or joined emoji sequence as one unit.

Punctuation alone is not a lexical unit. The output exposes every token so disputes are inspectable.

This is a version-pinned engineering convention, not a psychological claim. It does not capture syntax, familiarity, visual layout, or cognitive complexity. Cross-language calibration must test whether the rule remains usable; retain grapheme counts as a companion when word segmentation is contested.

The rule is unchanged from alpha.3, including its treatment of `12,400` as two lexical units. Do not present these units as universal word counts or exact human attention.
