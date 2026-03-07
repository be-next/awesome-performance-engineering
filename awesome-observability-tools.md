# Awesome Observability Tools [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated, opinionated list of tools and resources dedicated to **Observability** as an engineering capability — not just monitoring.

Observability is the ability to understand the internal state of a system by examining its outputs — **metrics, logs, traces, and profiles** — in order to explain *why* a system behaves the way it does, including in ways you didn't anticipate.

This list focuses on **modern observability practices** while acknowledging **legacy and operations-oriented tools** when they meaningfully contribute to system understanding — because most real-world environments are hybrid.

---

## Scope & Intent

This list is curated with the following principles:

* Observability as an **engineering capability**, not a product to buy
* Preference for **field-proven tools** over purely theoretical or early-stage solutions
* Explicit consideration of **system complexity, scale, cost, and operational constraints**
* Recognition that **OpenTelemetry is converging as the standard instrumentation layer** — but the ecosystem remains diverse
* Awareness that **AI is reshaping observability** — from anomaly detection to natural-language querying

The goal is to help practitioners:

* Choose tools adapted to their **context, scale, and maturity**
* Combine tools coherently rather than stack them blindly
* Build observability systems that actually support **debugging, diagnosis, and decision-making**

---

## How to Read This List

Tools are organized by **technical building blocks**, but observability problems are usually expressed in terms of **intent**. A complementary reading by intent is recommended:

### Observability by Intent

| Intent | Building blocks | Key tools |
| ------ | --------------- | --------- |
| **Golden Signals / RED / USE** | Metrics, dashboards, alerting | Prometheus, Grafana, VictoriaMetrics, Alertmanager |
| **Latency propagation & dependency analysis** | Distributed tracing | OpenTelemetry, Jaeger, Tempo, Zipkin |
| **High-cardinality debugging & unknown-unknowns** | Event-based observability, rich context | OpenTelemetry, tracing backends, structured logging |
| **Low-overhead production profiling** | Continuous profiling, eBPF | Parca, Pyroscope, async-profiler, bpftrace |
| **Black-box & legacy systems** | Metrics scraping, log-based analysis | StatsD, Graphite, Zabbix, Checkmk |
| **Cost-efficient observability at scale** | Telemetry pipelines, sampling | OTel Collector, Vector, Fluent Bit |

---

## Legend

| Symbol | Meaning |
| ------ | ------- |
| ⭐ | Widely adopted / reference solution |
| 🟢 | Actively maintained |
| 🔵 | Cloud-native / Kubernetes-friendly |
| 🟠 | Commercial / paid offering |
| 📚 | Extensive documentation |
| 🚀 | High performance / low overhead |
| 🧠 | Observability-first philosophy |
| 🧰 | Operations heritage / legacy-friendly |

---

## Metrics Collection & Time-Series Storage

*Scrapers, collectors, and time-series databases — the foundation of quantitative observability.*

* **[Prometheus](https://prometheus.io/)** ⭐🟢🔵📚🧠 — The de facto standard for cloud-native metrics. Pull-based model, dimensional data model, and PromQL. Excels at service-level monitoring; limited by single-node storage for very large deployments. [Go] [Apache-2.0] — [GitHub](https://github.com/prometheus/prometheus)
* **[VictoriaMetrics](https://victoriametrics.com/)** ⭐🟢🚀🧠 — High-performance, cost-efficient Prometheus-compatible TSDB. Handles significantly higher cardinality and longer retention than vanilla Prometheus. Excellent choice when Prometheus query compatibility matters but scale exceeds single-node limits. [Go] [Apache-2.0] — [GitHub](https://github.com/VictoriaMetrics/VictoriaMetrics)
* **[Thanos](https://thanos.io/)** ⭐🟢🔵 — Adds long-term storage, global query view, and high availability to Prometheus. Sidecar architecture lets you keep existing Prometheus deployments while adding horizontal scale. [Go] [Apache-2.0] — [GitHub](https://github.com/thanos-io/thanos)
* **[Mimir](https://grafana.com/oss/mimir/)** ⭐🟢🔵🚀 — Grafana's horizontally scalable, highly available Prometheus-compatible TSDB. Designed from the ground up for multi-tenant, large-scale deployments. [Go] [AGPL-3.0] — [GitHub](https://github.com/grafana/mimir)
* **[InfluxDB](https://www.influxdata.com/)** 🟢🟠 — Purpose-built time-series database with high write throughput. Strong ecosystem. v3 re-open-sourced under Apache 2.0 in 2024 with a Rust-based engine. [Go/Rust] [Apache-2.0/Commercial] — [GitHub](https://github.com/influxdata/influxdb)
* **[OpenTelemetry Collector](https://opentelemetry.io/docs/collector/)** — *(See [Observability Pipelines](#observability-pipelines--telemetry-processing) for full entry)*
* **[Grafana Alloy](https://grafana.com/oss/alloy-opentelemetry-collector/)** ⭐🟢🔵🧠 — OpenTelemetry-native telemetry collector from Grafana Labs (successor to Grafana Agent). Supports metrics, logs, traces, and profiles. Native integration with the Grafana stack. [Go] [Apache-2.0] — [GitHub](https://github.com/grafana/alloy)
* **[Telegraf](https://www.influxdata.com/time-series-platform/telegraf/)** 🟢 — Plugin-driven agent for collecting and reporting metrics. 300+ input plugins make it versatile for heterogeneous environments. [Go] [MIT] — [GitHub](https://github.com/influxdata/telegraf)
* **[StatsD](https://github.com/statsd/statsd)** 🧰 — Lightweight, UDP-based metrics aggregation daemon. Simple protocol, widely supported by applications. Still relevant in legacy environments. [Node.js] [MIT]
* **[Netdata](https://www.netdata.cloud/)** ⭐🟢🚀 — Real-time, per-second system and application monitoring with built-in anomaly detection. Zero-configuration agent with impressive out-of-the-box dashboards. [C] [GPL-3.0] — [GitHub](https://github.com/netdata/netdata)

---

## Distributed Tracing

*Request-level visibility across service boundaries — essential for understanding latency, dependencies, and failure propagation in distributed systems.*

* **[OpenTelemetry](https://opentelemetry.io/)** ⭐🟢🔵📚🧠 — The converging open standard for distributed tracing, metrics, and logs instrumentation. Language-specific SDKs, auto-instrumentation agents, and the Collector form a complete pipeline. If you're starting today, start here. [Multiple] [Apache-2.0] — [GitHub](https://github.com/open-telemetry)
* **[Jaeger](https://www.jaegertracing.io/)** ⭐🟢🔵📚 — CNCF graduated distributed tracing backend and UI. Mature, well-documented, strong Kubernetes integration. Originally from Uber. [Go] [Apache-2.0] — [GitHub](https://github.com/jaegertracing/jaeger)
* **[Grafana Tempo](https://grafana.com/oss/tempo/)** ⭐🟢🔵 — High-scale, cost-efficient tracing backend that requires only object storage (no indexing infrastructure). Pairs naturally with Grafana, Loki, and Mimir. [Go] [AGPL-3.0] — [GitHub](https://github.com/grafana/tempo)
* **[Zipkin](https://zipkin.io/)** 🟢📚 — One of the pioneering distributed tracing systems (Twitter, 2012). Still actively maintained with a loyal community. Simpler architecture than Jaeger, good for smaller deployments. [Java] [Apache-2.0] — [GitHub](https://github.com/openzipkin/zipkin)
* **[Apache SkyWalking](https://skywalking.apache.org/)** ⭐🟢🔵 — Full observability platform with strong tracing capabilities. Popular in the Java/JVM ecosystem. Auto-instrumentation via bytecode injection. [Java] [Apache-2.0] — [GitHub](https://github.com/apache/skywalking)
* **[SigNoz](https://signoz.io/)** 🟢🔵🧠 — Open-source observability platform built natively on OpenTelemetry. Unified metrics, traces, and logs in a single UI. ClickHouse-backed storage. Strong alternative to commercial APM. [Go/TypeScript] [ELv2/MIT] — [GitHub](https://github.com/SigNoz/signoz)
* **[Pinpoint](https://pinpoint-apm.gitbook.io/pinpoint)** 🧰 — Bytecode-instrumentation-based APM and tracing for Java and PHP. Zero-code-change approach. Popular in Korean and Asian enterprise environments. [Java] [Apache-2.0] — [GitHub](https://github.com/pinpoint-apm/pinpoint)

---

## Log Management & Log Pipelines

*Collection, processing, indexing, and analysis of log data — still the most universal telemetry signal.*

* **[Grafana Loki](https://grafana.com/oss/loki/)** ⭐🟢🔵📚🧠 — Label-based log aggregation that indexes metadata, not content. Dramatically cheaper than full-text indexing at scale. Pairs with Grafana for exploration. [Go] [AGPL-3.0] — [GitHub](https://github.com/grafana/loki)
* **[Fluent Bit](https://fluentbit.io/)** ⭐🟢🔵🚀 — Lightweight, high-performance log processor and forwarder designed for edge and containerized environments. Tiny memory footprint. [C] [Apache-2.0] — [GitHub](https://github.com/fluent/fluent-bit)
* **[Fluentd](https://www.fluentd.org/)** 🟢🔵 — CNCF graduated unified logging layer with 1000+ plugins. Heavier than Fluent Bit but more flexible for complex routing. [Ruby/C] [Apache-2.0] — [GitHub](https://github.com/fluent/fluentd)
* **[Vector](https://vector.dev/)** — *(See [Observability Pipelines](#observability-pipelines--telemetry-processing) for full entry)*
* **[Elasticsearch](https://www.elastic.co/elasticsearch)** ⭐🟢🟠🧰 — Distributed search and analytics engine. Powerful full-text search, but storage costs and operational complexity can be significant at scale. License changed from Apache-2.0 to SSPL. [Java] [SSPL/Commercial] — [GitHub](https://github.com/elastic/elasticsearch)
* **[OpenSearch](https://opensearch.org/)** 🟢🔵 — Community-driven fork of Elasticsearch (post-license change). AWS-backed, Apache-2.0 licensed. Drop-in replacement for Elasticsearch in most deployments. [Java] [Apache-2.0] — [GitHub](https://github.com/opensearch-project/OpenSearch)
* **[Logstash](https://www.elastic.co/logstash)** 🧰 — Flexible log ingestion and transformation pipeline. Part of the Elastic Stack. Heavy JVM footprint. [Java] [SSPL/Commercial] — [GitHub](https://github.com/elastic/logstash)
* **[Graylog](https://graylog.org/)** 🟢🟠🧰 — Centralized log management with built-in alerting and dashboards. Good for teams that want a self-contained log platform. [Java] [SSPL/Commercial] — [GitHub](https://github.com/Graylog2/graylog2-server)
* **[rsyslog](https://www.rsyslog.com/)** 🟢🚀🧰 — High-performance system logging daemon. Handles millions of messages per second. Essential in Linux infrastructure. [C] [GPL-3.0] — [GitHub](https://github.com/rsyslog/rsyslog)

---

## Observability Pipelines & Telemetry Processing

*Transport, transformation, sampling, and routing of observability data — increasingly critical as telemetry volumes grow and costs need control.*

* **[OpenTelemetry Collector](https://opentelemetry.io/docs/collector/)** ⭐🟢🔵🧠 — The standard telemetry processing pipeline. Receivers, processors, and exporters for any signal to any backend. Supports tail-based sampling, attribute enrichment, and routing. [Go] [Apache-2.0] — [GitHub](https://github.com/open-telemetry/opentelemetry-collector)
* **[Vector](https://vector.dev/)** 🟢🚀🧠 — End-to-end observability data routing and transformation. Programmable transforms (VRL language), strong at log-to-metric conversion and pipeline consolidation. [Rust] [MPL-2.0] — [GitHub](https://github.com/vectordotdev/vector)
* **[Fluent Bit](https://fluentbit.io/) / [Fluentd](https://www.fluentd.org/)** 🟢 — Log and telemetry forwarding pipelines with extensive plugin ecosystems. [Apache-2.0]
* **[Logstash](https://www.elastic.co/logstash)** 🧰 — ETL-style processing for observability data. Powerful filter plugins but resource-intensive. [Java]
* **[Cribl Stream](https://cribl.io/)** 🟠🚀 — Commercial observability pipeline for routing, reducing, and enriching telemetry data before it reaches backends. Strong ROI story for organizations with high telemetry costs. [Commercial]

---

## Visualization & Dashboards

*Exploration, visualization, and correlation of observability data — where signals become understanding.*

* **[Grafana](https://grafana.com/oss/grafana/)** ⭐🟢📚🧠 — The de facto standard for observability dashboards. Supports 100+ data sources, alerting, annotations, and increasingly sophisticated exploration features. The center of gravity for open-source observability UIs. [TypeScript/Go] [AGPL-3.0] — [GitHub](https://github.com/grafana/grafana)
* **[Kibana](https://www.elastic.co/kibana)** 🟢🟠🧰 — Visualization and exploration for Elasticsearch/OpenSearch data. Powerful for log exploration (Discover, Lens). Part of the Elastic Stack. [TypeScript] [SSPL/Commercial] — [GitHub](https://github.com/elastic/kibana)
* **[OpenSearch Dashboards](https://opensearch.org/)** 🟢🔵 — Open-source fork of Kibana for OpenSearch. [TypeScript] [Apache-2.0] — [GitHub](https://github.com/opensearch-project/OpenSearch-Dashboards)
* **[Apache Superset](https://superset.apache.org/)** 🟢 — Scalable analytics and dashboarding platform. SQL-first, strong at ad-hoc data exploration. [Python] [Apache-2.0] — [GitHub](https://github.com/apache/superset)
* **[Perses](https://perses.dev/)** 🟢🔵🧠 — CNCF sandbox project for dashboards-as-code. Native PromQL and TraceQL support. Designed for GitOps-driven observability. [Go/TypeScript] [Apache-2.0] — [GitHub](https://github.com/perses/perses)

---

## Profiling & Continuous Performance Analysis

*Always-on, low-overhead profiling in production — the emerging "fourth pillar" of observability alongside metrics, logs, and traces.*

* **[Parca](https://www.parca.dev/)** ⭐🟢🔵🧠 — eBPF-based continuous profiling platform. Zero-instrumentation, always-on profiling with differential flame graphs. CNCF sandbox project. [Go] [Apache-2.0] — [GitHub](https://github.com/parca-dev/parca)
* **[Grafana Pyroscope](https://grafana.com/oss/pyroscope/)** ⭐🟢🔵🧠 — Continuous profiling with flame graph visualization. Supports multiple languages. Integrates naturally with the Grafana stack. [Go] [AGPL-3.0] — [GitHub](https://github.com/grafana/pyroscope)
* **[async-profiler](https://github.com/async-profiler/async-profiler)** 🟢🚀 — Low-overhead sampling profiler for JVM. Captures CPU, allocation, lock contention, and wall-clock profiles. The reference tool for Java performance analysis. [Java/C++] [Apache-2.0]
* **[perf](https://perfwiki.github.io/)** 🧰🚀 — Linux kernel performance analysis tool. Hardware counters, tracepoints, and sampling. Foundational for system-level performance work. [C] [GPL-2.0]
* **[bpftrace](https://bpftrace.org/)** 🟢🚀🧠 — High-level tracing language for Linux eBPF. One-liners and scripts for dynamic kernel and user-space tracing. Invaluable for ad-hoc production investigation. [C++] [Apache-2.0] — [GitHub](https://github.com/bpftrace/bpftrace)
* **[bcc (BPF Compiler Collection)](https://github.com/iovisor/bcc)** 🟢🚀 — Toolkit for creating eBPF-based tracing and networking programs. Includes dozens of ready-to-use tools (execsnoop, biolatency, tcplife, etc.). [C/Python] [Apache-2.0]
* **[Grafana Beyla](https://grafana.com/oss/beyla-ebpf/)** 🟢🔵🧠🚀 — eBPF-based auto-instrumentation for HTTP and gRPC services. Zero-code, zero-configuration application observability. Generates RED metrics and distributed traces without SDK integration. [Go] [Apache-2.0] — [GitHub](https://github.com/grafana/beyla)
* **[Perfetto](https://perfetto.dev/)** 🟢 — System-wide tracing and profiling toolkit from Google. Designed for Android and Chrome but increasingly used for general system analysis. [C++] [Apache-2.0] — [GitHub](https://github.com/google/perfetto)

---

## Alerting & Incident Response

*Alert management, on-call workflows, and incident coordination — the operational bridge between observability and action.*

* **[Alertmanager](https://prometheus.io/docs/alerting/latest/alertmanager/)** ⭐🟢📚 — Prometheus-native alert handling with grouping, silencing, inhibition, and routing. [Go] [Apache-2.0] — [GitHub](https://github.com/prometheus/alertmanager)
* **[Grafana OnCall](https://grafana.com/oss/oncall/)** 🟢🔵 — Open-source on-call management and alert routing. Integrates natively with Grafana alerting. [Python] [AGPL-3.0] — [GitHub](https://github.com/grafana/oncall)
* **[Keep](https://www.keephq.dev/)** 🟢🔵🧠 — Open-source alert management platform. Consolidates alerts from multiple sources with workflow automation. [Python] [MIT] — [GitHub](https://github.com/keephq/keep)
* **[Alerta](https://alerta.io/)** 🟢 — Unified alert correlation and management. Consolidates alerts from multiple monitoring systems. [Python] [Apache-2.0] — [GitHub](https://github.com/alerta/alerta)
* **[PagerDuty](https://www.pagerduty.com/)** 🟠 — Industry-standard incident response and on-call management platform. [Commercial]
* **[Opsgenie](https://www.atlassian.com/software/opsgenie)** 🟠 — Alerting and escalation platform. Part of Atlassian suite. [Commercial]
* **[Rootly](https://rootly.com/)** 🟠🧠 — AI-assisted incident management with automated timelines and postmortem generation. [Commercial]

---

## Observability Platforms (Integrated)

*Full-stack platforms that combine metrics, logs, traces, and often profiling — trading flexibility for integration and convenience.*

* **[Datadog](https://www.datadoghq.com/)** 🟠🧠 — SaaS observability platform with AI-powered features (Watchdog anomaly detection, automated root-cause analysis). Strong breadth, premium pricing. [Commercial]
* **[Dynatrace](https://www.dynatrace.com/)** 🟠🧠 — AI-driven observability with automatic topology discovery and root-cause analysis (Davis AI). Strong in enterprise and complex Java environments. [Commercial]
* **[New Relic](https://newrelic.com/)** 🟠🧠 — Developer-centric observability with a generous free tier. NRQL query language, strong APM heritage. [Commercial]
* **[Splunk Observability](https://www.splunk.com/en_us/products/observability.html)** 🟠🧰 — Observability built on Splunk's machine data analytics platform. Strong for organizations already invested in Splunk. [Commercial]
* **[Elastic Observability](https://www.elastic.co/observability)** 🟠🧰 — Observability solution built on the Elastic Stack (Elasticsearch, Kibana, APM). Self-managed and cloud options. [Commercial]
* **[Honeycomb](https://www.honeycomb.io/)** 🟠🧠 — Observability platform built around high-cardinality, high-dimensionality event data. Pioneers of the "observability vs. monitoring" distinction. BubbleUp feature for automated correlation. [Commercial]
* **[Grafana Cloud](https://grafana.com/products/cloud/)** 🟠🧠 — Managed Grafana stack (Mimir, Loki, Tempo, Pyroscope) with a generous free tier. Best of open-source with SaaS convenience. [Commercial]
* **[Instana (IBM)](https://www.ibm.com/products/instana)** 🟠🧠 — Automatic infrastructure and application discovery with real-time observability. Strong in containerized and microservice environments. [Commercial]
* **[AppDynamics (Splunk/Cisco)](https://www.splunk.com/en_us/products/splunk-appdynamics.html)** 🟠🧰 — Enterprise APM with business transaction monitoring and code-level diagnostics. Merged into Splunk in 2025. [Commercial]
* **[Chronosphere](https://chronosphere.io/)** 🟠🧠 — Cloud-native observability platform focused on metrics at scale. Founded by Uber M3 creators. Strong cost control and cardinality management. [Commercial]
* **[Lightstep / ServiceNow Cloud Observability](https://www.servicenow.com/products/observability.html)** 🟠🧠 — OpenTelemetry-native observability platform, now part of ServiceNow. [Commercial]
* **[Sematext](https://www.sematext.com/)** 🟢🟠🧠📚 — SaaS observability platform with OpenTelemetry-native support and automatic topology discovery. [Commercial]

---

## Monitoring Suites (Operations-Oriented)

*Infrastructure-first and legacy monitoring systems — still widely deployed and relevant in hybrid environments.*

* **[Zabbix](https://www.zabbix.com/)** 🟢🧰 — Enterprise-grade monitoring platform with agent-based and agentless monitoring. Mature, highly configurable, strong in traditional infrastructure. [C] [GPL-2.0] — [GitHub](https://github.com/zabbix/zabbix)
* **[Nagios](https://www.nagios.org/)** 🟢🧰 — The grandfather of open-source monitoring. Check-based architecture. Enormous plugin ecosystem but showing its age. [C] [GPL-2.0] — [GitHub](https://github.com/NagiosEnterprises/nagioscore)
* **[Icinga](https://icinga.com/)** 🟢🧰 — Modern evolution of Nagios with better APIs, configuration management, and scalability. [C++] [GPL-2.0] — [GitHub](https://github.com/Icinga/icinga2)
* **[Checkmk](https://checkmk.com/)** 🟢🟠🧰 — Infrastructure and application monitoring with auto-discovery. Scales well for large enterprise environments. [Python/C++] [GPL-2.0/Commercial] — [GitHub](https://github.com/Checkmk/checkmk)

---

## Service Mesh Observability

*Observability primitives integrated into service mesh infrastructure — L7 visibility without application-level instrumentation.*

* **[Kiali](https://kiali.io/)** 🟢🔵 — Observability console for Istio service mesh. Topology visualization, traffic flow, and health analysis. [Go] [Apache-2.0] — [GitHub](https://github.com/kiali/kiali)
* **[Linkerd Viz](https://linkerd.io/2/reference/cli/viz/)** 🟢🔵 — Built-in telemetry and dashboard for Linkerd service mesh. Lightweight, opinionated. [Go] [Apache-2.0] — [GitHub](https://github.com/linkerd/linkerd2)
* **[Hubble](https://docs.cilium.io/en/stable/observability/hubble/)** 🟢🔵🚀 — eBPF-powered network observability for Cilium. L3/L4/L7 flow visibility, DNS monitoring, and service dependency mapping — all without sidecars. [Go] [Apache-2.0] — [GitHub](https://github.com/cilium/hubble)

---

## Database Observability

*Query-level performance visibility for databases — often the critical path in application performance.*

* **[PMM (Percona Monitoring and Management)](https://www.percona.com/software/database-tools/percona-monitoring-and-management)** 🟢 — Open-source database performance monitoring for MySQL, PostgreSQL, and MongoDB. Query analytics, slow query analysis. [Go] [AGPL-3.0] — [GitHub](https://github.com/percona/pmm)
* **[pgwatch](https://github.com/cybertec-postgresql/pgwatch)** 🟢 — PostgreSQL-specific monitoring and metrics collection. [Go] [BSD-3-Clause]
* **[pg_stat_monitor](https://github.com/percona/pg_stat_monitor)** 🟢 — PostgreSQL extension for enhanced query performance monitoring. More granular than pg_stat_statements. [C] [Apache-2.0]
* **[VividCortex / SolarWinds DPM](https://www.solarwinds.com/solarwinds-observability/use-cases/system-performance)** 🟠 — SaaS query-level database performance monitoring. [Commercial]
* **[Datadog DBM](https://www.datadoghq.com/product/database-monitoring/)** 🟠🧠 — Database monitoring with query-level explain plans, wait event analysis, and trace correlation. [Commercial]

---

## Real User Monitoring (RUM) & Frontend Observability

*Understanding performance as experienced by actual users — where infrastructure metrics end and user experience begins.*

* **[Sentry](https://sentry.io/)** 🟢🧠 — Error tracking and performance monitoring for frontend and backend. Session replay, Web Vitals, and release health tracking. [Python] [BSL/Commercial] — [GitHub](https://github.com/getsentry/sentry)
* **[Grafana Faro](https://grafana.com/oss/faro/)** 🟢🔵🧠 — Open-source frontend observability SDK. Captures errors, performance, and user events, sends to Grafana stack. [TypeScript] [Apache-2.0] — [GitHub](https://github.com/grafana/faro-web-sdk)
* **[OpenTelemetry Browser SDK](https://opentelemetry.io/docs/languages/js/getting-started/browser/)** 🟢🧠 — OTel instrumentation for web applications. Captures page loads, resource timings, and user interactions. [TypeScript] [Apache-2.0]
* **[LogRocket](https://logrocket.com/)** 🟠 — Session replay combined with frontend performance monitoring. [Commercial]

---

## AI-Augmented Observability

*Tools and capabilities that apply machine learning and AI to observability data — reducing noise, accelerating diagnosis, and enabling predictive operations.*

This is an emerging and fast-moving space. The tools below represent current capabilities, not a stable category.

* **[Dynatrace Davis AI](https://www.dynatrace.com/platform/artificial-intelligence/)** 🟠🧠 — Deterministic and causal AI for automatic root-cause analysis. Topology-aware, goes beyond statistical correlation. [Commercial]
* **[Datadog Watchdog](https://docs.datadoghq.com/watchdog/)** 🟠🧠 — ML-driven anomaly detection across metrics, logs, and APM data. Automatic story generation for correlated anomalies. [Commercial]
* **[Moogsoft](https://www.moogsoft.com/)** 🟠🧠 — AIOps platform for alert correlation, noise reduction, and incident clustering. [Commercial]
* **[New Relic AI](https://newrelic.com/platform/applied-intelligence)** 🟠🧠 — Applied intelligence with anomaly detection, incident correlation, and natural-language querying (NRAI). [Commercial]
* **[Honeycomb BubbleUp](https://www.honeycomb.io/platform/bubbleup)** 🟠🧠 — Automated outlier correlation across high-cardinality dimensions. Helps identify "what's different" about slow requests without manual hypotheses. [Commercial]
* **[Coroot](https://coroot.com/)** 🟢🔵🧠 — Open-source eBPF-powered observability with automated service map discovery and anomaly detection. [Go] [Apache-2.0] — [GitHub](https://github.com/coroot/coroot)

---

## SLO Management

*Defining, tracking, and alerting on Service Level Objectives — the bridge between observability data and reliability commitments.*

* **[Sloth](https://sloth.dev/)** 🟢🔵🧠 — SLO generation for Prometheus. Define SLOs in YAML, generates multi-window multi-burn-rate alerts automatically. [Go] [Apache-2.0] — [GitHub](https://github.com/slok/sloth)
* **[Pyrra](https://github.com/pyrra-dev/pyrra)** 🟢🔵🧠 — SLO management and alerting with a web UI. Kubernetes-native, generates Prometheus recording rules and alerts from SLO definitions. [Go] [Apache-2.0]
* **[OpenSLO](https://openslo.com/)** 🟢🧠 — Open specification for defining SLOs as code. Vendor-neutral, enables GitOps-driven SLO management. [YAML] [Apache-2.0] — [GitHub](https://github.com/OpenSLO/OpenSLO)
* **[Nobl9](https://www.nobl9.com/)** 🟠🧠 — Enterprise SLO platform connecting multiple data sources to unified SLO tracking and error budget management. [Commercial]

---

## Synthetic Monitoring

*Proactive monitoring from the outside — validating availability, performance, and correctness before users are affected.*

* **[Checkly](https://www.checklyhq.com/)** 🟢🔵🔗🧠 — Monitoring as code for APIs and browsers. Playwright-based synthetic checks with CI/CD integration. [TypeScript] [Free tier/Commercial] — [GitHub](https://github.com/checkly/checkly-cli)
* **[Grafana Synthetic Monitoring](https://grafana.com/docs/grafana-cloud/testing/synthetic-monitoring/)** 🟢🔵 — Probe-based synthetic monitoring integrated into Grafana Cloud. Multi-location HTTP, DNS, TCP, and ICMP checks. [Commercial]
* **[Uptime Kuma](https://uptime.kuma.pet/)** ⭐🟢🧪 — Self-hosted monitoring tool with a clean UI. HTTP, TCP, DNS, and keyword monitoring with notifications. Simple and effective. [JavaScript] [MIT] — [GitHub](https://github.com/louislam/uptime-kuma)
* **[Sematext](https://www.sematext.com/synthetic-monitoring)** 🟢🟠🧠📚 — Playwright-based synthetic checks with CI/CD integration, GitHub synchronization, SSL certificate expiration monitoring. [TypeScript] [Commercial]

---

## Legacy & Historical

*Tools with historical significance that are no longer actively evolving but remain widely deployed. Included for context — practitioners may encounter them in existing environments.*

* **[Graphite](https://graphiteapp.org/)** 🧰 — One of the original time-series storage and graphing systems. Whisper backend, Carbon collector. Historical significance but limited compared to modern alternatives. [Python] [Apache-2.0] — [GitHub](https://github.com/graphite-project/graphite-web)
* **[Nagios](https://www.nagios.org/)** 🧰 — The grandfather of open-source monitoring. Check-based architecture with an enormous plugin ecosystem. Still widely deployed in enterprise environments. *(Also listed in [Monitoring Suites](#monitoring-suites-operations-oriented))* [C] [GPL-2.0] — [GitHub](https://github.com/NagiosEnterprises/nagioscore)
* **[Redash](https://redash.io/)** 🧰 — SQL-first data visualization and collaboration. Connects to many data sources. Minimal maintenance since Databricks acquisition. [Python] [BSD-2-Clause] — [GitHub](https://github.com/getredash/redash)

---

## Learning Resources

### Books

* *Observability Engineering* — Charity Majors, Liz Fong-Jones, George Miranda (O'Reilly, 2022)
* *Distributed Systems Observability* — Cindy Sridharan (O'Reilly, 2018) — [Free online](https://www.oreilly.com/library/view/distributed-systems-observability/9781492033431/)
* *Cloud Native Observability with OpenTelemetry* — Alex Boten (Packt, 2022)
* *Site Reliability Engineering* — Betsy Beyer et al. (O'Reilly / Google, 2016) — [Free online](https://sre.google/sre-book/table-of-contents/)
* *BPF Performance Tools* — Brendan Gregg (Addison-Wesley, 2019) — The definitive reference for eBPF-based performance analysis
* *Systems Performance* — Brendan Gregg (Addison-Wesley, 2nd ed. 2020) — Essential reading for anyone serious about performance engineering
* *Practical Monitoring* — Mike Julian (O'Reilly, 2017) — Vendor-neutral monitoring principles, anti-patterns, and on-call design
* *Understanding Software Dynamics* — Richard L. Sites (Addison-Wesley, 2021) — Modern performance profiling with KUtrace, by the DEC Alpha co-architect
* *Designing Data-Intensive Applications* — Martin Kleppmann (O'Reilly, 2017) — Essential architecture reference for distributed systems and data pipelines
* *Database Reliability Engineering* — Laine Campbell, Charity Majors (O'Reilly, 2017) — SRE principles applied to database operations and performance

### Talks & Video Resources

* [Brendan Gregg — Blazing Performance with Flame Graphs](https://www.brendangregg.com/) — The original flame graph introduction (USENIX LISA 2013)
* [Brendan Gregg — Give Me 15 Minutes and I'll Change Your View of Linux Tracing](https://www.brendangregg.com/) — Concise Linux tracing primer (USENIX LISA 2016)
* [Bryan Cantrill — The Hurricane's Butterfly](https://www.youtube.com/watch?v=7AO4wz6gI3Q) — Debugging pathologically performing systems (Jane Street 2018)
* [Emery Berger — Performance Matters](https://www.youtube.com/watch?v=r-TLSBdHe1A) — Causal profiling and the Coz profiler (Strange Loop 2019)
* [Martin Thompson — Mechanical Sympathy](https://www.infoq.com/presentations/mechanical-sympathy/) — Understanding hardware for high-performance software

### Online Resources & Blogs

* [OpenTelemetry Documentation](https://opentelemetry.io/docs/) — The primary reference for modern instrumentation
* [Brendan Gregg's Blog](https://www.brendangregg.com/) — Deep technical content on systems performance, eBPF, and flame graphs
* [CNCF Observability Technical Advisory Group](https://github.com/cncf/tag-observability) — Community standards and whitepapers
* [Honeycomb Blog](https://www.honeycomb.io/blog) — Thought leadership on observability engineering
* [Grafana Blog](https://grafana.com/blog/) — Technical content on the Grafana observability stack
* [SRE Weekly](https://sreweekly.com/) — Weekly newsletter on reliability and observability
* [Netflix TechBlog](https://netflixtechblog.com/) — Chaos engineering, adaptive streaming, and performance at massive scale
* [Mechanical Sympathy Blog](http://mechanical-sympathy.blogspot.com) — Martin Thompson on low-latency, lock-free systems
* [The Observation Deck](https://bcantrill.dtrace.org/) — Bryan Cantrill on DTrace, observability, and system debugging

---

## Contributing

Contributions are welcome. Please read **[CONTRIBUTING.md](CONTRIBUTING.md)** before submitting changes.

## License

Released under **CC0 1.0 Universal**.
