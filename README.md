# Awesome Performance Engineering [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

<p align="center">
  <a href="https://github.com/be-next/awesome-performance-engineering">
    <img src="media/logo.svg" alt="Awesome Performance Engineering" width="400">
  </a>
</p>

> The discipline that ensures systems deliver fast, reliable, and cost-efficient experiences at any scale, combining observability and performance testing.

## Contents

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

Indicators: ⭐ Widely adopted · 🟢 Active · 🔵 Cloud-native · 🟠 Commercial · 🚀 High performance

## Observability

### Metrics Collection & Time-Series Storage

- [Prometheus](https://github.com/prometheus/prometheus) - ⭐🟢🔵 Pull-based cloud-native metrics platform with dimensional data model and PromQL query language.
- [VictoriaMetrics](https://github.com/VictoriaMetrics/VictoriaMetrics) - ⭐🟢🚀 High-performance, cost-efficient Prometheus-compatible TSDB with high-cardinality and long-retention support.
- [Thanos](https://github.com/thanos-io/thanos) - ⭐🟢🔵 Long-term storage, global query view, and high availability layer for Prometheus via sidecar architecture.
- [Mimir](https://github.com/grafana/mimir) - ⭐🟢🔵🚀 Horizontally scalable, multi-tenant Prometheus-compatible TSDB from Grafana Labs.
- [InfluxDB](https://github.com/influxdata/influxdb) - 🟢🟠 Purpose-built time-series database with high write throughput and a Rust-based engine (v3).
- [Grafana Alloy](https://github.com/grafana/alloy) - ⭐🟢🔵 OpenTelemetry-native telemetry collector supporting metrics, logs, traces, and profiles.
- [Telegraf](https://github.com/influxdata/telegraf) - 🟢 Plugin-driven agent for collecting and reporting metrics with 300+ input plugins.
- [StatsD](https://github.com/statsd/statsd) - Lightweight, UDP-based metrics aggregation daemon with broad application support.
- [Netdata](https://github.com/netdata/netdata) - ⭐🟢🚀 Real-time per-second monitoring with built-in anomaly detection and zero-configuration agent.

### Distributed Tracing

- [OpenTelemetry](https://github.com/open-telemetry) - ⭐🟢🔵 Open standard for distributed tracing, metrics, and logs with language-specific SDKs and auto-instrumentation.
- [Jaeger](https://github.com/jaegertracing/jaeger) - ⭐🟢🔵 CNCF graduated distributed tracing backend and UI, originally from Uber.
- [Grafana Tempo](https://github.com/grafana/tempo) - ⭐🟢🔵 High-scale tracing backend requiring only object storage, with native Grafana integration.
- [Zipkin](https://github.com/openzipkin/zipkin) - 🟢 Pioneering distributed tracing system (Twitter, 2012) with a simple architecture.
- [Apache SkyWalking](https://github.com/apache/skywalking) - ⭐🟢🔵 Observability platform with bytecode-injection-based tracing, popular in the Java ecosystem.
- [SigNoz](https://github.com/SigNoz/signoz) - 🟢🔵 Open-source OpenTelemetry-native observability platform with unified metrics, traces, and logs.
- [Pinpoint](https://github.com/pinpoint-apm/pinpoint) - Bytecode-instrumentation-based APM and tracing for Java and PHP with zero-code-change approach.

### Log Management & Log Pipelines

- [Grafana Loki](https://github.com/grafana/loki) - ⭐🟢🔵 Label-based log aggregation that indexes metadata instead of content for cost-efficient storage at scale.
- [Fluent Bit](https://github.com/fluent/fluent-bit) - ⭐🟢🔵🚀 Lightweight, high-performance log processor and forwarder for edge and containerized environments.
- [Fluentd](https://github.com/fluent/fluentd) - 🟢🔵 CNCF graduated unified logging layer with 1000+ plugins for complex routing.
- [Elasticsearch](https://github.com/elastic/elasticsearch) - ⭐🟢🟠 Distributed search and analytics engine with powerful full-text search capabilities.
- [OpenSearch](https://github.com/opensearch-project/OpenSearch) - 🟢🔵 Community-driven, Apache-2.0-licensed fork of Elasticsearch, backed by AWS.
- [Logstash](https://github.com/elastic/logstash) - Flexible log ingestion and transformation pipeline, part of the Elastic Stack.
- [Graylog](https://github.com/Graylog2/graylog2-server) - 🟢🟠 Centralized log management with built-in alerting and dashboards.
- [rsyslog](https://github.com/rsyslog/rsyslog) - 🟢🚀 High-performance system logging daemon handling millions of messages per second.

### Observability Pipelines and Telemetry Processing

- [OpenTelemetry Collector](https://github.com/open-telemetry/opentelemetry-collector) - ⭐🟢🔵 Standard telemetry processing pipeline with receivers, processors, and exporters for any signal.
- [Vector](https://github.com/vectordotdev/vector) - 🟢🚀 End-to-end observability data routing and transformation with programmable VRL transforms.
- [Logstash](https://www.elastic.co/logstash) - ETL-style processing for observability data with powerful filter plugins.
- [Cribl Stream](https://cribl.io/) - 🟠🚀 Commercial observability pipeline for routing, reducing, and enriching telemetry data.

### Visualization & Dashboards

- [Grafana](https://github.com/grafana/grafana) - ⭐🟢 Open-source observability dashboard platform supporting 100+ data sources with alerting and annotations.
- [Kibana](https://github.com/elastic/kibana) - 🟢🟠 Visualization and log exploration for Elasticsearch and OpenSearch data.
- [OpenSearch Dashboards](https://github.com/opensearch-project/OpenSearch-Dashboards) - 🟢🔵 Open-source fork of Kibana for OpenSearch.
- [Apache Superset](https://github.com/apache/superset) - 🟢 SQL-first analytics and dashboarding platform for ad-hoc data exploration.
- [Perses](https://github.com/perses/perses) - 🟢🔵 CNCF sandbox dashboards-as-code project with native PromQL and TraceQL support.
- [KubeStellar Console](https://github.com/kubestellar/console) - 🟢🔵 Multi-cluster Kubernetes dashboard with real-time observability, AI-powered operations, and CNCF project integrations across edge and cloud clusters.

### Profiling & Continuous Performance Analysis

- [Parca](https://github.com/parca-dev/parca) - ⭐🟢🔵 eBPF-based continuous profiling platform with zero-instrumentation and differential flame graphs (CNCF sandbox).
- [Grafana Pyroscope](https://github.com/grafana/pyroscope) - ⭐🟢🔵 Continuous profiling with flame graph visualization and multi-language support.
- [async-profiler](https://github.com/async-profiler/async-profiler) - 🟢🚀 Low-overhead JVM sampling profiler capturing CPU, allocation, and lock contention profiles.
- [perf](https://perfwiki.github.io/) - 🚀 Linux kernel performance analysis tool with hardware counters, tracepoints, and sampling.
- [bpftrace](https://github.com/bpftrace/bpftrace) - 🟢🚀 High-level tracing language for Linux eBPF with dynamic kernel and user-space tracing.
- [bcc (BPF Compiler Collection)](https://github.com/iovisor/bcc) - 🟢🚀 Toolkit for creating eBPF-based tracing programs with dozens of ready-to-use tools.
- [Grafana Beyla](https://github.com/grafana/beyla) - 🟢🔵🚀 eBPF-based zero-code auto-instrumentation generating RED metrics and distributed traces.
- [Perfetto](https://github.com/google/perfetto) - 🟢 System-wide tracing and profiling toolkit from Google for Android, Chrome, and general system analysis.

### Alerting & Incident Response

- [Alertmanager](https://github.com/prometheus/alertmanager) - ⭐🟢 Prometheus-native alert handling with grouping, silencing, inhibition, and routing.
- [Grafana OnCall](https://github.com/grafana/oncall) - 🟢🔵 Open-source on-call management and alert routing with native Grafana integration.
- [Keep](https://github.com/keephq/keep) - 🟢🔵 Open-source alert management platform consolidating alerts from multiple sources.
- [Alerta](https://github.com/alerta/alerta) - 🟢 Unified alert correlation and management across multiple monitoring systems.
- [PagerDuty](https://www.pagerduty.com/) - 🟠 Industry-standard incident response and on-call management platform.
- [Opsgenie](https://www.atlassian.com/software/opsgenie/migration) - 🟠 Alerting and escalation platform, part of the Atlassian suite.
- [Rootly](https://rootly.com/) - 🟠 AI-assisted incident management with automated timelines and postmortem generation.

### Observability Platforms (Integrated)

- [Datadog](https://www.datadoghq.com/) - 🟠 SaaS observability platform with AI-powered anomaly detection and root-cause analysis.
- [Dynatrace](https://www.dynatrace.com/) - 🟠 AI-driven observability with automatic topology discovery and root-cause analysis (Davis AI).
- [New Relic](https://newrelic.com/) - 🟠 Developer-centric observability platform with NRQL query language and a generous free tier.
- [Splunk Observability](https://www.splunk.com/en_us/products/observability.html) - 🟠 Observability built on Splunk's machine data analytics platform.
- [Elastic Observability](https://www.elastic.co/observability) - 🟠 Observability solution built on the Elastic Stack with self-managed and cloud options.
- [Honeycomb](https://www.honeycomb.io/) - 🟠 Observability platform for high-cardinality event data with BubbleUp automated correlation.
- [Grafana Cloud](https://grafana.com/products/cloud/) - 🟠 Managed Grafana stack (Mimir, Loki, Tempo, Pyroscope) with a generous free tier.
- [Instana (IBM)](https://www.ibm.com/products/instana) - 🟠 Automatic infrastructure and application discovery with real-time observability.
- [AppDynamics (Splunk/Cisco)](https://www.splunk.com/en_us/products/splunk-appdynamics.html) - 🟠 Enterprise APM with business transaction monitoring and code-level diagnostics.
- [Chronosphere](https://chronosphere.io/) - 🟠 Cloud-native observability platform focused on metrics at scale with cost control.
- [Lightstep / ServiceNow Cloud Observability](https://www.servicenow.com/products/observability.html) - 🟠 OpenTelemetry-native observability platform, now part of ServiceNow.
- [Sematext](https://sematext.com/) - 🟢🟠 SaaS observability platform with OpenTelemetry-native support and topology discovery.

### Monitoring Suites (Operations-Oriented)

- [Zabbix](https://github.com/zabbix/zabbix) - 🟢 Enterprise-grade monitoring platform with agent-based and agentless monitoring.
- [Nagios](https://github.com/NagiosEnterprises/nagioscore) - 🟢 Pioneering open-source check-based monitoring with an enormous plugin ecosystem.
- [Icinga](https://github.com/Icinga/icinga2) - 🟢 Modern evolution of Nagios with improved APIs, configuration management, and scalability.
- [Checkmk](https://github.com/Checkmk/checkmk) - 🟢🟠 Infrastructure and application monitoring with auto-discovery for large environments.

### Service Mesh Observability

- [Kiali](https://github.com/kiali/kiali) - 🟢🔵 Observability console for Istio with topology visualization and traffic flow analysis.
- [Linkerd Viz](https://github.com/linkerd/linkerd2) - 🟢🔵 Built-in telemetry and dashboard for Linkerd service mesh.
- [Hubble](https://github.com/cilium/hubble) - 🟢🔵🚀 eBPF-powered network observability for Cilium with L3/L4/L7 flow visibility.

### Database Observability

- [PMM (Percona Monitoring and Management)](https://github.com/percona/pmm) - 🟢 Open-source database performance monitoring for MySQL, PostgreSQL, and MongoDB.
- [pgwatch](https://github.com/cybertec-postgresql/pgwatch) - 🟢 PostgreSQL-specific monitoring and metrics collection.
- [pg_stat_monitor](https://github.com/percona/pg_stat_monitor) - 🟢 PostgreSQL extension for enhanced query performance monitoring.
- [VividCortex / SolarWinds DPM](https://www.solarwinds.com/solarwinds-observability/use-cases/system-performance) - 🟠 SaaS query-level database performance monitoring.
- [Datadog DBM](https://www.datadoghq.com/product/database-monitoring/) - 🟠 Database monitoring with query-level explain plans, wait event analysis, and trace correlation.

### Real User Monitoring (RUM) & Frontend Observability

- [Sentry](https://github.com/getsentry/sentry) - 🟢 Error tracking and performance monitoring with session replay and Web Vitals.
- [Grafana Faro](https://github.com/grafana/faro-web-sdk) - 🟢🔵 Open-source frontend observability SDK capturing errors, performance, and user events.
- [OpenTelemetry Browser SDK](https://opentelemetry.io/docs/languages/js/getting-started/browser/) - 🟢 OTel instrumentation for web applications capturing page loads and resource timings.
- [LogRocket](https://logrocket.com/) - 🟠 Session replay combined with frontend performance monitoring.

### AI-Augmented Observability

- [Dynatrace Davis AI](https://www.dynatrace.com/platform/artificial-intelligence/) - 🟠 Deterministic and causal AI for topology-aware automatic root-cause analysis.
- [Datadog Watchdog](https://docs.datadoghq.com/watchdog/) - 🟠 ML-driven anomaly detection across metrics, logs, and APM data.
- [Moogsoft](https://www.moogsoft.com/) - 🟠 AIOps platform for alert correlation, noise reduction, and incident clustering.
- [New Relic AI](https://newrelic.com/platform/applied-intelligence) - 🟠 Applied intelligence with anomaly detection, incident correlation, and natural-language querying.
- [Honeycomb BubbleUp](https://www.honeycomb.io/platform/bubbleup) - 🟠 Automated outlier correlation across high-cardinality dimensions.
- [Coroot](https://github.com/coroot/coroot) - 🟢🔵 Open-source eBPF-powered observability with automated service map discovery.

### SLO Management

- [Sloth](https://github.com/slok/sloth) - 🟢🔵 SLO generation for Prometheus with YAML definitions and multi-window multi-burn-rate alerts.
- [Pyrra](https://github.com/pyrra-dev/pyrra) - 🟢🔵 Kubernetes-native SLO management generating Prometheus recording rules and alerts.
- [OpenSLO](https://github.com/OpenSLO/OpenSLO) - 🟢 Open, vendor-neutral specification for defining SLOs as code.
- [Nobl9](https://www.nobl9.com/) - 🟠 Enterprise SLO platform with unified tracking and error budget management.

### Synthetic Monitoring

- [Checkly](https://github.com/checkly/checkly-cli) - 🟢🔵 Monitoring as code for APIs and browsers with Playwright-based synthetic checks.
- [Grafana Synthetic Monitoring](https://grafana.com/docs/grafana-cloud/testing/synthetic-monitoring/) - 🟢🔵 Probe-based multi-location synthetic monitoring integrated into Grafana Cloud.
- [Uptime Kuma](https://github.com/louislam/uptime-kuma) - ⭐🟢 Self-hosted monitoring tool with HTTP, TCP, DNS, and keyword checks.
- [Sematext](https://sematext.com/synthetic-monitoring/) - 🟢🟠 Playwright-based synthetic checks with CI/CD integration and SSL monitoring.

### Legacy & Historical

- [Graphite](https://github.com/graphite-project/graphite-web) - Pioneering time-series storage and graphing system with Whisper backend and Carbon collector.
- [Redash](https://github.com/getredash/redash) - SQL-first data visualization and collaboration connecting to many data sources.

## Performance Testing

### Load & Stress Testing

- [k6](https://github.com/grafana/k6) - ⭐🟢🔵 Modern load testing tool with JavaScript ES6 scripting and native Prometheus/Grafana integration.
- [Gatling](https://github.com/gatling/gatling) - ⭐🟢🚀 High-performance load testing framework with Scala/Java/Kotlin DSL and detailed HTML reports.
- [Locust](https://github.com/locustio/locust) - ⭐🟢 Python-based load testing framework defining user behavior in plain Python code.
- [Apache JMeter](https://github.com/apache/jmeter) - ⭐🟢 Load testing tool with GUI and extensive protocol support (HTTP, JDBC, JMS, LDAP, SOAP).
- [Artillery](https://github.com/artilleryio/artillery) - 🟢🔵 Node.js-based load testing toolkit with YAML scenarios supporting HTTP, WebSocket, and Socket.io.
- [NBomber](https://github.com/PragmaticFlow/NBomber) - 🟢 Load testing framework for .NET with C#/F# scripting.
- [Tsung](https://github.com/processone/tsung) - 🚀 Erlang-based distributed load testing tool handling massive concurrent connections across multiple protocols.
- [GoReplay (gor)](https://github.com/probelabs/goreplay) - 🟢🚀 Capture and replay production HTTP traffic for load testing with real traffic patterns.
- [Anteon (formerly Ddosify)](https://github.com/getanteon/anteon) - 🔵 eBPF-based Kubernetes performance testing platform with distributed load generation.
- [Neoload](https://www.tricentis.com/products/performance-testing-neoload) - 🟠 Enterprise performance testing platform with codeless and as-code options.
- [LoadRunner / OpenText](https://www.opentext.com/products/professional-performance-engineering) - 🟠 Enterprise performance testing platform with broad protocol support.

### HTTP Benchmarking & Micro-Benchmarking

- [wrk2](https://github.com/giltene/wrk2) - 🚀 Constant-throughput HTTP benchmarking with accurate latency histograms that avoids coordinated omission.
- [wrk](https://github.com/wg/wrk) - 🚀 HTTP benchmarking tool with Lua scripting for quick relative performance comparisons.
- [Vegeta](https://github.com/tsenart/vegeta) - 🟢🚀 HTTP load testing tool with constant request rate mode and built-in plotting.
- [hey](https://github.com/rakyll/hey) - 🟢 Simple HTTP load generator, successor to Apache Bench (ab).
- [oha](https://github.com/hatoo/oha) - 🟢🚀 Rust-based HTTP load generator with real-time TUI.
- [bombardier](https://github.com/codesenberg/bombardier) - 🟢🚀 Fast, cross-platform HTTP benchmarking tool with detailed latency reporting.
- [hyperfoil](https://github.com/Hyperfoil/Hyperfoil) - 🟢🔵🚀 Distributed benchmarking framework designed to avoid coordinated omission.

### API Testing & Contract Testing

- [Hurl](https://github.com/Orange-OpenSource/hurl) - 🟢 Plain-text HTTP request runner for API testing in CI with assertions and chaining.
- [Postman](https://www.postman.com/) - ⭐🟢🟠 API development and testing platform with Newman CLI for CI/CD integration.
- [REST-assured](https://github.com/rest-assured/rest-assured) - 🟢 Java DSL for testing REST APIs with fluent syntax and JUnit/TestNG integration.
- [Karate](https://github.com/karatelabs/karate) - 🟢 BDD-style API testing framework combining API testing, mocking, and performance testing.
- [Step CI](https://github.com/stepci/stepci) - 🟢 Open-source YAML-based API testing and monitoring framework for CI/CD.
- [Pact](https://github.com/pact-foundation) - 🟢 Contract testing framework ensuring provider-consumer compatibility for HTTP APIs and messaging.
- [Dredd](https://github.com/apiaryio/dredd) - API testing tool that validates implementations against OpenAPI and API Blueprint specifications.

### gRPC & Protocol-Specific Testing

- [ghz](https://github.com/bojand/ghz) - 🟢🚀 gRPC benchmarking and load testing tool supporting unary and streaming RPCs.
- [k6 + xk6-grpc](https://github.com/grafana/xk6-grpc) - 🟢🔵 k6 extension for scriptable gRPC load testing scenarios.
- [k6 + xk6-kafka](https://github.com/mostafa/xk6-kafka) - 🟢🔵 k6 extension for Apache Kafka load testing at scale.
- [kafka-producer-perf-test / kafka-consumer-perf-test](https://kafka.apache.org/documentation/#basic_ops_producer_consumer_perf) - 🟢 Built-in Kafka benchmarking tools for producer and consumer throughput.
- [RabbitMQ PerfTest](https://github.com/rabbitmq/rabbitmq-perf-test) - 🟢 Official RabbitMQ benchmarking tool for throughput and latency measurement.
- [k6 + xk6-websockets](https://grafana.com/docs/k6/latest/javascript-api/k6-websockets/) - 🟢🔵 Built-in k6 WebSocket support for testing real-time and bidirectional protocols.

### Browser & Frontend Performance

- [Lighthouse](https://github.com/GoogleChrome/lighthouse) - ⭐🟢 Google's auditing tool for performance, accessibility, and SEO with actionable scores.
- [WebPageTest](https://github.com/catchpoint/WebPageTest) - ⭐🟢 Web performance analysis with filmstrip views, waterfall charts, and multi-location testing.
- [Playwright](https://github.com/microsoft/playwright) - ⭐🟢 Browser automation framework with built-in performance timing APIs for Chromium, Firefox, and WebKit.
- [Sitespeed.io](https://github.com/sitespeedio/sitespeed.io) - 🟢 Open-source web performance monitoring integrating Lighthouse, WebPageTest, and Grafana dashboards.
- [Puppeteer](https://github.com/puppeteer/puppeteer) - 🟢 Chrome DevTools Protocol API enabling programmatic access to performance traces and network interception.
- [Yellowlab Tools](https://github.com/YellowLabTools/YellowLabTools) - 🟢 Frontend code quality and performance auditing for JavaScript, CSS, and rendering issues.
- [SpeedCurve](https://www.speedcurve.com/) - 🟠 Continuous frontend performance monitoring with Core Web Vitals tracking and competitive benchmarking.

### Service Virtualization and Mocking

- [WireMock](https://github.com/wiremock/wiremock) - ⭐🟢🔵 HTTP mock server with request matching, stateful behavior, response templating, and fault injection.
- [Mountebank](https://github.com/mountebank-testing/mountebank) - 🟢 Multi-protocol service virtualization supporting HTTP, HTTPS, TCP, and SMTP.
- [Hoverfly](https://github.com/SpectoLabs/hoverfly) - 🟢🔵 Lightweight service virtualization with capture-and-replay mode for API simulation.
- [MockServer](https://github.com/mock-server/mockserver) - 🟢 HTTP/HTTPS mock server with expectation-based matching and callback actions.
- [Microcks](https://github.com/microcks/microcks) - 🟢🔵 Kubernetes-native API mocking and testing importing OpenAPI, AsyncAPI, gRPC, and GraphQL contracts.

### Synthetic Data Generation

- [Faker](https://github.com/faker-js/faker) - ⭐🟢 Realistic fake data generation for JavaScript/TypeScript with massive locale support.
- [DataFaker](https://github.com/datafaker-net/datafaker) - 🟢 Modern Java data generation library with expression-based generation.
- [Mimesis](https://github.com/lk-geimfari/mimesis) - 🟢🚀 High-performance fake data generator for Python with strong locale support.
- [Neosync](https://github.com/nucleuscloud/neosync) - 🔵 Open-source platform for anonymizing production data and generating synthetic datasets.

### Database Performance Testing & Benchmarking

- [HammerDB](https://github.com/TPC-Council/HammerDB) - ⭐🟢 Open-source database benchmarking tool supporting TPC-C and TPC-H workloads across major databases.
- [sysbench](https://github.com/akopytov/sysbench) - ⭐🟢🚀 Scriptable multi-threaded benchmark tool for OLTP, CPU, memory, and I/O tests.
- [pgbench](https://www.postgresql.org/docs/current/pgbench.html) - 🟢 PostgreSQL built-in benchmarking tool with custom scripts for workload simulation.
- [YCSB (Yahoo! Cloud Serving Benchmark)](https://github.com/brianfrankcooper/YCSB) - ⭐🟢 Framework for benchmarking NoSQL and NewSQL databases with standard workloads.
- [benchbase (formerly OLTPBench)](https://github.com/cmu-db/benchbase) - 🟢 Multi-DBMS benchmarking framework supporting TPC-C, TPC-H, and YCSB workloads.
- [mysqlslap](https://dev.mysql.com/doc/refman/en/mysqlslap.html) - MySQL built-in load emulation client for quick benchmarks.

### System & Infrastructure Benchmarking

- [fio](https://github.com/axboe/fio) - ⭐🟢🚀 Reference I/O benchmarking tool with configurable workloads and multiple engines (libaio, io_uring).
- [stress-ng](https://github.com/ColinIanKing/stress-ng) - 🟢🚀 System stress testing tool with 300+ methods covering CPU, memory, I/O, and network.
- [Phoronix Test Suite](https://github.com/phoronix-test-suite/phoronix-test-suite) - 🟢 Comprehensive benchmarking platform with 500+ test profiles and result comparison.
- [iperf3](https://github.com/esnet/iperf) - ⭐🟢🚀 Network bandwidth measurement tool for TCP/UDP throughput testing.

### Chaos Engineering & Fault Injection

- [Litmus](https://github.com/litmuschaos/litmus) - ⭐🟢🔵 CNCF incubating Kubernetes chaos engineering platform with extensive experiment library.
- [Chaos Mesh](https://github.com/chaos-mesh/chaos-mesh) - ⭐🟢🔵 CNCF incubating Kubernetes-native chaos platform with pod, network, and I/O fault injection.
- [Gremlin](https://www.gremlin.com/) - 🟠 Enterprise chaos engineering platform with managed experiments and safety controls.
- [Chaos Monkey](https://github.com/Netflix/chaosmonkey) - ⭐🟢 Netflix's pioneering chaos tool that randomly terminates instances in production.
- [Pumba](https://github.com/alexei-led/pumba) - 🟢🔵 Chaos testing for Docker containers with network delay and packet loss injection.
- [Steadybit](https://steadybit.com/) - 🟠🔵 Enterprise reliability platform combining chaos engineering with resilience validation.
- [AWS Fault Injection Service](https://aws.amazon.com/fis/) - 🟠🔵 Managed fault injection for AWS resources with native service integration.

### Network Simulation & Traffic Shaping

- [tc (Traffic Control)](https://man7.org/linux/man-pages/man8/tc.8.html) - Linux kernel traffic shaping with netem qdisc for network emulation.
- [Comcast](https://github.com/tylertreat/comcast) - CLI tool for simulating bad network conditions wrapping tc/pfctl.
- [Clumsy](https://github.com/jagt/clumsy) - 🟢 Windows network condition simulator for packet drop, lag, throttle, and reordering.

### CI/CD Integration & Performance Gates

- [Gatling Enterprise](https://gatling.io/platform) - 🟠 Managed Gatling execution with CI/CD integrations and historical comparison.
- [Lighthouse CI](https://github.com/GoogleChrome/lighthouse-ci) - 🟢 Run Lighthouse in CI with performance budgets, baseline comparison, and trend tracking.
- [Taurus](https://github.com/Blazemeter/taurus) - 🟢 YAML-based automation wrapper for JMeter, Gatling, Locust with unified reporting.

### Results Analysis & Reporting

- [k6 HTML Report](https://github.com/benc-uk/k6-reporter) - 🟢 Standalone HTML report generator for k6 test results.
- [HdrHistogram](https://github.com/HdrHistogram/HdrHistogram) - 🟢🚀 High Dynamic Range Histogram for accurate latency measurement capturing the full distribution.
- [Gatling Reports](https://gatling.io/) - 🟢 Built-in HTML reports with percentile distributions and response time series.
- [Apache JMeter Dashboard](https://jmeter.apache.org/usermanual/generating-dashboard.html) - 🟢 Built-in HTML dashboard generating APDEX scores and response time distributions.
- [Taurus Reporting](https://gettaurus.org/docs/Reporting/) - 🟢 Unified reporting across multiple load testing engines with BlazeMeter integration.

### Cloud Provider Services

- [Azure App Testing](https://azure.microsoft.com/en-us/products/app-testing/) - 🟠🔵 Microsoft's managed load testing service supporting JMeter and Locust with multi-region simulation.
- [AWS Distributed Load Testing](https://github.com/aws-solutions/distributed-load-testing-on-aws) - 🟠🔵 Distributed load testing architecture on AWS via CloudFormation supporting JMeter, k6, and Locust.

### Developer-Centric Platforms

- [Grafana k6 Cloud](https://grafana.com/products/cloud/performance-load-testing-k6/) - 🟠 Managed k6 execution with multi-region load zones and real-time Grafana visualization.
- [Octoperf](https://octoperf.com/) - 🟠 SaaS performance testing platform built on JMeter with distributed load generation.

### Enterprise Platforms

- [BlazeMeter](https://www.blazemeter.com/) - 🟠 Cloud performance testing platform supporting JMeter, Gatling, Locust, Selenium, and Playwright.

### Tools & Integrations

- [Datadog Synthetic Monitoring + AI](https://docs.datadoghq.com/synthetics/) - 🟠 Synthetic API and browser tests with ML-powered anomaly detection and APM correlation.
- [Dynatrace Load Testing Integration](https://docs.dynatrace.com/docs/deliver/test-pipeline-observability) - 🟠 Automated CI/CD quality gates using AI-based performance evaluation against baselines.

## Related

- [awesome-sre-tools](https://github.com/SquadcastHub/awesome-sre-tools) - SRE and production engineering tools.
- [sre-learning-resources](https://github.com/flanksource/sre-learning-resources) - Learning paths for modern SRE skills.
- [awesome-monitoring](https://github.com/Enapiuz/awesome-monitoring) - Monitoring and observability tools.
- [awesome-testing](https://github.com/TheJambo/awesome-testing) - Software testing methodologies and frameworks.
- [awesome-chaos-engineering](https://github.com/dastergon/awesome-chaos-engineering) - Chaos engineering platforms and resources.
- [awesome-kubernetes](https://github.com/run-x/awesome-kubernetes) - Kubernetes tooling and cloud-native patterns.
- [awesome-k8s-security](https://github.com/magnologan/awesome-k8s-security) - Kubernetes security and hardening.
- [awesome-scalability](https://github.com/binhnguyennus/awesome-scalability) - Scalability patterns and architectures.
