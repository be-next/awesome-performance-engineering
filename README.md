# Awesome Performance Engineering [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

<p align="center">
  <img src="media/logo.svg" alt="Awesome Performance Engineering" width="400">
</p>

A curated, opinionated collection of tools and resources dedicated to **Performance Engineering** — the discipline that ensures systems deliver fast, reliable, and cost-efficient experiences at any scale.

This repository covers two complementary and increasingly convergent domains: **Observability** and **Performance Testing**.

## Contents

* [Why This Repository Exists](#why-this-repository-exists)
* [Curated Lists](#curated-lists)
* [Performance Engineering Perspective](#performance-engineering-perspective)
* [Related Awesome Lists](#related-awesome-lists)

---

## Why This Repository Exists

Performance problems don't come from a single component. They emerge from the **complex interplay between architectures, workloads, data patterns, infrastructure decisions, and real user behavior**. Diagnosing them requires both the ability to observe systems as they truly behave and the discipline to test them under realistic conditions.

Yet in practice, observability and performance testing are often treated as separate concerns, owned by different teams, using disconnected toolchains. This fragmentation is one of the main reasons performance issues reach production.

This repository was created with a clear conviction:

> **Performance engineering is a continuous discipline** — not a phase, not a checklist, not a team. It requires combining deep system understanding, realistic validation, and production-grade observability into a coherent practice.

Rather than an exhaustive catalog, this project aims to:

* Highlight **production-grade, field-proven tools** alongside promising emerging solutions
* Bridge the gap between **testing and observability** — because you can't fix what you can't see, and you can't trust what you haven't tested
* Help practitioners **choose tools adapted to their context**, maturity, and constraints
* Provide **opinionated guidance** based on real-world experience, not vendor marketing

---

## Curated Lists

### Awesome Observability Tools

📄 **[awesome-observability-tools.md](awesome-observability-tools.md)**

A curated list of tools enabling **deep, actionable visibility** into modern distributed systems — from kernel-level tracing to full-stack platforms.

Covered domains include:

* Metrics collection & time-series databases — Prometheus, VictoriaMetrics, OpenTelemetry, and beyond
* Distributed tracing — understanding request flows, latency propagation, and dependency chains
* Log management & telemetry pipelines — from ingestion to correlation at scale
* Continuous profiling — always-on, low-overhead production profiling with eBPF and beyond
* Observability platforms — integrated solutions for teams at different maturity levels
* Visualization & dashboards — turning signals into decisions
* AI-augmented observability — ML-powered anomaly detection and root-cause analysis

The focus is on tools that support **high-throughput, large-scale systems** (where sampling strategies and storage costs matter), **cloud-native and hybrid architectures** (Kubernetes, service meshes, serverless, and legacy coexistence), and **production diagnostics and root-cause analysis** (from golden signals to unknown-unknowns).

👉 **Goal:** observe systems as they really behave — not as we assume they behave.

---

### Awesome Performance Testing Tools

📄 **[awesome-performance-testing-tools.md](awesome-performance-testing-tools.md)**

A curated list of tools covering the **full performance testing lifecycle** — from workload design to results analysis, not limited to load generation.

Included categories:

* Load & stress testing — modern, scriptable generators (k6, Gatling, Locust) and protocol-level tools
* HTTP benchmarking — high-precision tools for latency measurement and saturation testing
* API testing & contract testing — validating performance at the service boundary
* Browser & frontend performance — Core Web Vitals, Lighthouse, real-user and synthetic measurement
* Service virtualization & mocking — isolating components for targeted performance testing
* Synthetic data generation — creating realistic datasets that reflect production cardinality and distribution
* Chaos engineering & fault injection — testing resilience and graceful degradation under failure
* CI/CD integration — embedding performance validation into delivery pipelines

Special attention is given to tools that:

* Enable **realistic workloads with production-like data volumes and patterns**
* Support **shift-left performance** — catching regressions early, not just in pre-production
* Integrate with **observability platforms** for closed-loop performance analysis
* Scale from **developer laptop to distributed load generation**

👉 **Goal:** test systems under conditions as close as possible to real life — and make performance feedback continuous, not episodic.

---

## Performance Engineering Perspective

Throughout both lists, tools are annotated with emoji indicators that provide quick guidance. Each list defines its own legend, but the common indicators are:

* ⭐ Widely adopted / reference solution
* 🟢 Actively maintained
* 🔵 Cloud-native / Kubernetes-friendly
* 🟠 Commercial / paid offering
* 🚀 High performance / low overhead
* 📚 Extensive documentation
* 🧠 Observability-first or engineering-first philosophy
* 🧰 Operations heritage / legacy-friendly
* 🔗 CI/CD pipeline-ready
* 🧪 Developer-friendly / PoC-friendly

These are **guidance signals based on field experience**, not absolute classifications. Context always wins over labels.

---

## Related Awesome Lists

This repository complements existing awesome lists while maintaining a distinct focus on performance engineering:

* [awesome-sre-tools](https://github.com/SquadcastHub/awesome-sre-tools) - SRE and production engineering tools covering monitoring, incident response, CI/CD, alerting, and reliability workflows.
* [sre-learning-resources](https://github.com/flanksource/sre-learning-resources) - Learning paths and hands-on resources for building modern SRE skills.
* [awesome-monitoring](https://github.com/Enapiuz/awesome-monitoring) - A broad, well-structured list of monitoring and observability tools covering metrics, logs, traces, alerting, and visualization.
* [awesome-testing](https://github.com/TheJambo/awesome-testing) - Comprehensive overview of software testing methodologies, frameworks, and tools spanning unit, integration, performance, and quality engineering.
* [awesome-chaos-engineering](https://github.com/dastergon/awesome-chaos-engineering) - Chaos engineering principles, experiments, platforms, and resilience learning resources.
* [awesome-kubernetes](https://github.com/run-x/awesome-kubernetes) - Actively maintained Kubernetes list covering tooling, observability, CI/CD, service meshes, operators, and cloud-native patterns.
* [awesome-k8s-security](https://github.com/magnologan/awesome-k8s-security) - Kubernetes security tools, hardening guides, and threat-modeling resources.
* [awesome-scalability](https://github.com/binhnguyennus/awesome-scalability) - Scalability patterns, architectures, and engineering techniques for large-scale distributed systems.

---

## Contributing

Contributions are welcome. Please read **[CONTRIBUTING.md](CONTRIBUTING.md)** and the **[Code of Conduct](code-of-conduct.md)** before submitting changes.

## License

Released under **CC0 1.0 Universal**.
