# Awesome Performance Engineering

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![Lint Markdown](https://github.com/be-next/awesome-performance-engineering/actions/workflows/lint.yml/badge.svg)](https://github.com/be-next/awesome-performance-engineering/actions/workflows/lint.yml)
[![Check Links](https://github.com/be-next/awesome-performance-engineering/actions/workflows/links.yml/badge.svg)](https://github.com/be-next/awesome-performance-engineering/actions/workflows/links.yml)

A curated, opinionated collection of tools and resources dedicated to **Performance Engineering** — the discipline that ensures systems deliver fast, reliable, and cost-efficient experiences at any scale.

This repository covers two complementary and increasingly convergent domains: **Observability** and **Performance Testing**.

---

## 🎯 Why This Repository Exists

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

## 📋 Curated Lists

### 🔭 Awesome Observability Tools

📄 **[awesome-observability-tools.md](awesome-observability-tools.md)**

A curated list of tools enabling **deep, actionable visibility** into modern distributed systems — from kernel-level tracing to full-stack platforms.

Covered domains include:

* **Metrics collection & time-series databases** — Prometheus, VictoriaMetrics, OpenTelemetry, and beyond
* **Distributed tracing** — understanding request flows, latency propagation, and dependency chains
* **Log management & telemetry pipelines** — from ingestion to correlation at scale
* **Continuous profiling** — always-on, low-overhead production profiling with eBPF and beyond
* **APM & observability platforms** — integrated solutions for teams at different maturity levels
* **Visualization, dashboards & exploration** — turning signals into decisions
* **Open standards** — OpenTelemetry as the unifying layer of modern observability

The focus is on tools that support:

* **High-throughput, large-scale systems** — where sampling strategies and storage costs matter
* **Cloud-native and hybrid architectures** — Kubernetes, service meshes, serverless, and legacy coexistence
* **Production diagnostics and root-cause analysis** — from golden signals to unknown-unknowns

👉 **Goal:** observe systems as they really behave — not as we assume they behave.

---

### 🚀 Awesome Performance Testing Tools

📄 **[awesome-performance-testing-tools.md](awesome-performance-testing-tools.md)**

A curated list of tools covering the **full performance testing lifecycle** — from workload design to results analysis, not limited to load generation.

Included categories:

* **Load & stress testing** — modern, scriptable generators (k6, Gatling, Locust) and protocol-level tools
* **HTTP benchmarking** — high-precision tools for latency measurement and saturation testing
* **API testing & contract testing** — validating performance at the service boundary
* **Browser & frontend performance** — Core Web Vitals, Lighthouse, real-user and synthetic measurement
* **Service virtualization & mocking** — isolating components for targeted performance testing
* **Synthetic data generation** — creating realistic datasets that reflect production cardinality and distribution
* **Chaos engineering & fault injection** — testing resilience and graceful degradation under failure
* **CI/CD integration** — embedding performance validation into delivery pipelines

Special attention is given to tools that:

* Enable **realistic workloads with production-like data volumes and patterns**
* Support **shift-left performance** — catching regressions early, not just in pre-production
* Integrate with **observability platforms** for closed-loop performance analysis
* Scale from **developer laptop to distributed load generation**

👉 **Goal:** test systems under conditions as close as possible to real life — and make performance feedback continuous, not episodic.

---

## 🧭 Performance Engineering Perspective

Throughout both lists, tools are annotated with emoji indicators that provide quick guidance. Each list defines its own legend, but the common indicators are:

| Indicator | Meaning |
| --------- | ------- |
| ⭐ | Widely adopted / reference solution |
| 🟢 | Actively maintained |
| 🔵 | Cloud-native / Kubernetes-friendly |
| 🟠 | Commercial / paid offering |
| 🚀 | High performance / low overhead |
| 📚 | Extensive documentation |
| 🧠 | Observability-first or engineering-first philosophy |
| 🧰 | Operations heritage / legacy-friendly |
| 🔗 | CI/CD pipeline-ready |
| 🧪 | Developer-friendly / PoC-friendly |

These are **guidance signals based on field experience**, not absolute classifications. Context always wins over labels.

---

## 🤖 Performance Engineering in the Age of AI

AI is not just another buzzword in the performance engineering landscape — it is actively reshaping how we observe, test, diagnose, and optimize systems. Understanding where AI delivers real value today and where it is heading is essential for any performance practitioner.

### What AI Is Already Changing

**Anomaly detection and intelligent alerting.** Traditional threshold-based alerting generates noise. ML-driven systems (Dynatrace Davis, Datadog Watchdog, Moogsoft, and emerging open-source approaches) learn baseline behavior and surface meaningful deviations — reducing alert fatigue and accelerating detection of novel issues.

**Automated root-cause analysis.** Correlation across metrics, traces, and logs is where AI excels. Platforms increasingly automate the tedious work of tracing a user-facing symptom back through service dependencies to an infrastructure root cause — work that used to require senior engineers and hours of investigation.

**Predictive capacity planning.** ML models trained on historical metrics and workload patterns can forecast resource exhaustion, scaling needs, and SLO violations before they occur — shifting performance management from reactive to proactive.

**Intelligent load test design.** AI can analyze production traffic patterns (request distributions, user journeys, data cardinality) and generate load test scenarios that are statistically representative of real workloads — addressing one of the oldest challenges in performance testing: test realism.

**Log analysis and pattern recognition.** LLMs and NLP techniques are transforming how we query and understand log data. Natural language interfaces for observability (asking "why is the checkout service slow?" instead of writing PromQL) are moving from prototype to product.

### What AI Will Transform Next

**Autonomous remediation loops.** The trajectory points toward systems that not only detect and diagnose issues but also execute corrective actions — auto-scaling, traffic shifting, circuit breaking — with human approval gradually becoming optional for well-understood failure modes.

**Performance copilots.** AI assistants that understand your specific architecture, SLOs, and historical patterns. They will help write performance tests, interpret flame graphs, suggest optimization targets, and review capacity plans — functioning as tireless junior performance engineers.

**Continuous optimization.** Instead of periodic tuning exercises, AI-driven systems will continuously adjust JVM parameters, database connection pools, cache configurations, and infrastructure sizing based on observed behavior — a shift from "set and forget" to "observe and adapt."

**Shift from dashboards to conversations.** The next generation of observability interfaces may be conversational rather than visual. Instead of navigating dashboard hierarchies, engineers will describe what they need to understand, and AI will synthesize the relevant signals into a coherent narrative.

### A Practitioner's View

AI amplifies the performance engineer's capabilities but does not replace the need for **system thinking, architectural judgment, and domain expertise**. The most impactful use of AI in performance engineering is not replacing humans — it is eliminating the drudgery (alert triage, manual correlation, repetitive test scripting) so engineers can focus on the work that requires understanding: capacity decisions, architecture trade-offs, and reliability strategy.

The tools in this repository are selected with this pragmatic view: we highlight AI-augmented capabilities where they exist, but we value **proven engineering fundamentals** over hype.

---

## 🔗 Related Awesome Lists

This repository complements existing awesome lists while maintaining a distinct focus on performance engineering:

### 🚀 Site Reliability Engineering (SRE)

[![GitHub stars](https://img.shields.io/github/stars/SquadcastHub/awesome-sre-tools?style=social)](https://github.com/SquadcastHub/awesome-sre-tools)
![Last commit](https://img.shields.io/github/last-commit/SquadcastHub/awesome-sre-tools)

* **[awesome-sre-tools](https://github.com/SquadcastHub/awesome-sre-tools)** — SRE and production engineering tools covering monitoring, incident response, CI/CD, alerting, and reliability workflows.

[![GitHub stars](https://img.shields.io/github/stars/flanksource/sre-learning-resources?style=social)](https://github.com/flanksource/sre-learning-resources)
![Last commit](https://img.shields.io/github/last-commit/flanksource/sre-learning-resources)

* **[sre-learning-resources](https://github.com/flanksource/sre-learning-resources)** — Learning paths and hands-on resources for building modern SRE skills.

### 📊 Monitoring & Observability

[![GitHub stars](https://img.shields.io/github/stars/Enapiuz/awesome-monitoring?style=social)](https://github.com/Enapiuz/awesome-monitoring)
![Last commit](https://img.shields.io/github/last-commit/Enapiuz/awesome-monitoring)

* **[awesome-monitoring](https://github.com/Enapiuz/awesome-monitoring)** — A broad, well-structured list of monitoring and observability tools covering metrics, logs, traces, alerting, and visualization.

### 🧪 Testing

[![GitHub stars](https://img.shields.io/github/stars/TheJambo/awesome-testing?style=social)](https://github.com/TheJambo/awesome-testing)
![Last commit](https://img.shields.io/github/last-commit/TheJambo/awesome-testing)

* **[awesome-testing](https://github.com/TheJambo/awesome-testing)** — Comprehensive overview of software testing methodologies, frameworks, and tools spanning unit, integration, performance, and quality engineering.

### 💥 Chaos Engineering

[![GitHub stars](https://img.shields.io/github/stars/dastergon/awesome-chaos-engineering?style=social)](https://github.com/dastergon/awesome-chaos-engineering)
![Last commit](https://img.shields.io/github/last-commit/dastergon/awesome-chaos-engineering)

* **[awesome-chaos-engineering](https://github.com/dastergon/awesome-chaos-engineering)** — Chaos engineering principles, experiments, platforms, and resilience learning resources.

### ☸️ Kubernetes & Cloud-Native

[![GitHub stars](https://img.shields.io/github/stars/run-x/awesome-kubernetes?style=social)](https://github.com/run-x/awesome-kubernetes)
![Last commit](https://img.shields.io/github/last-commit/run-x/awesome-kubernetes)

* **[awesome-kubernetes](https://github.com/run-x/awesome-kubernetes)** — Actively maintained Kubernetes list covering tooling, observability, CI/CD, service meshes, operators, and cloud-native patterns.

[![GitHub stars](https://img.shields.io/github/stars/magnologan/awesome-k8s-security?style=social)](https://github.com/magnologan/awesome-k8s-security)
![Last commit](https://img.shields.io/github/last-commit/magnologan/awesome-k8s-security)

* **[awesome-k8s-security](https://github.com/magnologan/awesome-k8s-security)** — Kubernetes security tools, hardening guides, and threat-modeling resources.

### 📈 Scalability & Distributed Systems

[![GitHub stars](https://img.shields.io/github/stars/binhnguyennus/awesome-scalability?style=social)](https://github.com/binhnguyennus/awesome-scalability)
![Last commit](https://img.shields.io/github/last-commit/binhnguyennus/awesome-scalability)

* **[awesome-scalability](https://github.com/binhnguyennus/awesome-scalability)** — Scalability patterns, architectures, and engineering techniques for large-scale distributed systems.

---

## 🤝 Contributing

Contributions are welcome and encouraged.

Before contributing, please read **[CONTRIBUTING.md](CONTRIBUTING.md)**.

### We welcome

* New tools that fit the performance engineering scope
* Improvements to descriptions or categorization
* Corrections to broken or outdated links
* New categories backed by concrete use cases
* References to high-quality learning resources

### We avoid

* Unmaintained or abandoned tools
* Tools without documentation or public references
* Duplicate entries
* Purely promotional or marketing-driven content

The objective is to keep the lists **useful, credible, and sustainable over time**.

---

## 🔍 Quality & Maintenance

This repository relies on automated quality checks:

* Link validation (PR, main branch, scheduled)
* Markdown linting
* Spell checking

Automation helps, but **curation remains a human responsibility**.

---

## 📚 Learning Resources

Both lists include references to:

* Books and long-form articles
* Official documentation and specifications
* Community blogs and conference talks
* Standards and best practices related to performance engineering

The intent is to support **learning and skill progression**, not just tool selection.

---

## 🌐 About idle-ti.me

This repository is part of the broader **idle-ti.me** initiative, which explores:

* Performance and resilience of information systems
* Observability practices and tooling
* Feedback from real-world, production environments

The GitHub repository serves as a **technical reference**, while idle-ti.me provides additional context through articles, analyses, and experiments.

---

## 📄 License

This work is released under the **CC0 1.0 Universal** license.

You are free to use, share, and adapt it without restriction.

---

## 🙏 Acknowledgments

Thanks to all contributors and reviewers who help keep these lists accurate, relevant, and valuable to the community.
