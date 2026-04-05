<!-- markdownlint-disable MD024 MD012 -->
# Learning Resources

> Extracted from awesome-observability-tools.md and awesome-performance-testing-tools.md during consolidation into a single awesome-list-compliant README. These resources are preserved here as a seed for curation into idle-ti.me articles (recommended reading lists, talks, podcasts).

---

## Observability

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

## Performance Testing


### Books

#### Performance Testing & Methodology

* *The Art of Application Performance Testing* — Ian Molyneaux (O'Reilly, 2nd ed. 2014) — Complete performance testing lifecycle from strategy to execution, by a 30+ year industry veteran
* *Performance Testing Guidance for Web Applications* — Microsoft patterns & practices — [Free online](https://learn.microsoft.com/en-us/previous-versions/msp-n-p/bb924375(v=pandp.10))
* *Every Computer Performance Book* — Bob Wescott — Practical, vendor-neutral performance analysis methodology
* *Performance Solutions* — Connie U. Smith, Lloyd G. Williams (Addison-Wesley, 2001) — Software Performance Engineering (SPE) methodology: model performance before building

#### Systems Performance

* *Systems Performance* — Brendan Gregg (Addison-Wesley, 2nd ed. 2020) — The definitive guide to systems performance analysis and methodology
* *Understanding Software Dynamics* — Richard L. Sites (Addison-Wesley, 2021) — Modern performance profiling with KUtrace, by the DEC Alpha co-architect
* *The Art of Computer Systems Performance Analysis* — Raj Jain (Wiley, 1991) — Measurement techniques, experimental design, simulation, queueing models — the foundational textbook

#### Capacity Planning & Scalability

* *The Art of Capacity Planning* — John Allspaw, Arun Kejariwal (O'Reilly, 2nd ed. 2017) — Practical capacity planning for web operations
* *Guerrilla Capacity Planning* — Neil J. Gunther (Springer, 2007) — Universal Scalability Law (USL) and tactical capacity planning

#### JVM & Java

* *Java Performance* — Scott Oaks (O'Reilly, 2nd ed. 2020) — Comprehensive JVM performance tuning
* *Optimizing Java* — Benjamin J. Evans, James Gough, Chris Newland (O'Reilly, 2018) — Beyond GC: JIT, bytecode, threading, and cloud performance
* *JVM Performance Engineering* — Monica Beckwith (Addison-Wesley, 2024) — OpenJDK HotSpot internals, GraalVM, ahead-of-time compilation

#### Web & Frontend

* *High Performance Browser Networking* — Ilya Grigorik (O'Reilly) — [Free online](https://hpbn.co/) — Essential reading for frontend and network performance
* *High Performance Web Sites* — Steve Souders (O'Reilly, 2007) — The 14 rules that started modern web performance optimization
* *Web Performance in Action* — Jeremy L. Wagner (Manning, 2017) — HTTP/2, rendering optimization, automated workflows

#### Database Performance

* *SQL Performance Explained* — Markus Winand — [Free online](https://use-the-index-luke.com/) — Vendor-agnostic indexing guide for Oracle, MySQL, PostgreSQL, SQL Server
* *High Performance MySQL* — Silvia Botros, Jeremy Tinley (O'Reilly, 4th ed. 2021) — MySQL optimization at scale

#### Systems Thinking

* *Performance Engineering* — Giuseppe Serazzi (Springer, 2023) — [Free / Open Access](https://link.springer.com/book/10.1007/978-3-031-36763-2) — Performance evaluation through case studies using Java Modelling Tools (JMT)
* *Thinking in Systems: A Primer* — Donella Meadows (Chelsea Green, 2008) — Stocks, flows, feedback loops, and leverage points — essential for capacity reasoning

### Talks & Video Resources

* [Gil Tene — How NOT to Measure Latency](https://www.youtube.com/watch?v=lJ8ydIuPFeU) — Essential talk on coordinated omission and latency measurement
* [Emery Berger — Performance Matters](https://www.youtube.com/watch?v=r-TLSBdHe1A) — Causal profiling and the Coz profiler (Strange Loop 2019)
* [Martin Thompson — Mechanical Sympathy](https://www.infoq.com/presentations/mechanical-sympathy/) — Understanding hardware for high-performance software
* [Bryan Cantrill — The Hurricane's Butterfly](https://www.youtube.com/watch?v=7AO4wz6gI3Q) — Debugging pathologically performing systems (Jane Street 2018)
* [Brendan Gregg — Blazing Performance with Flame Graphs](https://www.brendangregg.com/) — The original flame graph introduction (USENIX LISA 2013)

### Online Resources & Blogs

* [k6 Documentation](https://grafana.com/docs/k6/latest/) — Excellent guides, tutorials, and examples for modern load testing
* [Brendan Gregg's Blog](https://www.brendangregg.com/) — Deep technical content on systems performance
* [Web.dev — Learn Performance](https://web.dev/learn/performance/) — Google's comprehensive course on Core Web Vitals and rendering
* [Gatling Academy](https://academy.gatling.io/) — Free training courses for Gatling
* [Mechanical Sympathy Blog](http://mechanical-sympathy.blogspot.com) — Martin Thompson on low-latency, lock-free systems, and the Disruptor
* [PerfPlanet / Web Performance Calendar](https://calendar.perfplanet.com/) — 24 expert articles every December since 2009
* [High Scalability](https://highscalability.com/) — Architecture case studies from Netflix, Twitter, Amazon, and beyond
* [CNCF TAG App Delivery](https://github.com/cncf/tag-app-delivery) — Cloud-native delivery practices including performance

### Podcasts

* [TestGuild Performance](https://testguild.com/performance-testing/) — Weekly podcast on performance testing and SRE (since 2014)
* [PerfBytes](https://www.perfbytes.com/) — Performance engineering topics and conference coverage

### Standards & Methodologies

* [USE Method](https://www.brendangregg.com/usemethod.html) — Utilization, Saturation, Errors — for resource analysis
* [RED Method](https://grafana.com/blog/the-red-method-how-to-instrument-your-services/) — Rate, Errors, Duration — for service-level analysis
* [Google SRE — Testing for Reliability](https://sre.google/sre-book/testing-reliability/) — Testing practices from Google SRE
* [Performance Testing Guidance (Microsoft)](https://learn.microsoft.com/en-us/previous-versions/msp-n-p/bb924375(v=pandp.10)) — Methodology for web application performance testing
* [Universal Scalability Law (USL)](https://arxiv.org/abs/0808.1431) — Neil Gunther's scalability model that subsumes Amdahl's Law
* [W3C Web Performance APIs](https://www.w3.org/webperf/) — Navigation Timing, Resource Timing, Long Tasks API, and other browser performance standards

### Benchmark Suites & Reference Workloads

* [TPC Benchmarks](https://www.tpc.org/) — Industry-standard OLTP (TPC-C), decision support (TPC-H, TPC-DS), and IoT benchmarks
* [SPEC Benchmarks](https://www.spec.org/) — SPECjbb (Java), SPECweb (web servers), SPECpower (energy efficiency)
* [YCSB](https://github.com/brianfrankcooper/YCSB) — Yahoo! Cloud Serving Benchmark for NoSQL and cloud databases (3,500+ citations)

### Research & Academic Resources

* [ICPE — International Conference on Performance Engineering](https://icpe.spec.org/) — Annual ACM/SPEC conference combining research and industry practice
* [ACM SIGMETRICS](https://www.sigmetrics.org/) — Premier academic venue for performance evaluation research
* *A Survey on Load Testing of Large-Scale Software Systems* — Jiang & Hassan (IEEE TSE, 2015) — Comprehensive survey covering load design, execution, and analysis
* *Software Performance AntiPatterns* — Smith & Williams (WOSP, 2000) — Foundational catalog of recurring performance problems and solutions
* *Hunter: Using Change Point Detection for Performance Regressions* — MongoDB (ICPE, 2023) — Automated regression detection in CI/CD

