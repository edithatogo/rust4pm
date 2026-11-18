# Specification — Conductor planning: preserve Serde and independent OCEL/XML parsing

## Verified source inventory
- `process_mining/Cargo.toml` declares `serde`, `serde_json`, `serde_with`, `schemars`, `quick-xml`, `csv` and optional Polars/DuckDB/SQLite. Serde participates in event/OCEL DTOs; format encoders, XML recovery, process-mining algorithms and tabular/database integrations remain distinct responsibilities.
- This is an appropriate existing decomposition. The Mailweft integration issue #4 independently qualifies Rust4PM against patched quick-xml security advisories; adding or expanding Serde does not remediate an XML parser vulnerability.
- If unmaintained or multiple XML versions are found, evaluate targeted `quick-xml` upgrade/feature acceptance with import/export and malformed input fixtures, not a replacement by Serde.

## Non-goals
No takeover of process-mining algorithms, graph semantics, persistence or downstream Mailweft/FOI ownership; no changes to crate APIs without upstream and consumer qualification. No broad serde migration; default no-go unless a real repeated handwritten wire codec is identified.
