# Changelog

Notable changes to this list are documented in this file, grouped by date — the list is continuously curated rather than versioned. Format inspired by [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## 2026-08-06

### Added

- PageSpeed.ONE (Browser & Frontend Performance) — synthetic speed testing combined with historical CrUX field data; the entry links to the English site since the bare domain serves the Czech locale.

### Fixed

- Restored the Keep (Alerting & Incident Response) and SpeedCurve (Browser & Frontend Performance) entries, which had lost the line break separating them from the preceding entry and no longer rendered as list items. Neither `awesome-lint` nor `markdownlint` reports this defect.

### Changed

- Rewrote the contribution guidelines: the documented entry format no longer matched the one `awesome-lint` enforces, and the guidelines still invited learning resources that the single-file list has no section for. Added a submission policy covering disclosure and bulk cross-list submissions.

## 2026-07-17

### Added

- HyperDX and Axiom (Observability Platforms).
- Odigos (Profiling & Continuous Performance Analysis).
- incident.io (Alerting & Incident Response).
- pganalyze (Database Observability).
- HolmesGPT (AI-Augmented Observability) — CNCF sandbox.
- Goose (Load & Stress Testing).
- autocannon and Criterion.rs (HTTP Benchmarking & Micro-Benchmarking) — Criterion.rs now lives under the `criterion-rs` organization; the original `bheisler` repository is unmaintained.
- NoSQLBench (Database Performance Testing & Benchmarking).
- DebugBear (Browser & Frontend Performance).
- Azure Chaos Studio (Chaos Engineering & Fault Injection).
- CodSpeed (CI/CD Integration & Performance Gates).

## 2026-07-15

### Added

- GreptimeDB (Metrics Collection & Time-Series Storage).
- py-spy, pprof, and JDK Mission Control (Profiling & Continuous Performance Analysis) — sampling and production profilers for Python, Go, and the JVM.
- OpenObserve (Observability Platforms).
- pgBadger (Database Observability).
- K8sGPT (AI-Augmented Observability) — CNCF sandbox.
- Gatus (Synthetic Monitoring).
- Fortio and k6 Studio (Load & Stress Testing).
- JMH and hyperfine (HTTP Benchmarking & Micro-Benchmarking).
- Bruno and Schemathesis (API Testing & Contract Testing).
- Unlighthouse (Browser & Frontend Performance).
- Toxiproxy (Network Simulation & Traffic Shaping).
- Bencher (CI/CD Integration & Performance Gates).

### Changed

- Replaced Grafana Beyla with OpenTelemetry eBPF Instrumentation (OBI) — Grafana Labs donated Beyla to OpenTelemetry in May 2025; `grafana/beyla` is now a downstream distribution of the upstream project.
- Moved Redash from Legacy & Historical back to Visualization & Dashboards — the project was revived as a community-maintained effort with regular releases (v26.3.0, March 2026).
- Dropped the active (🟢) indicator from Chaos Monkey — no commits since October 2024.
- Fixed NeoLoad capitalization.

### Removed

- Dredd — repository archived by its owner in November 2024; last release dates from 2021.
- Grafana OnCall — OSS project entered maintenance mode in March 2025 and was archived on 2026-03-24; superseded by the commercial Grafana Cloud IRM.
- Yellowlab Tools — no maintainer activity since November 2023.
- Moogsoft — absorbed into Dell AIOps following the 2023 acquisition; no longer a standalone product.
