# Conductor planning: preserve Serde and independent OCEL/XML parsing

[Specification](spec.md) · [Plan](plan.md) · [Metadata](metadata.json)

Rust4PM process_mining already uses serde derive, serde_json, serde_with and schemars; quick-xml and CSV remain essential format parsers and not Serde-replacement candidates.

This is an advisory, supplemental Conductor record; actual implementation is governed by the repository's existing maintainer workflow.
