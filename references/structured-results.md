# Structured results

Full JSON is for saved evidence, integrations, or an explicit request. It is not the default reader response. Follow [the schema](evaluation-result.schema.json); do not replace missing knowledge with values merely to satisfy it.

## Record relationships

- `scenarios` identify audience/encounter assumptions. A rendering uses `rendering_id` and `scenario_id`.
- Each cost row identifies one scenario, rendering, and cost basis. Use a null rendering reference when none can be supported; MAR cost and savings then stay withheld.
- Each cost metric has `status`, `value`, and `reason`. `reported` requires a measured number. `withheld` and `not_applicable` require null, not a guessed zero.
- Findings link to meaning entries, scenarios, and renderings. Keep excluded or contested findings and their reasons visible. Material unresolved disputes block P1 even though contested costs are excluded from conservative savings.
- `crac_allocations` name a finding, the observed boundary, and a half-open interval `[start, end)` in the declared cost units. The interval length equals observed units; deduct replacement units. Within a cost row, use each interval once. Keep the unit-to-content mapping inspectable in the boundary/location descriptions.
- `qualification` describes only the exact final content in the record and the named scenarios. It does not record a publisher's ongoing declaration. Content may meet the pinned version’s requirements while latest-version use remains unverified.
- `qualification.local_context_repair_needed` is `true` when a repair is needed, `false` when no repair is needed for the evaluated context, and `null` when that cannot be determined. Explain unknowns in `qualification.reason`; don't use false to mean “not assessed.” Only false can support `meets_requirements`.
- `latest_standard` records an actual lookup or its absence. Do not use an installed copy alone or a test fixture to make a live claim about the latest stable release.

Unavailable whole content may correctly have empty meaning/rendering/finding ledgers and withheld measurements. A separately inspected headline is not a complete article evaluation. Channel records disclose the sample and access limits; numbers never establish actual audience exposure.

## Validate

Run:

```text
node scripts/validate_result.js path/to/result.json
```

The optional validation helper needs Node and Python with the `jsonschema` package. Set `INFO_MINIMALISM_PYTHON` to the Python executable if it is not `python`; its normal module path, including `PYTHONPATH`, is respected. Missing dependencies produce exit code 2, not a validation pass. Evaluation and text counting do not require Python.

The helper applies the complete Draft 2020-12 schema with format checking, then checks references, non-overlap, arithmetic, and several qualification blockers. Exit 0 means these checks passed; exit 1 means a schema or relational failure. It does not prove preservation, honest sampling, authentic release metadata, or continued publisher adherence. Inspect those substantively.
