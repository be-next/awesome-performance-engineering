# Awesome Performance Engineering [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

<p align="center">
  <a href="https://github.com/be-next/awesome-performance-engineering">
    <img src="media/logo.svg" alt="Awesome Performance Engineering" width="400">
  </a>
</p>

> The discipline that ensures systems deliver fast, reliable, and cost-efficient experiences at any scale, combining observability and performance testing.

## Contents

- [Legend](#legend)
- [Observability](#observability)
  - [Metrics Collection & Time-Series Storage](#metrics-collection--time-series-storage)
  - [Distributed Tracing](#distributed-tracing)
  - [Log Management & Log Pipelines](#log-management--log-pipelines)
  - [Observability Pipelines and Telemetry Processing](#observability-pipelines-and-telemetry-processing)
  - [Visualization & Dashboards](#visualization--dashboards)
  - [Profiling & Continuous Performance Analysis](#profiling--continuous-performance-analysis)
  - [Alerting & Incident Response](#alerting--incident-response)
  - [Observability Platforms (Integrated)](#observability-platforms-integrated)
  - [Monitoring Suites (Operations-Oriented)](#monitoring-suites-operations-oriented)
  - [Service Mesh Observability](#service-mesh-observability)
  - [Database Observability](#database-observability)
  - [Real User Monitoring (RUM) & Frontend Observability](#real-user-monitoring-rum--frontend-observability)
  - [AI-Augmented Observability](#ai-augmented-observability)
  - [SLO Management](#slo-management)
  - [Synthetic Monitoring](#synthetic-monitoring)
  - [Legacy & Historical](#legacy--historical)
- [Performance Testing](#performance-testing)
  - [Load & Stress Testing](#load--stress-testing)
  - [HTTP Benchmarking & Micro-Benchmarking](#http-benchmarking--micro-benchmarking)
  - [API Testing & Contract Testing](#api-testing--contract-testing)
  - [gRPC & Protocol-Specific Testing](#grpc--protocol-specific-testing)
  - [Browser & Frontend Performance](#browser--frontend-performance)
  - [Service Virtualization and Mocking](#service-virtualization-and-mocking)
  - [Synthetic Data Generation](#synthetic-data-generation)
  - [Database Performance Testing & Benchmarking](#database-performance-testing--benchmarking)
  - [System & Infrastructure Benchmarking](#system--infrastructure-benchmarking)
  - [Chaos Engineering & Fault Injection](#chaos-engineering--fault-injection)
  - [Network Simulation & Traffic Shaping](#network-simulation--traffic-shaping)
  - [CI/CD Integration & Performance Gates](#cicd-integration--performance-gates)
  - [Results Analysis & Reporting](#results-analysis--reporting)
  - [Cloud Provider Services](#cloud-provider-services)
  - [Developer-Centric Platforms](#developer-centric-platforms)
  - [Enterprise Platforms](#enterprise-platforms)
  - [Tools & Integrations](#tools--integrations)
- [Related](#related)

## Legend

- ⭐ Widely adopted / reference solution
- 🟢 Actively maintained
- 🔵 Cloud-native / Kubernetes-friendly
- 🟠 Commercial / paid offering
- 🚀 High performance / low overhead

## Observability

### Metrics Collection & Time-Series Storage

- [Prometheus](https://github.com/prometheus/prometheus) - The de facto standard for cloud-native metrics. Pull-based model, dimensional data model, and PromQL. Excels at service-level monitoring; limited by single-node storage for very large deployments. ⭐🟢🔵
- [VictoriaMetrics](https://github.com/VictoriaMetrics/VictoriaMetrics) - High-performance, cost-efficient Prometheus-compatible TSDB. Handles significantly higher cardinality and longer retention than vanilla Prometheus. Excellent choice when Prometheus query compatibility matters but scale exceeds single-node limits. ⭐🟢🚀
- [Thanos](https://github.com/thanos-io/thanos) - Adds long-term storage, global query view, and high availability to Prometheus. Sidecar architecture lets you keep existing Prometheus deployments while adding horizontal scale. ⭐🟢🔵
- [Mimir](https://github.com/grafana/mimir) - Grafana's horizontally scalable, highly available Prometheus-compatible TSDB. Designed from the ground up for multi-tenant, large-scale deployments. ⭐🟢🔵🚀
- [InfluxDB](https://github.com/influxdata/influxdb) - Purpose-built time-series database with high write throughput. Strong ecosystem. v3 re-open-sourced under Apache 2.0 in 2024 with a Rust-based engine. 🟢🟠
- [Grafana Alloy](https://github.com/grafana/alloy) - OpenTelemetry-native telemetry collector from Grafana Labs (successor to Grafana Agent). Supports metrics, logs, traces, and profiles. Native integration with the Grafana stack. ⭐🟢🔵
- [Telegraf](https://github.com/influxdata/telegraf) - Plugin-driven agent for collecting and reporting metrics. 300+ input plugins make it versatile for heterogeneous environments. 🟢
- [StatsD](https://github.com/statsd/statsd) - Lightweight, UDP-based metrics aggregation daemon. Simple protocol, widely supported by applications. Still relevant in legacy environments.
- [Netdata](https://github.com/netdata/netdata) - Real-time, per-second system and application monitoring with built-in anomaly detection. Zero-configuration agent with impressive out-of-the-box dashboards. ⭐🟢🚀

### Distributed Tracing

- [OpenTelemetry](https://github.com/open-telemetry) - The converging open standard for distributed tracing, metrics, and logs instrumentation. Language-specific SDKs, auto-instrumentation agents, and the Collector form a complete pipeline. If you're starting today, start here. ⭐🟢🔵
- [Jaeger](https://github.com/jaegertracing/jaeger) - CNCF graduated distributed tracing backend and UI. Mature, well-documented, strong Kubernetes integration. Originally from Uber. ⭐🟢🔵
- [Grafana Tempo](https://github.com/grafana/tempo) - High-scale, cost-efficient tracing backend that requires only object storage (no indexing infrastructure). Pairs naturally with Grafana, Loki, and Mimir. ⭐🟢🔵
- [Zipkin](https://github.com/openzipkin/zipkin) - One of the pioneering distributed tracing systems (Twitter, 2012). Still actively maintained with a loyal community. Simpler architecture than Jaeger, good for smaller deployments. 🟢
- [Apache SkyWalking](https://github.com/apache/skywalking) - Full observability platform with strong tracing capabilities. Popular in the Java/JVM ecosystem. Auto-instrumentation via bytecode injection. ⭐🟢🔵
- [SigNoz](https://github.com/SigNoz/signoz) - Open-source observability platform built natively on OpenTelemetry. Unified metrics, traces, and logs in a single UI. ClickHouse-backed storage. Strong alternative to commercial APM. 🟢🔵
- [Pinpoint](https://github.com/pinpoint-apm/pinpoint) - Bytecode-instrumentation-based APM and tracing for Java and PHP. Zero-code-change approach. Popular in Korean and Asian enterprise environments.

### Log Management & Log Pipelines

- [Grafana Loki](https://github.com/grafana/loki) - Label-based log aggregation that indexes metadata, not content. Dramatically cheaper than full-text indexing at scale. Pairs with Grafana for exploration. ⭐🟢🔵
- [Fluent Bit](https://github.com/fluent/fluent-bit) - Lightweight, high-performance log processor and forwarder designed for edge and containerized environments. Tiny memory footprint. ⭐🟢🔵🚀
- [Fluentd](https://github.com/fluent/fluentd) - CNCF graduated unified logging layer with 1000+ plugins. Heavier than Fluent Bit but more flexible for complex routing. 🟢🔵
- [Elasticsearch](https://github.com/elastic/elasticsearch) - Distributed search and analytics engine. Powerful full-text search, but storage costs and operational complexity can be significant at scale. License changed from Apache-2.0 to SSPL. ⭐🟢🟠
- [OpenSearch](https://github.com/opensearch-project/OpenSearch) - Community-driven fork of Elasticsearch (post-license change). AWS-backed, Apache-2.0 licensed. Drop-in replacement for Elasticsearch in most deployments. 🟢🔵
- [Logstash](https://github.com/elastic/logstash) - Flexible log ingestion and transformation pipeline. Part of the Elastic Stack. Heavy JVM footprint.
- [Graylog](https://github.com/Graylog2/graylog2-server) - Centralized log management with built-in alerting and dashboards. Good for teams that want a self-contained log platform. 🟢🟠
- [rsyslog](https://github.com/rsyslog/rsyslog) - High-performance system logging daemon. Handles millions of messages per second. Essential in Linux infrastructure. 🟢🚀

### Observability Pipelines and Telemetry Processing

- [OpenTelemetry Collector](https://github.com/open-telemetry/opentelemetry-collector) - The standard telemetry processing pipeline. Receivers, processors, and exporters for any signal to any backend. Supports tail-based sampling, attribute enrichment, and routing. ⭐🟢🔵
- [Vector](https://github.com/vectordotdev/vector) - End-to-end observability data routing and transformation. Programmable transforms (VRL language), strong at log-to-metric conversion and pipeline consolidation. 🟢🚀
- [Logstash](https://www.elastic.co/logstash) - ETL-style processing for observability data. Powerful filter plugins but resource-intensive.
- [Cribl Stream](https://cribl.io/) - Commercial observability pipeline for routing, reducing, and enriching telemetry data before it reaches backends. Strong ROI story for organizations with high telemetry costs. 🟠🚀

### Visualization & Dashboards

- [Grafana](https://github.com/grafana/grafana) - The de facto standard for observability dashboards. Supports 100+ data sources, alerting, annotations, and increasingly sophisticated exploration features. The center of gravity for open-source observability UIs. ⭐🟢
- [Kibana](https://github.com/elastic/kibana) - Visualization and exploration for Elasticsearch/OpenSearch data. Powerful for log exploration (Discover, Lens). Part of the Elastic Stack. 🟢🟠
- [OpenSearch Dashboards](https://github.com/opensearch-project/OpenSearch-Dashboards) - Open-source fork of Kibana for OpenSearch. 🟢🔵
- [Apache Superset](https://github.com/apache/superset) - Scalable analytics and dashboarding platform. SQL-first, strong at ad-hoc data exploration. 🟢
- [Perses](https://github.com/perses/perses) - CNCF sandbox project for dashboards-as-code. Native PromQL and TraceQL support. Designed for GitOps-driven observability. 🟢🔵

### Profiling & Continuous Performance Analysis

- [Parca](https://github.com/parca-dev/parca) - eBPF-based continuous profiling platform. Zero-instrumentation, always-on profiling with differential flame graphs. CNCF sandbox project. ⭐🟢🔵
- [Grafana Pyroscope](https://github.com/grafana/pyroscope) - Continuous profiling with flame graph visualization. Supports multiple languages. Integrates naturally with the Grafana stack. ⭐🟢🔵
- [async-profiler](https://github.com/async-profiler/async-profiler) - Low-overhead sampling profiler for JVM. Captures CPU, allocation, lock contention, and wall-clock profiles. The reference tool for Java performance analysis. 🟢🚀
- [perf](https://perfwiki.github.io/) - Linux kernel performance analysis tool. Hardware counters, tracepoints, and sampling. Foundational for system-level performance work. 🚀
- [bpftrace](https://github.com/bpftrace/bpftrace) - High-level tracing language for Linux eBPF. One-liners and scripts for dynamic kernel and user-space tracing. Invaluable for ad-hoc production investigation. 🟢🚀
- [bcc (BPF Compiler Collection)](https://github.com/iovisor/bcc) - Toolkit for creating eBPF-based tracing and networking programs. Includes dozens of ready-to-use tools (execsnoop, biolatency, tcplife, etc.). 🟢🚀
- [Grafana Beyla](https://github.com/grafana/beyla) - eBPF-based auto-instrumentation for HTTP and gRPC services. Zero-code, zero-configuration application observability. Generates RED metrics and distributed traces without SDK integration. 🟢🔵🚀
- [Perfetto](https://github.com/google/perfetto) - System-wide tracing and profiling toolkit from Google. Designed for Android and Chrome but increasingly used for general system analysis. 🟢

### Alerting & Incident Response

- [Alertmanager](https://github.com/prometheus/alertmanager) - Prometheus-native alert handling with grouping, silencing, inhibition, and routing. ⭐🟢
- [Grafana OnCall](https://github.com/grafana/oncall) - Open-source on-call management and alert routing. Integrates natively with Grafana alerting. 🟢🔵
- [Keep](https://github.com/keephq/keep) - Open-source alert management platform. Consolidates alerts from multiple sources with workflow automation. 🟢🔵
- [Alerta](https://github.com/alerta/alerta) - Unified alert correlation and management. Consolidates alerts from multiple monitoring systems. 🟢
- [PagerDuty](https://www.pagerduty.com/) - Industry-standard incident response and on-call management platform. 🟠
- [Opsgenie](https://www.atlassian.com/software/opsgenie) - Alerting and escalation platform. Part of Atlassian suite. 🟠
- [Rootly](https://rootly.com/) - AI-assisted incident management with automated timelines and postmortem generation. 🟠

### Observability Platforms (Integrated)

- [Datadog](https://www.datadoghq.com/) - SaaS observability platform with AI-powered features (Watchdog anomaly detection, automated root-cause analysis). Strong breadth, premium pricing. 🟠
- [Dynatrace](https://www.dynatrace.com/) - AI-driven observability with automatic topology discovery and root-cause analysis (Davis AI). Strong in enterprise and complex Java environments. 🟠
- [New Relic](https://newrelic.com/) - Developer-centric observability with a generous free tier. NRQL query language, strong APM heritage. 🟠
- [Splunk Observability](https://www.splunk.com/en_us/products/observability.html) - Observability built on Splunk's machine data analytics platform. Strong for organizations already invested in Splunk. 🟠
- [Elastic Observability](https://www.elastic.co/observability) - Observability solution built on the Elastic Stack (Elasticsearch, Kibana, APM). Self-managed and cloud options. 🟠
- [Honeycomb](https://www.honeycomb.io/) - Observability platform built around high-cardinality, high-dimensionality event data. Pioneers of the "observability vs. monitoring" distinction. BubbleUp feature for automated correlation. 🟠
- [Grafana Cloud](https://grafana.com/products/cloud/) - Managed Grafana stack (Mimir, Loki, Tempo, Pyroscope) with a generous free tier. Best of open-source with SaaS convenience. 🟠
- [Instana (IBM)](https://www.ibm.com/products/instana) - Automatic infrastructure and application discovery with real-time observability. Strong in containerized and microservice environments. 🟠
- [AppDynamics (Splunk/Cisco)](https://www.splunk.com/en_us/products/splunk-appdynamics.html) - Enterprise APM with business transaction monitoring and code-level diagnostics. Merged into Splunk in 2025. 🟠
- [Chronosphere](https://chronosphere.io/) - Cloud-native observability platform focused on metrics at scale. Founded by Uber M3 creators. Strong cost control and cardinality management. 🟠
- [Lightstep / ServiceNow Cloud Observability](https://www.servicenow.com/products/observability.html) - OpenTelemetry-native observability platform, now part of ServiceNow. 🟠
- [Sematext](https://www.sematext.com/) - SaaS observability platform with OpenTelemetry-native support and automatic topology discovery. 🟢🟠

### Monitoring Suites (Operations-Oriented)

- [Zabbix](https://github.com/zabbix/zabbix) - Enterprise-grade monitoring platform with agent-based and agentless monitoring. Mature, highly configurable, strong in traditional infrastructure. 🟢
- [Nagios](https://github.com/NagiosEnterprises/nagioscore) - The grandfather of open-source monitoring. Check-based architecture. Enormous plugin ecosystem but showing its age. 🟢
- [Icinga](https://github.com/Icinga/icinga2) - Modern evolution of Nagios with better APIs, configuration management, and scalability. 🟢
- [Checkmk](https://github.com/Checkmk/checkmk) - Infrastructure and application monitoring with auto-discovery. Scales well for large enterprise environments. 🟢🟠

### Service Mesh Observability

- [Kiali](https://github.com/kiali/kiali) - Observability console for Istio service mesh. Topology visualization, traffic flow, and health analysis. 🟢🔵
- [Linkerd Viz](https://github.com/linkerd/linkerd2) - Built-in telemetry and dashboard for Linkerd service mesh. Lightweight, opinionated. 🟢🔵
- [Hubble](https://github.com/cilium/hubble) - eBPF-powered network observability for Cilium. L3/L4/L7 flow visibility, DNS monitoring, and service dependency mapping — all without sidecars. 🟢🔵🚀

### Database Observability

- [PMM (Percona Monitoring and Management)](https://github.com/percona/pmm) - Open-source database performance monitoring for MySQL, PostgreSQL, and MongoDB. Query analytics, slow query analysis. 🟢
- [pgwatch](https://github.com/cybertec-postgresql/pgwatch) - PostgreSQL-specific monitoring and metrics collection. 🟢
- [pg_stat_monitor](https://github.com/percona/pg_stat_monitor) - PostgreSQL extension for enhanced query performance monitoring. More granular than pg_stat_statements. 🟢
- [VividCortex / SolarWinds DPM](https://www.solarwinds.com/solarwinds-observability/use-cases/system-performance) - SaaS query-level database performance monitoring. 🟠
- [Datadog DBM](https://www.datadoghq.com/product/database-monitoring/) - Database monitoring with query-level explain plans, wait event analysis, and trace correlation. 🟠

### Real User Monitoring (RUM) & Frontend Observability

- [Sentry](https://github.com/getsentry/sentry) - Error tracking and performance monitoring for frontend and backend. Session replay, Web Vitals, and release health tracking. 🟢
- [Grafana Faro](https://github.com/grafana/faro-web-sdk) - Open-source frontend observability SDK. Captures errors, performance, and user events, sends to Grafana stack. 🟢🔵
- [OpenTelemetry Browser SDK](https://opentelemetry.io/docs/languages/js/getting-started/browser/) - OTel instrumentation for web applications. Captures page loads, resource timings, and user interactions. 🟢
- [LogRocket](https://logrocket.com/) - Session replay combined with frontend performance monitoring. 🟠

### AI-Augmented Observability

- [Dynatrace Davis AI](https://www.dynatrace.com/platform/artificial-intelligence/) - Deterministic and causal AI for automatic root-cause analysis. Topology-aware, goes beyond statistical correlation. 🟠
- [Datadog Watchdog](https://docs.datadoghq.com/watchdog/) - ML-driven anomaly detection across metrics, logs, and APM data. Automatic story generation for correlated anomalies. 🟠
- [Moogsoft](https://www.moogsoft.com/) - AIOps platform for alert correlation, noise reduction, and incident clustering. 🟠
- [New Relic AI](https://newrelic.com/platform/applied-intelligence) - Applied intelligence with anomaly detection, incident correlation, and natural-language querying (NRAI). 🟠
- [Honeycomb BubbleUp](https://www.honeycomb.io/platform/bubbleup) - Automated outlier correlation across high-cardinality dimensions. Helps identify "what's different" about slow requests without manual hypotheses. 🟠
- [Coroot](https://github.com/coroot/coroot) - Open-source eBPF-powered observability with automated service map discovery and anomaly detection. 🟢🔵

### SLO Management

- [Sloth](https://github.com/slok/sloth) - SLO generation for Prometheus. Define SLOs in YAML, generates multi-window multi-burn-rate alerts automatically. 🟢🔵
- [Pyrra](https://github.com/pyrra-dev/pyrra) - SLO management and alerting with a web UI. Kubernetes-native, generates Prometheus recording rules and alerts from SLO definitions. 🟢🔵
- [OpenSLO](https://github.com/OpenSLO/OpenSLO) - Open specification for defining SLOs as code. Vendor-neutral, enables GitOps-driven SLO management. 🟢
- [Nobl9](https://www.nobl9.com/) - Enterprise SLO platform connecting multiple data sources to unified SLO tracking and error budget management. 🟠

### Synthetic Monitoring

- [Checkly](https://github.com/checkly/checkly-cli) - Monitoring as code for APIs and browsers. Playwright-based synthetic checks with CI/CD integration. 🟢🔵
- [Grafana Synthetic Monitoring](https://grafana.com/docs/grafana-cloud/testing/synthetic-monitoring/) - Probe-based synthetic monitoring integrated into Grafana Cloud. Multi-location HTTP, DNS, TCP, and ICMP checks. 🟢🔵
- [Uptime Kuma](https://github.com/louislam/uptime-kuma) - Self-hosted monitoring tool with a clean UI. HTTP, TCP, DNS, and keyword monitoring with notifications. Simple and effective. ⭐🟢
- [Sematext](https://www.sematext.com/synthetic-monitoring) - Playwright-based synthetic checks with CI/CD integration, GitHub synchronization, SSL certificate expiration monitoring. 🟢🟠

### Legacy & Historical

- [Graphite](https://github.com/graphite-project/graphite-web) - One of the original time-series storage and graphing systems. Whisper backend, Carbon collector. Historical significance but limited compared to modern alternatives.
- [Redash](https://github.com/getredash/redash) - SQL-first data visualization and collaboration. Connects to many data sources. Minimal maintenance since Databricks acquisition.

## Performance Testing

### Load & Stress Testing

- [k6](https://github.com/grafana/k6) - Modern load testing tool with JavaScript ES6 scripting. Developer-friendly, excellent CLI experience, native Prometheus/Grafana integration. Extensible via Go (xk6). Acquired by Grafana Labs. The current reference for shift-left performance testing. ⭐🟢🔵
- [Gatling](https://github.com/gatling/gatling) - High-performance load testing framework with Scala/Java/Kotlin DSL. Excellent for complex, protocol-level scenarios. Produces detailed HTML reports. Strong in enterprise Java environments. ⭐🟢🚀
- [Locust](https://github.com/locustio/locust) - Python-based load testing framework. Define user behavior in plain Python code. Distributed mode for scaling. Low barrier to entry for Python teams. ⭐🟢
- [Apache JMeter](https://github.com/apache/jmeter) - Veteran load testing tool with GUI and extensive protocol support (HTTP, JDBC, JMS, LDAP, SOAP, etc.). Massive plugin ecosystem. Heavyweight but unmatched protocol breadth. Still widely used in enterprise testing. ⭐🟢
- [Artillery](https://github.com/artilleryio/artillery) - Node.js-based load testing toolkit with YAML-based scenarios. Cloud-native, good Kubernetes support. Supports HTTP, WebSocket, Socket.io, and custom engines. 🟢🔵
- [NBomber](https://github.com/PragmaticFlow/NBomber) - Load testing framework for .NET. C#/F# scripting with a focus on developer ergonomics. v5+ requires commercial license for organizational use (v4 remains Apache-2.0). 🟢
- [Tsung](https://github.com/processone/tsung) - Distributed, multi-protocol load testing tool built on Erlang. Handles massive concurrent connections efficiently. Supports HTTP, WebSocket, XMPP, LDAP, and database protocols. Low maintenance activity since 2023. 🚀
- [GoReplay (gor)](https://github.com/probelabs/goreplay) - Capture and replay production HTTP traffic for load testing and monitoring. Uses real traffic patterns for maximum realism. 🟢🚀
- [Anteon (formerly Ddosify)](https://github.com/getanteon/anteon) - eBPF-based Kubernetes monitoring and performance testing platform with distributed load generation and visual UI. Reduced development activity since mid-2024. 🔵
- [Neoload](https://www.tricentis.com/products/performance-testing-neoload) - Enterprise performance testing platform with codeless and as-code options. Strong SAP, Citrix, and legacy protocol support. 🟠
- [LoadRunner / OpenText](https://www.opentext.com/products/professional-performance-engineering) - The legacy enterprise standard for performance testing. Broad protocol support. Expensive but deeply embedded in many large organizations. 🟠

### HTTP Benchmarking & Micro-Benchmarking

- [wrk2](https://github.com/giltene/wrk2) - Constant-throughput HTTP benchmarking tool that produces accurate latency histograms (HdrHistogram). Fixes the coordinated omission problem present in most benchmarking tools. Essential for understanding true tail latency. Stable but not actively maintained (last significant commits ~2019). 🚀
- [wrk](https://github.com/wg/wrk) - Modern HTTP benchmarking tool with Lua scripting. Fast and simple, but susceptible to coordinated omission. Best used for relative comparisons, not absolute latency measurement. Stable, minimal recent activity. 🚀
- [Vegeta](https://github.com/tsenart/vegeta) - HTTP load testing tool with constant request rate mode. Clean CLI, library usage in Go, and built-in plotting. Good for saturation testing. 🟢🚀
- [hey](https://github.com/rakyll/hey) - Simple HTTP load generator. Successor to Apache Bench (ab). Quick and easy for ad-hoc benchmarks. 🟢
- [oha](https://github.com/hatoo/oha) - HTTP load generator with real-time TUI. Written in Rust for performance. Modern alternative to hey/ab. 🟢🚀
- [bombardier](https://github.com/codesenberg/bombardier) - Fast, cross-platform HTTP benchmarking tool with good latency reporting. 🟢🚀
- [hyperfoil](https://github.com/Hyperfoil/Hyperfoil) - Distributed benchmarking framework designed to avoid coordinated omission. Built for microservice architectures. 🟢🔵🚀

### API Testing & Contract Testing

- [Hurl](https://github.com/Orange-OpenSource/hurl) - Run and test HTTP requests with plain text. Excellent for API testing in CI pipelines. Supports assertions, captures, and chaining. 🟢
- [Postman](https://www.postman.com/) - API development and testing platform. Collection Runner for basic load testing. Newman CLI for CI/CD integration. Ubiquitous in API development. ⭐🟢🟠
- [REST-assured](https://github.com/rest-assured/rest-assured) - Java DSL for testing REST APIs. Fluent syntax, integrates with JUnit/TestNG. Standard for Java-based API testing. 🟢
- [Karate](https://github.com/karatelabs/karate) - BDD-style API testing framework that combines API testing, mocking, and performance testing. Unique Gherkin-like syntax for non-developers. Built-in Gatling integration for load testing. 🟢
- [Step CI](https://github.com/stepci/stepci) - Open-source API testing and monitoring framework. YAML-based workflow definitions, designed for CI/CD. 🟢
- [Pact](https://github.com/pact-foundation) - Contract testing framework for HTTP APIs and messaging. Ensures provider-consumer compatibility without integration tests. Catches breaking changes that cause performance degradation. 🟢
- [Dredd](https://github.com/apiaryio/dredd) - API testing from API description documents (OpenAPI, API Blueprint). Validates implementation matches specification. In maintenance mode.

### gRPC & Protocol-Specific Testing

- [ghz](https://github.com/bojand/ghz) - Simple gRPC benchmarking and load testing tool. Supports unary and streaming RPCs, configurable concurrency, and multiple output formats (CSV, JSON, HTML). 🟢🚀
- [k6 + xk6-grpc](https://github.com/grafana/xk6-grpc) - k6 extension for gRPC load testing. Scriptable gRPC scenarios with the full k6 ecosystem. 🟢🔵
- [k6 + xk6-kafka](https://github.com/mostafa/xk6-kafka) - k6 extension for Apache Kafka load testing. Produce and consume messages at scale. 🟢🔵
- [kafka-producer-perf-test / kafka-consumer-perf-test](https://kafka.apache.org/documentation/#basic_ops_producer_consumer_perf) - Built-in Kafka benchmarking tools for measuring producer and consumer throughput. 🟢
- [RabbitMQ PerfTest](https://github.com/rabbitmq/rabbitmq-perf-test) - Official benchmarking tool for RabbitMQ. Measures throughput and latency for publishing and consuming. 🟢
- [k6 + xk6-websockets](https://grafana.com/docs/k6/latest/javascript-api/k6-websockets/) - Built-in k6 WebSocket support for testing real-time applications, streaming APIs, and bidirectional protocols. 🟢🔵

### Browser & Frontend Performance

- [Lighthouse](https://github.com/GoogleChrome/lighthouse) - Google's auditing tool for performance, accessibility, SEO, and best practices. Produces actionable scores and recommendations. Runnable in Chrome DevTools, CLI, or CI. The baseline for web performance assessment. ⭐🟢
- [WebPageTest](https://github.com/catchpoint/WebPageTest) - Deep web performance analysis with filmstrip views, waterfall charts, and multi-location testing. The gold standard for detailed frontend performance diagnosis. Self-hostable. ⭐🟢
- [Playwright](https://github.com/microsoft/playwright) - Browser automation framework with built-in performance timing APIs. Supports Chromium, Firefox, and WebKit. Excellent for performance testing of single-page applications. ⭐🟢
- [Sitespeed.io](https://github.com/sitespeedio/sitespeed.io) - Open-source toolkit for monitoring and measuring web performance. Integrates Lighthouse, WebPageTest, and browser-level metrics into dashboards (Grafana). Strong for continuous performance monitoring. 🟢
- [Puppeteer](https://github.com/puppeteer/puppeteer) - Chrome DevTools Protocol API for Node.js. Enables programmatic access to Chrome performance traces, network interception, and rendering metrics. 🟢
- [Yellowlab Tools](https://github.com/YellowLabTools/YellowLabTools) - Online tool for auditing frontend code quality and performance. Detects heavy JavaScript, CSS complexity, and rendering issues. 🟢
- [SpeedCurve](https://www.speedcurve.com/) - Continuous frontend performance monitoring with Core Web Vitals tracking, competitive benchmarking, and visual regression. 🟠

### Service Virtualization and Mocking

- [WireMock](https://github.com/wiremock/wiremock) - Flexible HTTP mock server and service virtualization tool. Supports request matching, stateful behavior, response templating, and fault injection. Runs standalone or embedded in JVM tests. ⭐🟢🔵
- [Mountebank](https://github.com/mountebank-testing/mountebank) - Multi-protocol service virtualization (HTTP, HTTPS, TCP, SMTP). Supports stubs, proxies, and injection. Test doubles over the wire. 🟢
- [Hoverfly](https://github.com/SpectoLabs/hoverfly) - Lightweight service virtualization for API simulation and testing. Capture-and-replay mode for building realistic simulations from production traffic. 🟢🔵
- [MockServer](https://github.com/mock-server/mockserver) - Enables mocking of any HTTP/HTTPS system via expectations. Supports forward and callback actions. 🟢
- [Microcks](https://github.com/microcks/microcks) - Open-source tool for API mocking and testing. Imports OpenAPI, AsyncAPI, gRPC, GraphQL, and SOAP contracts. Kubernetes-native. 🟢🔵

### Synthetic Data Generation

- [Faker](https://github.com/faker-js/faker) - Generate realistic fake data (names, addresses, emails, etc.) in JavaScript/TypeScript. Massive locale support. Available in many languages ([Python](https://github.com/joke2k/faker), [Ruby](https://github.com/faker-ruby/faker), [Java — use DataFaker](https://github.com/datafaker-net/datafaker), [Go](https://github.com/bxcodec/faker)). ⭐🟢
- [DataFaker](https://github.com/datafaker-net/datafaker) - Modern Java data generation library. Successor to java-faker with better performance, more providers, and expression-based generation. 🟢
- [Mimesis](https://github.com/lk-geimfari/mimesis) - High-performance fake data generator for Python. Faster than Faker for bulk generation. Strong locale support. 🟢🚀
- [Neosync](https://github.com/nucleuscloud/neosync) - Open-source platform for anonymizing production data and generating synthetic datasets. Acquired by Grow Therapy in 2025; no longer actively maintained. Still usable as a self-hosted solution. 🔵

### Database Performance Testing & Benchmarking

- [HammerDB](https://github.com/TPC-Council/HammerDB) - Open-source database benchmarking tool supporting TPC-C and TPC-H workloads. Supports Oracle, SQL Server, PostgreSQL, MySQL, and MariaDB. Industry standard for database benchmarks. ⭐🟢
- [sysbench](https://github.com/akopytov/sysbench) - Scriptable multi-threaded benchmark tool. Database benchmarks (OLTP), CPU, memory, and file I/O tests. Standard tool for MySQL/MariaDB performance evaluation. ⭐🟢🚀
- [pgbench](https://www.postgresql.org/docs/current/pgbench.html) - PostgreSQL built-in benchmarking. Custom scripts for workload simulation. 🟢
- [YCSB (Yahoo! Cloud Serving Benchmark)](https://github.com/brianfrankcooper/YCSB) - Framework for benchmarking NoSQL and NewSQL databases. Standard workloads (A-F) enable fair comparison across database technologies. ⭐🟢
- [benchbase (formerly OLTPBench)](https://github.com/cmu-db/benchbase) - Multi-DBMS benchmarking framework supporting TPC-C, TPC-H, YCSB, and other workloads. From Carnegie Mellon Database Group. 🟢
- [mysqlslap](https://dev.mysql.com/doc/refman/en/mysqlslap.html) - MySQL built-in load emulation client. Quick and simple for MySQL-specific benchmarks.

### System & Infrastructure Benchmarking

- [fio](https://github.com/axboe/fio) - The reference tool for I/O benchmarking. Configurable workloads (sequential, random, mixed), multiple I/O engines (libaio, io_uring, etc.). Essential for storage performance evaluation. ⭐🟢🚀
- [stress-ng](https://github.com/ColinIanKing/stress-ng) - System stress testing tool covering CPU, memory, I/O, network, and OS-level stressors. 300+ stress methods. Excellent for validating system stability and thermal limits. 🟢🚀
- [Phoronix Test Suite](https://github.com/phoronix-test-suite/phoronix-test-suite) - Comprehensive benchmarking platform with 500+ test profiles. Automated testing, result comparison, and historical tracking. 🟢
- [iperf3](https://github.com/esnet/iperf) - Network bandwidth measurement tool. TCP/UDP throughput testing between two endpoints. The standard for network performance validation. ⭐🟢🚀

### Chaos Engineering & Fault Injection

- [Litmus](https://github.com/litmuschaos/litmus) - CNCF incubating chaos engineering platform for Kubernetes. Extensive experiment library (ChaosHub), GitOps-friendly, Prometheus integration for measuring impact. ⭐🟢🔵
- [Chaos Mesh](https://github.com/chaos-mesh/chaos-mesh) - CNCF incubating Kubernetes-native chaos engineering platform. Pod, network, I/O, time, and JVM fault injection. Dashboard and scheduling. ⭐🟢🔵
- [Gremlin](https://www.gremlin.com/) - Enterprise chaos engineering platform. Managed experiments with safety controls (halt conditions). Supports infrastructure, application, and network attacks. 🟠
- [Chaos Monkey](https://github.com/Netflix/chaosmonkey) - Netflix's original chaos tool: randomly terminates instances in production. Pioneered the discipline. ⭐🟢
- [Pumba](https://github.com/alexei-led/pumba) - Chaos testing for Docker containers. Kill, pause, stop containers and inject network delays/packet loss. Lightweight alternative to full chaos platforms. 🟢🔵
- [Steadybit](https://www.steadybit.com/) - Enterprise reliability platform combining chaos engineering with automated resilience validation. 🟠🔵
- [AWS Fault Injection Service](https://aws.amazon.com/fis/) - Managed fault injection for AWS resources. Native integration with AWS services. 🟠🔵

### Network Simulation & Traffic Shaping

- [tc (Traffic Control)](https://man7.org/linux/man-pages/man8/tc.8.html) - Linux kernel traffic shaping. Netem qdisc for network emulation (delay, loss, reordering, corruption). The foundational tool.
- [Comcast](https://github.com/tylertreat/comcast) - Simple CLI tool for simulating bad network conditions (packet loss, latency, bandwidth). Wraps tc/pfctl. No longer actively maintained.
- [Clumsy](https://github.com/jagt/clumsy) - Windows network condition simulator. Drop, lag, throttle, and reorder packets. 🟢

### CI/CD Integration & Performance Gates

- [Gatling Enterprise](https://gatling.io/platform) - Managed Gatling execution with CI/CD integrations, team collaboration, and historical comparison. 🟠
- [Lighthouse CI](https://github.com/GoogleChrome/lighthouse-ci) - Run Lighthouse in CI with performance budgets. Assert on scores, compare against baselines, and track trends. 🟢
- [Taurus](https://github.com/Blazemeter/taurus) - Automation wrapper for JMeter, Gatling, Locust, and other tools. YAML-based test configuration, unified reporting. Simplifies CI/CD integration for existing test suites. 🟢

### Results Analysis & Reporting

- [k6 HTML Report](https://github.com/benc-uk/k6-reporter) - Generate standalone HTML reports from k6 test results. 🟢
- [HdrHistogram](https://github.com/HdrHistogram/HdrHistogram) - High Dynamic Range Histogram for latency measurement. Captures the full distribution without data loss. Foundation of accurate latency reporting. Available in [Java](https://github.com/HdrHistogram/HdrHistogram), [Go](https://github.com/HdrHistogram/hdrhistogram-go), [C](https://github.com/HdrHistogram/HdrHistogram_c), and more. 🟢🚀
- [Gatling Reports](https://gatling.io/) - Built-in HTML reports with percentile distributions, request/response time series, and active users timeline. Generated automatically after each Gatling run. 🟢
- [Apache JMeter Dashboard](https://jmeter.apache.org/usermanual/generating-dashboard.html) - Built-in HTML dashboard report generator for JMeter. Produces APDEX scores, response time distributions, and throughput analysis. 🟢
- [Taurus Reporting](https://gettaurus.org/docs/Reporting/) - Unified reporting across multiple load testing engines. BlazeMeter integration for cloud reporting. 🟢

### Cloud Provider Services

- [Azure App Testing](https://azure.microsoft.com/en-us/products/app-testing/) - Microsoft's managed load testing service (formerly Azure Load Testing, rebranded September 2025). Supports JMeter and Locust natively with multi-region traffic simulation, server-side metrics correlation via Azure Monitor, and CI/CD integration (Azure DevOps, GitHub Actions). Copilot-assisted test authoring. Pay-per-use pricing (~$0.15/VUH). The most complete first-party cloud provider offering for performance testing. 🟠🔵
- [AWS Distributed Load Testing](https://github.com/aws-solutions/distributed-load-testing-on-aws) - AWS Solutions Implementation that deploys a distributed load testing architecture via CloudFormation (ECS Fargate). Supports JMeter, k6, and Locust scripts. Multi-region execution, scheduling, and baseline comparison. Not a managed SaaS — you deploy and pay for the underlying AWS resources. 🟠🔵

### Developer-Centric Platforms

- [Grafana k6 Cloud](https://grafana.com/products/cloud/k6/) - Managed k6 execution with geographic distribution across multiple global load zones, real-time result visualization in Grafana, and native CI/CD integration. Performance Insights provide automated analysis of test results. The natural choice for teams already using k6 OSS who need scale and collaboration. 🟠
- [Octoperf](https://octoperf.com/) - SaaS performance testing platform built on JMeter with a modern UI, team collaboration, and trend analysis. European-hosted (GDPR-compliant). Supports JMeter scripts natively with enhanced reporting and distributed load generation. Good fit for teams migrating from JMeter to a managed platform. 🟠

### Enterprise Platforms

- [BlazeMeter](https://www.blazemeter.com/) - Cloud performance testing supporting JMeter, Gatling, Locust, Selenium, and Playwright. Mock services, API monitoring, and shared workspaces. Part of Perforce. 🟠

### Tools & Integrations

- [Datadog Synthetic Monitoring + AI](https://docs.datadoghq.com/synthetics/) - Synthetic API and browser tests with ML-powered anomaly detection and intelligent alerting. Correlates synthetic test failures with APM traces. 🟠
- [Dynatrace Load Testing Integration](https://docs.dynatrace.com/docs/deliver/test-pipeline-observability) - Automated quality gates in CI/CD using AI-based performance evaluation. Davis AI compares test results against baselines and detects anomalies in real time. 🟠

## Related

- [awesome-sre-tools](https://github.com/SquadcastHub/awesome-sre-tools) - SRE and production engineering tools.
- [sre-learning-resources](https://github.com/flanksource/sre-learning-resources) - Learning paths for modern SRE skills.
- [awesome-monitoring](https://github.com/Enapiuz/awesome-monitoring) - Monitoring and observability tools.
- [awesome-testing](https://github.com/TheJambo/awesome-testing) - Software testing methodologies and frameworks.
- [awesome-chaos-engineering](https://github.com/dastergon/awesome-chaos-engineering) - Chaos engineering platforms and resources.
- [awesome-kubernetes](https://github.com/run-x/awesome-kubernetes) - Kubernetes tooling and cloud-native patterns.
- [awesome-k8s-security](https://github.com/magnologan/awesome-k8s-security) - Kubernetes security and hardening.
- [awesome-scalability](https://github.com/binhnguyennus/awesome-scalability) - Scalability patterns and architectures.
