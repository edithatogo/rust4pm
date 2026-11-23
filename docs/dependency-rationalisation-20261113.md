# Rust dependency rationalisation — rust4pm (2026-11-13)

**Status:** proposal and review contract; no code adoption, runtime verification or benchmark result is claimed here.

## Repository-specific decisions

- This fork is a separately owned upstream-compatible process-mining dependency; downstream Mailweft and FOI Process must not force broad changes onto it.
- **Verified:** `process_mining` already declares optional Polars, Rayon, Itertools, Serde, Criterion and optional durable persistence; proc-macro crate already legitimately uses Syn and Quote.
- **Retain:** domain OCEL algorithms, Petgraph and conversion contracts; investigate existing features rather than adding crates already present.
- **Evaluate:** Proptest for OCEL/ XES imports, lifecycle ordering, duplicate events, interchange and Petri net invariants; Criterion upgrades only after benchmark comparability.
- **Conditional:** Polars version convergence and optional-feature boundaries must be tested with downstream Mailweft/FOI Process, Arrow schema and actual installed consumer resolution.
- **Avoid:** blanket Tokio, Reqwest, SQLx, Ratatui or PyO3; do not alter published external crate API without explicit compatibility evaluation.

## Evidence and release gate
1. Discover actual source, package boundary, MSRV, lockfile, existing tests and Conductor ownership; avoid speculative dependencies.
2. For runtime behaviour, write failing contract tests before implementation, run targeted and full suites; preserve stable schemas, errors, CLI semantics and deterministic outputs.
3. Record `cargo tree -d`, feature selections, security/licensing/advisory reviews, transitive dependency cost and rollback before accepting an adoption.
4. For performance changes, benchmark identical inputs and correctness/invariance oracles; do not claim improvements without measurements.
5. This document is a planning entry, NOT proof of compilation, hosted CI or scientific validation; update status only after a revision-bound receipt.
