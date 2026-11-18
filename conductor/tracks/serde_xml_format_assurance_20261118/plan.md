# Plan — Conductor planning: preserve Serde and independent OCEL/XML parsing

- [ ] Inventory actual Serde DTOs, serde_with adapters, OCEL JSON/XML reader/writer and CSV code, versions and affected downstream APIs.
- [ ] Freeze source-verified XES/OCEL import/export, incomplete/hostile XML, entity/namespace behaviour, oversized files, duplicate JSON keys, precision, timestamps and qualifier preservation; keep data-loss reporting explicit.
- [ ] Qualify quick-xml/security separately with upstream version, pinned source, MSRV, compile/features, independent Mailweft/FOI fixtures; do not infer security from a Serde change.
- [ ] Benchmark any identified repeated manual JSON writing and delete it only where a typed Serde contract yields byte/schema parity and fewer maintenance obligations. Otherwise record no-go.
- [ ] Run exact-head locked tests, fuzz/security/bench and actual downstream consumer qualification. Existing upstream maintainer governance remains authoritative.

