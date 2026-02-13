# Awesome Performance Testing Tools [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated, opinionated list of tools and resources dedicated to **Performance Testing** as a continuous engineering practice — not just load generation.

Performance testing is about validating that systems behave acceptably under realistic conditions: expected load, peak traffic, degraded infrastructure, and adversarial scenarios. Done well, it provides **confidence before deployment and evidence after incidents**.

This list covers the full performance testing lifecycle — from **workload design and data generation** through **load execution and chaos injection** to **results analysis and CI/CD integration**.

---

## 🎯 Scope & Intent

This list is curated with the following principles:

* Performance testing as a **continuous discipline**, not a pre-release gate
* Emphasis on **realistic workloads** — production-like data, traffic patterns, and failure modes
* Recognition that **shift-left performance** is essential — catching regressions in CI, not in staging
* Tools that **complement observability** — because load generation without visibility is noise
* Inclusion of **chaos engineering** as integral to performance validation — systems must perform under failure, not just under load

The goal is to help practitioners:

* Select tools adapted to their **technology stack, team size, and maturity**
* Build **repeatable, realistic performance test suites** that evolve with the system
* Integrate performance feedback into **delivery pipelines** rather than treating it as a separate phase

---

## 🧭 How to Read This List

Tools are organized by **functional category**, but real performance testing often combines several categories. A complementary reading by use case:

### 🔎 Performance Testing by Use Case

| Use case | Categories involved | Key tools |
| -------- | ------------------- | --------- |
| **API load testing in CI/CD** | Load testing, CI/CD integration | k6, Gatling, Artillery |
| **Full-stack performance validation** | Load testing, browser perf, observability | k6, Lighthouse, Grafana |
| **Microservice resilience testing** | Chaos engineering, service virtualization | Litmus, Gremlin, WireMock |
| **Database performance benchmarking** | Benchmarking, data generation | HammerDB, sysbench, pgbench |
| **Frontend experience optimization** | Browser performance, RUM | Lighthouse, WebPageTest, Playwright |
| **Capacity planning & saturation testing** | Load testing, HTTP benchmarking | Gatling, wrk2, Vegeta |
| **Pre-production data realism** | Data generation, service virtualization | Faker, DataFaker, WireMock |

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
| 🔗 | CI/CD pipeline-ready |
| 🧪 | Developer-friendly / PoC-friendly |
| 🧰 | Operations heritage / legacy-friendly |

---

## Load & Stress Testing

*Scriptable load generators for simulating realistic user traffic, validating throughput, and identifying breaking points.*

* **[k6](https://k6.io/)** ⭐🟢🔵📚🔗🧪 — Modern load testing tool with JavaScript ES6 scripting. Developer-friendly, excellent CLI experience, native Prometheus/Grafana integration. Extensible via Go (xk6). Acquired by Grafana Labs. The current reference for shift-left performance testing. [Go] [AGPL-3.0] — [GitHub](https://github.com/grafana/k6)
* **[Gatling](https://gatling.io/)** ⭐🟢📚🔗🚀 — High-performance load testing framework with Scala/Java/Kotlin DSL. Excellent for complex, protocol-level scenarios. Produces detailed HTML reports. Strong in enterprise Java environments. [Scala/Java] [Apache-2.0] — [GitHub](https://github.com/gatling/gatling)
* **[Locust](https://locust.io/)** ⭐🟢📚🧪 — Python-based load testing framework. Define user behavior in plain Python code. Distributed mode for scaling. Low barrier to entry for Python teams. [Python] [MIT] — [GitHub](https://github.com/locustio/locust)
* **[Apache JMeter](https://jmeter.apache.org/)** ⭐🟢📚🧰 — Veteran load testing tool with GUI and extensive protocol support (HTTP, JDBC, JMS, LDAP, SOAP, etc.). Massive plugin ecosystem. Heavyweight but unmatched protocol breadth. Still widely used in enterprise testing. [Java] [Apache-2.0] — [GitHub](https://github.com/apache/jmeter)
* **[Artillery](https://www.artillery.io/)** 🟢🔵🔗🧪 — Node.js-based load testing toolkit with YAML-based scenarios. Cloud-native, good Kubernetes support. Supports HTTP, WebSocket, Socket.io, and custom engines. [Node.js] [MPL-2.0] — [GitHub](https://github.com/artilleryio/artillery)
* **[NBomber](https://nbomber.com/)** 🟢🔗🧪 — Load testing framework for .NET. C#/F# scripting with a focus on developer ergonomics. v5+ requires commercial license for organizational use (v4 remains Apache-2.0). [C#] [Commercial/Apache-2.0] — [GitHub](https://github.com/PragmaticFlow/NBomber)
* **[Tsung](https://github.com/processone/tsung)** 🚀🧰 — Distributed, multi-protocol load testing tool built on Erlang. Handles massive concurrent connections efficiently. Supports HTTP, WebSocket, XMPP, LDAP, and database protocols. Low maintenance activity since 2023. [Erlang] [GPL-2.0]
* **[GoReplay (gor)](https://goreplay.org/)** 🟢🚀 — Capture and replay production HTTP traffic for load testing and monitoring. Uses real traffic patterns for maximum realism. [Go] [LGPL-3.0] — [GitHub](https://github.com/probelabs/goreplay)
* **[Anteon (formerly Ddosify)](https://getanteon.com/)** 🔵🧪 — eBPF-based Kubernetes monitoring and performance testing platform with distributed load generation and visual UI. Reduced development activity since mid-2024. [Go] [AGPL-3.0] — [GitHub](https://github.com/getanteon/anteon)
* **[Neoload](https://www.tricentis.com/products/performance-testing-neoload)** 🟠📚 — Enterprise performance testing platform with codeless and as-code options. Strong SAP, Citrix, and legacy protocol support. [Commercial]
* **[LoadRunner / OpenText](https://www.opentext.com/products/loadrunner-professional)** 🟠🧰 — The legacy enterprise standard for performance testing. Broad protocol support. Expensive but deeply embedded in many large organizations. [Commercial]

---

## HTTP Benchmarking & Micro-Benchmarking

*High-precision tools for measuring HTTP server throughput, latency distributions, and saturation behavior. Complementary to full load testing — focused on raw numbers rather than user scenarios.*

* **[wrk2](https://github.com/giltene/wrk2)** 🚀 — Constant-throughput HTTP benchmarking tool that produces accurate latency histograms (HdrHistogram). Fixes the coordinated omission problem present in most benchmarking tools. Essential for understanding true tail latency. Stable but not actively maintained (last significant commits ~2019). [C] [Apache-2.0]
* **[wrk](https://github.com/wg/wrk)** 🚀 — Modern HTTP benchmarking tool with Lua scripting. Fast and simple, but susceptible to coordinated omission. Best used for relative comparisons, not absolute latency measurement. Stable, minimal recent activity. [C] [Apache-2.0]
* **[Vegeta](https://github.com/tsenart/vegeta)** 🟢🚀🔗 — HTTP load testing tool with constant request rate mode. Clean CLI, library usage in Go, and built-in plotting. Good for saturation testing. [Go] [MIT]
* **[hey](https://github.com/rakyll/hey)** 🟢🧪 — Simple HTTP load generator. Successor to Apache Bench (ab). Quick and easy for ad-hoc benchmarks. [Go] [Apache-2.0]
* **[oha](https://github.com/hatoo/oha)** 🟢🚀🧪 — HTTP load generator with real-time TUI. Written in Rust for performance. Modern alternative to hey/ab. [Rust] [MIT]
* **[bombardier](https://github.com/codesenberg/bombardier)** 🟢🚀 — Fast, cross-platform HTTP benchmarking tool with good latency reporting. [Go] [MIT]
* **[hyperfoil](https://hyperfoil.io/)** 🟢🔵🚀 — Distributed benchmarking framework designed to avoid coordinated omission. Built for microservice architectures. [Java] [Apache-2.0] — [GitHub](https://github.com/Hyperfoil/Hyperfoil)

> **A note on coordinated omission:** Many benchmarking tools (including wrk, ab, and hey) report misleadingly optimistic latencies because they don't account for queuing delay when the server is overloaded. Tools like wrk2, Vegeta (constant-rate mode), and Hyperfoil explicitly address this. For serious latency analysis, this matters. See [Gil Tene's talk](https://www.youtube.com/watch?v=lJ8ydIuPFeU) for the full explanation.

---

## API Testing & Contract Testing

*Validating API behavior, correctness, and performance at the service boundary — where performance issues often originate and are cheapest to detect.*

* **[Hurl](https://hurl.dev/)** 🟢🔗🧪 — Run and test HTTP requests with plain text. Excellent for API testing in CI pipelines. Supports assertions, captures, and chaining. [Rust] [Apache-2.0] — [GitHub](https://github.com/Orange-OpenSource/hurl)
* **[Postman](https://www.postman.com/)** ⭐🟢📚🟠 — API development and testing platform. Collection Runner for basic load testing. Newman CLI for CI/CD integration. Ubiquitous in API development. [Commercial/Free tier]
* **[REST-assured](https://rest-assured.io/)** 🟢📚 — Java DSL for testing REST APIs. Fluent syntax, integrates with JUnit/TestNG. Standard for Java-based API testing. [Java] [Apache-2.0] — [GitHub](https://github.com/rest-assured/rest-assured)
* **[Karate](https://karatelabs.github.io/karate/)** 🟢📚🧪 — BDD-style API testing framework that combines API testing, mocking, and performance testing. Unique Gherkin-like syntax for non-developers. Built-in Gatling integration for load testing. [Java] [MIT] — [GitHub](https://github.com/karatelabs/karate)
* **[Step CI](https://stepci.com/)** 🟢🔗🧪 — Open-source API testing and monitoring framework. YAML-based workflow definitions, designed for CI/CD. [TypeScript] [MPL-2.0] — [GitHub](https://github.com/stepci/stepci)
* **[Pact](https://pact.io/)** 🟢🔗 — Contract testing framework for HTTP APIs and messaging. Ensures provider-consumer compatibility without integration tests. Catches breaking changes that cause performance degradation. [Multiple] [MIT] — [GitHub](https://github.com/pact-foundation)
* **[Dredd](https://github.com/apiaryio/dredd)** 🔗🧰 — API testing from API description documents (OpenAPI, API Blueprint). Validates implementation matches specification. In maintenance mode. [JavaScript] [MIT]

---

## gRPC & Protocol-Specific Testing

*Performance testing beyond HTTP — gRPC, WebSocket, message queues, and other protocols that power modern architectures.*

* **[ghz](https://ghz.sh/)** 🟢🚀🔗 — Simple gRPC benchmarking and load testing tool. Supports unary and streaming RPCs, configurable concurrency, and multiple output formats (CSV, JSON, HTML). [Go] [Apache-2.0] — [GitHub](https://github.com/bojand/ghz)
* **[k6 + xk6-grpc](https://github.com/grafana/xk6-grpc)** 🟢🔵🔗 — k6 extension for gRPC load testing. Scriptable gRPC scenarios with the full k6 ecosystem. [Go] [AGPL-3.0]
* **[k6 + xk6-kafka](https://github.com/mostafa/xk6-kafka)** 🟢🔵🔗 — k6 extension for Apache Kafka load testing. Produce and consume messages at scale. [Go] [Apache-2.0]
* **[kafka-producer-perf-test / kafka-consumer-perf-test](https://kafka.apache.org/documentation/#basic_ops_producer_consumer_perf)** 🟢🧰 — Built-in Kafka benchmarking tools for measuring producer and consumer throughput. [Java] [Apache-2.0]
* **[RabbitMQ PerfTest](https://github.com/rabbitmq/rabbitmq-perf-test)** 🟢 — Official benchmarking tool for RabbitMQ. Measures throughput and latency for publishing and consuming. [Java] [Apache-2.0/MPL-2.0]
* **[k6 + xk6-websockets](https://grafana.com/docs/k6/latest/javascript-api/k6-experimental/websockets/)** 🟢🔵🔗 — Built-in k6 WebSocket support for testing real-time applications, streaming APIs, and bidirectional protocols. [Go] [AGPL-3.0]

---

## Browser & Frontend Performance

*Measuring and optimizing the performance users actually experience — Core Web Vitals, rendering, resource loading, and perceived speed.*

* **[Lighthouse](https://developer.chrome.com/docs/lighthouse/)** ⭐🟢📚🔗 — Google's auditing tool for performance, accessibility, SEO, and best practices. Produces actionable scores and recommendations. Runnable in Chrome DevTools, CLI, or CI. The baseline for web performance assessment. [JavaScript] [Apache-2.0] — [GitHub](https://github.com/GoogleChrome/lighthouse)
* **[WebPageTest](https://www.webpagetest.org/)** ⭐🟢📚 — Deep web performance analysis with filmstrip views, waterfall charts, and multi-location testing. The gold standard for detailed frontend performance diagnosis. Self-hostable. [PHP] [Apache-2.0] — [GitHub](https://github.com/catchpoint/WebPageTest)
* **[Playwright](https://playwright.dev/)** ⭐🟢📚🔗 — Browser automation framework with built-in performance timing APIs. Supports Chromium, Firefox, and WebKit. Excellent for performance testing of single-page applications. [TypeScript] [Apache-2.0] — [GitHub](https://github.com/microsoft/playwright)
* **[Sitespeed.io](https://www.sitespeed.io/)** 🟢🔗📚 — Open-source toolkit for monitoring and measuring web performance. Integrates Lighthouse, WebPageTest, and browser-level metrics into dashboards (Grafana). Strong for continuous performance monitoring. [JavaScript] [MIT] — [GitHub](https://github.com/sitespeedio/sitespeed.io)
* **[Puppeteer](https://pptr.dev/)** 🟢📚 — Chrome DevTools Protocol API for Node.js. Enables programmatic access to Chrome performance traces, network interception, and rendering metrics. [TypeScript] [Apache-2.0] — [GitHub](https://github.com/puppeteer/puppeteer)
* **[Yellowlab Tools](https://yellowlab.tools/)** 🟢🧪 — Online tool for auditing frontend code quality and performance. Detects heavy JavaScript, CSS complexity, and rendering issues. [JavaScript] [GPL-2.0] — [GitHub](https://github.com/YellowLabTools/YellowLabTools)
* **[SpeedCurve](https://www.speedcurve.com/)** 🟠 — Continuous frontend performance monitoring with Core Web Vitals tracking, competitive benchmarking, and visual regression. [Commercial]

---

## Service Virtualization & Mocking

*Simulating dependencies to isolate components for targeted performance testing — essential when real services are unavailable, expensive, or rate-limited.*

* **[WireMock](https://wiremock.org/)** ⭐🟢📚🔵 — Flexible HTTP mock server and service virtualization tool. Supports request matching, stateful behavior, response templating, and fault injection. Runs standalone or embedded in JVM tests. [Java] [Apache-2.0] — [GitHub](https://github.com/wiremock/wiremock)
* **[Mountebank](https://github.com/bbyars/mountebank)** 🟢📚 — Multi-protocol service virtualization (HTTP, HTTPS, TCP, SMTP). Supports stubs, proxies, and injection. Test doubles over the wire. [JavaScript] [MIT] — [GitHub](https://github.com/mountebank-testing/mountebank)
* **[Hoverfly](https://hoverfly.io/)** 🟢🔵 — Lightweight service virtualization for API simulation and testing. Capture-and-replay mode for building realistic simulations from production traffic. [Go] [Apache-2.0] — [GitHub](https://github.com/SpectoLabs/hoverfly)
* **[MockServer](https://www.mock-server.com/)** 🟢 — Enables mocking of any HTTP/HTTPS system via expectations. Supports forward and callback actions. [Java] [Apache-2.0] — [GitHub](https://github.com/mock-server/mockserver)
* **[Microcks](https://microcks.io/)** 🟢🔵 — Open-source tool for API mocking and testing. Imports OpenAPI, AsyncAPI, gRPC, GraphQL, and SOAP contracts. Kubernetes-native. [Java] [Apache-2.0] — [GitHub](https://github.com/microcks/microcks)
* **[Toxiproxy](https://github.com/Shopify/toxiproxy)** 🟢🔗 — TCP proxy for simulating network conditions (latency, bandwidth, connection failures). From Shopify. Invaluable for testing how applications handle degraded networks. *(See also: [Chaos Engineering](#chaos-engineering--fault-injection), [Network Simulation](#network-simulation--traffic-shaping))* [Go] [MIT]

---

## Synthetic Data Generation

*Creating realistic test datasets that reflect production cardinality, distributions, and edge cases — one of the most underestimated aspects of performance testing realism.*

* **[Faker](https://fakerjs.dev/)** ⭐🟢📚🧪 — Generate realistic fake data (names, addresses, emails, etc.) in JavaScript/TypeScript. Massive locale support. Available in many languages ([Python](https://github.com/joke2k/faker), [Ruby](https://github.com/faker-ruby/faker), [Java — use DataFaker](https://github.com/datafaker-net/datafaker), [Go](https://github.com/bxcodec/faker)). [TypeScript] [MIT] — [GitHub](https://github.com/faker-js/faker)
* **[DataFaker](https://www.datafaker.net/)** 🟢📚 — Modern Java data generation library. Successor to java-faker with better performance, more providers, and expression-based generation. [Java] [Apache-2.0] — [GitHub](https://github.com/datafaker-net/datafaker)
* **[Mimesis](https://mimesis.name/)** 🟢🚀 — High-performance fake data generator for Python. Faster than Faker for bulk generation. Strong locale support. [Python] [MIT] — [GitHub](https://github.com/lk-geimfari/mimesis)
* **[Neosync](https://www.neosync.dev/)** 🔵🧪 — Open-source platform for anonymizing production data and generating synthetic datasets. Acquired by Grow Therapy in 2025; no longer actively maintained. Still usable as a self-hosted solution. [Go] [MIT] — [GitHub](https://github.com/nucleuscloud/neosync)

---

## Database Performance Testing & Benchmarking

*Validating database throughput, query performance, and scalability — often the critical bottleneck in application performance.*

* **[HammerDB](https://www.hammerdb.com/)** ⭐🟢📚 — Open-source database benchmarking tool supporting TPC-C and TPC-H workloads. Supports Oracle, SQL Server, PostgreSQL, MySQL, and MariaDB. Industry standard for database benchmarks. [Tcl] [GPL-2.0] — [GitHub](https://github.com/TPC-Council/HammerDB)
* **[sysbench](https://github.com/akopytov/sysbench)** ⭐🟢🚀 — Scriptable multi-threaded benchmark tool. Database benchmarks (OLTP), CPU, memory, and file I/O tests. Standard tool for MySQL/MariaDB performance evaluation. [C] [GPL-2.0]
* **[pgbench](https://www.postgresql.org/docs/current/pgbench.html)** 🟢🧰 — PostgreSQL built-in benchmarking. Custom scripts for workload simulation. [C] [PostgreSQL License]
* **[YCSB (Yahoo! Cloud Serving Benchmark)](https://github.com/brianfrankcooper/YCSB)** ⭐🟢 — Framework for benchmarking NoSQL and NewSQL databases. Standard workloads (A-F) enable fair comparison across database technologies. [Java] [Apache-2.0]
* **[benchbase (formerly OLTPBench)](https://github.com/cmu-db/benchbase)** 🟢 — Multi-DBMS benchmarking framework supporting TPC-C, TPC-H, YCSB, and other workloads. From Carnegie Mellon Database Group. [Java] [Apache-2.0]
* **[mysqlslap](https://dev.mysql.com/doc/refman/en/mysqlslap.html)** 🧰 — MySQL built-in load emulation client. Quick and simple for MySQL-specific benchmarks. [C] [GPL-2.0]

---

## System & Infrastructure Benchmarking

*Measuring raw system performance — CPU, memory, disk I/O, network — to establish baselines and validate infrastructure before application-level testing.*

* **[fio](https://fio.readthedocs.io/)** ⭐🟢🚀 — The reference tool for I/O benchmarking. Configurable workloads (sequential, random, mixed), multiple I/O engines (libaio, io_uring, etc.). Essential for storage performance evaluation. [C] [GPL-2.0] — [GitHub](https://github.com/axboe/fio)
* **[stress-ng](https://github.com/ColinIanKing/stress-ng)** 🟢🚀 — System stress testing tool covering CPU, memory, I/O, network, and OS-level stressors. 300+ stress methods. Excellent for validating system stability and thermal limits. [C] [GPL-2.0]
* **[Phoronix Test Suite](https://www.phoronix-test-suite.com/)** 🟢📚 — Comprehensive benchmarking platform with 500+ test profiles. Automated testing, result comparison, and historical tracking. [PHP] [GPL-3.0] — [GitHub](https://github.com/phoronix-test-suite/phoronix-test-suite)
* **[iperf3](https://software.es.net/iperf/)** ⭐🟢🚀 — Network bandwidth measurement tool. TCP/UDP throughput testing between two endpoints. The standard for network performance validation. [C] [BSD-3-Clause] — [GitHub](https://github.com/esnet/iperf)

---

## Chaos Engineering & Fault Injection

*Testing system behavior under failure — because production will introduce faults you didn't plan for. Performance under degradation is performance that matters.*

* **[Litmus](https://litmuschaos.io/)** ⭐🟢🔵📚 — CNCF incubating chaos engineering platform for Kubernetes. Extensive experiment library (ChaosHub), GitOps-friendly, Prometheus integration for measuring impact. [Go] [Apache-2.0] — [GitHub](https://github.com/litmuschaos/litmus)
* **[Chaos Mesh](https://chaos-mesh.org/)** ⭐🟢🔵 — CNCF incubating Kubernetes-native chaos engineering platform. Pod, network, I/O, time, and JVM fault injection. Dashboard and scheduling. [Go] [Apache-2.0] — [GitHub](https://github.com/chaos-mesh/chaos-mesh)
* **[Gremlin](https://www.gremlin.com/)** 🟠📚 — Enterprise chaos engineering platform. Managed experiments with safety controls (halt conditions). Supports infrastructure, application, and network attacks. [Commercial]
* **[Chaos Monkey](https://netflix.github.io/chaosmonkey/)** ⭐🟢 — Netflix's original chaos tool: randomly terminates instances in production. Pioneered the discipline. [Go] [Apache-2.0] — [GitHub](https://github.com/Netflix/chaosmonkey)
* **[Pumba](https://github.com/alexei-led/pumba)** 🟢🔵 — Chaos testing for Docker containers. Kill, pause, stop containers and inject network delays/packet loss. Lightweight alternative to full chaos platforms. [Go] [Apache-2.0]
* **[Toxiproxy](https://github.com/Shopify/toxiproxy)** 🟢🔗 — TCP proxy for simulating network conditions. Programmatic control of latency, bandwidth, and connection failures. Simple, focused, effective. [Go] [MIT]
* **[Steadybit](https://www.steadybit.com/)** 🟠🔵 — Enterprise reliability platform combining chaos engineering with automated resilience validation. [Commercial]
* **[AWS Fault Injection Service](https://aws.amazon.com/fis/)** 🟠🔵 — Managed fault injection for AWS resources. Native integration with AWS services. [Commercial]

---

## Network Simulation & Traffic Shaping

*Simulating real-world network conditions — latency, packet loss, bandwidth constraints — to test application behavior over imperfect networks.*

* **[tc (Traffic Control)](https://man7.org/linux/man-pages/man8/tc.8.html)** 🧰 — Linux kernel traffic shaping. Netem qdisc for network emulation (delay, loss, reordering, corruption). The foundational tool. [C] [GPL-2.0]
* **[Toxiproxy](https://github.com/Shopify/toxiproxy)** 🟢🔗 — Application-level TCP proxy for simulating network conditions. Easier to use than tc for application-level testing. [Go] [MIT]
* **[Comcast](https://github.com/tylertreat/comcast)** 🧪🧰 — Simple CLI tool for simulating bad network conditions (packet loss, latency, bandwidth). Wraps tc/pfctl. No longer actively maintained. [Go] [Apache-2.0]
* **[Clumsy](https://jagt.github.io/clumsy/)** 🟢🧪 — Windows network condition simulator. Drop, lag, throttle, and reorder packets. [C] [MIT] — [GitHub](https://github.com/jagt/clumsy)

---

## CI/CD Integration & Performance Gates

*Embedding performance validation into delivery pipelines — making performance feedback continuous rather than episodic.*

* **[k6](https://k6.io/) + [k6-operator](https://github.com/grafana/k6-operator)** ⭐🟢🔵🔗 — Run distributed k6 load tests in Kubernetes via a custom operator. Native threshold-based pass/fail for pipeline gates. [Go] [Apache-2.0]
* **[Gatling Enterprise](https://gatling.io/enterprise/)** 🟠🔗 — Managed Gatling execution with CI/CD integrations, team collaboration, and historical comparison. [Commercial]
* **[Lighthouse CI](https://github.com/GoogleChrome/lighthouse-ci)** 🟢🔗 — Run Lighthouse in CI with performance budgets. Assert on scores, compare against baselines, and track trends. [JavaScript] [Apache-2.0]
* **[Sitespeed.io](https://www.sitespeed.io/)** 🟢🔗 — Continuous web performance monitoring with CI/CD integration. Performance budgets, Grafana dashboards, and historical tracking. [JavaScript] [MIT] — [GitHub](https://github.com/sitespeedio/sitespeed.io)
* **[Taurus](https://gettaurus.org/)** 🟢🔗📚 — Automation wrapper for JMeter, Gatling, Locust, and other tools. YAML-based test configuration, unified reporting. Simplifies CI/CD integration for existing test suites. [Python] [Apache-2.0] — [GitHub](https://github.com/Blazemeter/taurus)
* **[Grafana k6 Cloud](https://grafana.com/products/cloud/k6/)** 🟠🔗 — Managed k6 execution with CI/CD integration and geographic distribution. *(See [Commercial & SaaS](#commercial--saas-platforms) for details)* [Commercial]
* **[BlazeMeter](https://www.blazemeter.com/)** 🟠🔗 — Cloud performance testing with native CI/CD pipeline integration. *(See [Commercial & SaaS](#commercial--saas-platforms) for details)* [Commercial]

---

## Results Analysis & Reporting

*Tools for making sense of performance test results — visualization, comparison, trend analysis, and communication.*

* **[Grafana](https://grafana.com/oss/grafana/)** ⭐🟢📚 — Visualize k6, Gatling, and JMeter results alongside observability data in unified dashboards. The natural integration point between testing and observability. [TypeScript/Go] [AGPL-3.0] — [GitHub](https://github.com/grafana/grafana)
* **[k6 HTML Report](https://github.com/benc-uk/k6-reporter)** 🟢🧪 — Generate standalone HTML reports from k6 test results. [JavaScript] [MIT]
* **[HdrHistogram](https://github.com/HdrHistogram/HdrHistogram)** 🟢🚀 — High Dynamic Range Histogram for latency measurement. Captures the full distribution without data loss. Foundation of accurate latency reporting. Available in [Java](https://github.com/HdrHistogram/HdrHistogram), [Go](https://github.com/HdrHistogram/hdrhistogram-go), [C](https://github.com/HdrHistogram/HdrHistogram_c), and more. [Multiple] [BSD-2-Clause/Public Domain]
* **[Gatling Reports](https://gatling.io/)** 🟢 — Built-in HTML reports with percentile distributions, request/response time series, and active users timeline. Generated automatically after each Gatling run. [Scala]
* **[Apache JMeter Dashboard](https://jmeter.apache.org/usermanual/generating-dashboard.html)** 🟢🧰 — Built-in HTML dashboard report generator for JMeter. Produces APDEX scores, response time distributions, and throughput analysis. [Java]
* **[Taurus Reporting](https://gettaurus.org/docs/Reporting/)** 🟢🔗 — Unified reporting across multiple load testing engines. BlazeMeter integration for cloud reporting. [Python]

---

## Commercial & SaaS Platforms

*Integrated performance testing platforms for teams that need managed infrastructure, geographic distribution, collaboration features, and enterprise support. Choosing between SaaS and open-source is often a question of team maturity, scale, and budget — not technical capability.*

### Cloud Provider Services

* **[Azure App Testing](https://azure.microsoft.com/en-us/products/app-testing/)** 🟠🔵📚 — Microsoft's managed load testing service (formerly Azure Load Testing, rebranded September 2025). Supports JMeter and Locust natively with multi-region traffic simulation, server-side metrics correlation via Azure Monitor, and CI/CD integration (Azure DevOps, GitHub Actions). Copilot-assisted test authoring. Pay-per-use pricing (~$0.15/VUH). The most complete first-party cloud provider offering for performance testing. [Commercial]
* **[AWS Distributed Load Testing](https://aws.amazon.com/solutions/implementations/distributed-load-testing-on-aws/)** 🟠🔵 — AWS Solutions Implementation that deploys a distributed load testing architecture via CloudFormation (ECS Fargate). Supports JMeter, k6, and Locust scripts. Multi-region execution, scheduling, and baseline comparison. Not a managed SaaS — you deploy and pay for the underlying AWS resources. [Commercial] — [GitHub](https://github.com/aws-solutions/distributed-load-testing-on-aws)

### Developer-Centric Platforms

* **[Grafana k6 Cloud](https://grafana.com/products/cloud/k6/)** 🟠🔗 — Managed k6 execution with geographic distribution across multiple global load zones, real-time result visualization in Grafana, and native CI/CD integration. Performance Insights provide automated analysis of test results. The natural choice for teams already using k6 OSS who need scale and collaboration. [Commercial]
* **[Octoperf](https://octoperf.com/)** 🟠🔗📚 — SaaS performance testing platform built on JMeter with a modern UI, team collaboration, and trend analysis. European-hosted (GDPR-compliant). Supports JMeter scripts natively with enhanced reporting and distributed load generation. Good fit for teams migrating from JMeter to a managed platform. [Commercial]
* **~~Flood (Tricentis)~~** — Cloud load testing platform supporting JMeter, Gatling, and Selenium. **Decommissioned in June 2024.** Tricentis has migrated users to NeoLoad. Listed for historical reference only.

### Enterprise Platforms

* **[BlazeMeter](https://www.blazemeter.com/)** 🟠🔗📚 — Cloud performance testing supporting JMeter, Gatling, Locust, Selenium, and Playwright. Mock services, API monitoring, and shared workspaces. Part of Perforce. [Commercial]
* **[Neoload (Tricentis)](https://www.tricentis.com/products/performance-testing-neoload)** 🟠📚 — Enterprise performance testing with codeless design, as-code scripting, and RPA-based protocol support. Strong coverage for SAP, Citrix, and legacy protocols. SLA-based analysis and CI/CD integration. [Commercial]
* **[LoadRunner / OpenText](https://www.opentext.com/products/loadrunner-professional)** 🟠🧰 — The legacy enterprise standard with the broadest protocol support in the industry (50+ protocols). LoadRunner Professional (on-premise) and LoadRunner Cloud (SaaS). Deep APM integration. Expensive but deeply embedded in regulated industries. [Commercial]
* **[Gatling Enterprise](https://gatling.io/enterprise/)** 🟠🔗 — Managed Gatling with distributed execution, real-time dashboards, historical comparison, and team collaboration. Self-hosted or cloud options. [Commercial]

---

## 🤖 AI-Augmented Performance Testing

*AI is entering the performance testing lifecycle — from test generation and workload modeling to results analysis. For the broader perspective on AI in performance engineering, see the [README](README.md#-performance-engineering-in-the-age-of-ai).*

Key areas where AI delivers value in performance testing today:

* **Test script generation** — LLMs generate k6, Gatling, or JMeter scripts from OpenAPI specs, reducing scaffolding effort
* **Workload modeling** — AI analyzes production traffic patterns to generate statistically representative load profiles
* **Automated results analysis** — ML-based anomaly detection flags regressions that static thresholds miss (gradual degradation, bimodal latency distributions)
* **Natural language querying** — asking "what caused the latency spike at minute 12?" instead of navigating dashboards

### Tools & Integrations

* **[k6 Cloud Performance Insights](https://grafana.com/products/cloud/k6/)** 🟠 — Automated analysis of k6 test results. Identifies performance issues, correlates metrics, and suggests root causes. [Commercial]
* **[Datadog Synthetic Monitoring + AI](https://docs.datadoghq.com/synthetics/)** 🟠 — Synthetic API and browser tests with ML-powered anomaly detection and intelligent alerting. Correlates synthetic test failures with APM traces. [Commercial]
* **[Dynatrace Load Testing Integration](https://docs.dynatrace.com/docs/deliver/test-pipeline-observability)** 🟠 — Automated quality gates in CI/CD using AI-based performance evaluation. Davis AI compares test results against baselines and detects anomalies in real time. [Commercial]
* **[Checkly](https://www.checklyhq.com/)** 🟢🔗 — Monitoring-as-code with Playwright-based synthetic tests. AI-assisted test generation from browsing sessions (beta). [TypeScript] [Free tier/Commercial] — [GitHub](https://github.com/checkly/checkly-cli)
* **LLM-assisted test scripting** — GitHub Copilot, Claude Code, and similar AI coding assistants are increasingly effective at generating load test scripts from natural language descriptions or API specifications. Not a standalone tool, but a workflow shift worth noting.

### What's Coming Next

* **Adaptive quality gates** — AI that learns performance baselines across releases and detects statistically significant regressions beyond static thresholds
* **Self-tuning load scenarios** — dynamic adjustment of workload profiles (ramp-up, request mix, data patterns) based on observed system behavior during tests
* **Performance copilots** — AI assistants for end-to-end test strategy: design, execution, analysis, and optimization recommendations
* **Predictive impact analysis** — given a code change (PR diff), predicting which performance aspects are affected and recommending targeted tests

> **Practitioner's view:** AI is most valuable for eliminating **mechanical work** (script scaffolding, result triage, report generation) and augmenting **analytical tasks** (identifying regressions, correlating signals). It does not replace workload design thinking, system understanding, or architectural judgment. Use AI to generate the first draft, then apply engineering expertise to make it realistic.

---

## Learning Resources

### Books

* *Systems Performance* — Brendan Gregg (Addison-Wesley, 2nd ed. 2020) — The definitive guide to systems performance analysis and methodology
* *The Art of Capacity Planning* — John Allspaw, Arun Kejariwal (O'Reilly, 2nd ed. 2017) — Practical capacity planning for web operations
* *Performance Testing Guidance for Web Applications* — Microsoft patterns & practices — [Free online](https://learn.microsoft.com/en-us/previous-versions/msp-n-p/bb924375(v=pandp.10))
* *Java Performance* — Scott Oaks (O'Reilly, 2nd ed. 2020) — Comprehensive JVM performance tuning
* *High Performance Browser Networking* — Ilya Grigorik (O'Reilly) — [Free online](https://hpbn.co/) — Essential reading for frontend and network performance
* *Every Computer Performance Book* — Bob Wescott — Practical, vendor-neutral performance analysis methodology

### Online Resources

* [k6 Documentation](https://k6.io/docs/) — Excellent guides, tutorials, and examples for modern load testing
* [Brendan Gregg's Blog](https://www.brendangregg.com/) — Deep technical content on systems performance
* [Web.dev Performance](https://web.dev/performance/) — Google's comprehensive guide to web performance
* [Gil Tene — How NOT to Measure Latency](https://www.youtube.com/watch?v=lJ8ydIuPFeU) — Essential talk on coordinated omission and latency measurement
* [Gatling Academy](https://academy.gatling.io/) — Free training courses for Gatling
* [CNCF TAG App Delivery](https://github.com/cncf/tag-app-delivery) — Cloud-native delivery practices including performance

### Standards & Methodologies

* [USE Method](https://www.brendangregg.com/usemethod.html) — Utilization, Saturation, Errors — for resource analysis
* [RED Method](https://grafana.com/blog/2018/08/02/the-red-method-how-to-instrument-your-services/) — Rate, Errors, Duration — for service-level analysis
* [Google SRE — Testing for Reliability](https://sre.google/sre-book/testing-reliability/) — Testing practices from Google SRE
* [Performance Testing Guidance (Microsoft)](https://learn.microsoft.com/en-us/previous-versions/msp-n-p/bb924375(v=pandp.10)) — Methodology for web application performance testing

---

## Contributing

Contributions are welcome. Please read **[CONTRIBUTING.md](CONTRIBUTING.md)** before submitting changes.

## License

Released under **CC0 1.0 Universal**.
