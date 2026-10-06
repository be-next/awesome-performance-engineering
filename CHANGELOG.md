# Changelog

Notable changes to this list are documented in this file, grouped by date — the list is continuously curated rather than versioned. Format inspired by [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## 2026-10-06

### Removed

- Neosync (Synthetic Data Generation) — repository archived after the project was acquired by Grow Therapy; its README states it is no longer actively maintained.

### Changed

- Audited the 🟢 indicator across all 154 GitHub-hosted entries against the last commit on the default branch rather than GitHub's `pushedAt`, which counts pushes to any branch and overstates activity. Removed 🟢 from Clumsy, HdrHistogram, Step CI, bombardier, sysbench, GoReplay, Lighthouse CI and WebPageTest, none of which had committed in over a year. Added 🟢 to AWS Distributed Load Testing, Graphite, Tsung and Anteon, which are active but carried no such tag.
- Added ⭐ to Puppeteer, Apache Superset and Sentry, where the omission contradicted a direct peer in the same section.

## 2026-10-01

### Changed

- Added the missing indicators to five entries that carried none, applied from verified status: StatsD (⭐ — the line protocol is implemented well beyond the reference daemon, whose last commit is 2025-05-20, so no 🟢), Pinpoint (🟢), Logstash (⭐🟢), mysqlslap (🟢, matching pgbench), and tc (🟢 — shipped by iproute2, last updated 2026-09-21).
- Comcast and Graphite deliberately keep no indicator. Graphite sits in Legacy & Historical, where the absence is the point. Comcast's last commit is 2025-03-20 and its last release 2015, so 🟢 would be wrong and its adoption does not reach the bar the list applies to ⭐; it needs a keep-or-remove decision before it crosses the two-year inactivity rule in March 2027.

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
