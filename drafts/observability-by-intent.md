# Reading Observability by Intent

> This content was extracted from `awesome-observability-tools.md` as part of the consolidation into a single awesome-list-compliant README.
> It is preserved here as a seed for a future article on idle-ti.me.

---

Tools are usually organized by **technical building blocks** (metrics, tracing, logs, profiling). But real observability problems are expressed in terms of **intent**: what am I trying to understand, debug, or prove? A cross-reference by intent is a more practical entry point for many practitioners.

## The Intent-Based View

| Intent | Building blocks | Key tools |
| ------ | --------------- | --------- |
| **Golden Signals / RED / USE** | Metrics, dashboards, alerting | Prometheus, Grafana, VictoriaMetrics, Alertmanager |
| **Latency propagation & dependency analysis** | Distributed tracing | OpenTelemetry, Jaeger, Tempo, Zipkin |
| **High-cardinality debugging & unknown-unknowns** | Event-based observability, rich context | OpenTelemetry, tracing backends, structured logging |
| **Low-overhead production profiling** | Continuous profiling, eBPF | Parca, Pyroscope, async-profiler, bpftrace |
| **Black-box & legacy systems** | Metrics scraping, log-based analysis | StatsD, Graphite, Zabbix, Checkmk |
| **Cost-efficient observability at scale** | Telemetry pipelines, sampling | OTel Collector, Vector, Fluent Bit |

## Why This Matters

Tool taxonomies optimize for the tool vendor's mental model — metrics here, traces there, logs elsewhere. But when an engineer is paged at 3 AM, they don't think "I need a time-series database" — they think "why is checkout slow right now?"

Reading observability by intent flips the mental model back to the practitioner's actual question. It also makes it clear that **most real problems require combining multiple building blocks**, and that choosing tools coherently matters more than stacking them blindly.

## Future Expansion Ideas for the Article

- For each intent, describe the typical workflow step-by-step (signal → correlation → hypothesis → validation)
- Add anti-patterns: what happens when you try to solve each intent with the wrong building block
- Case studies: real incidents where the intent-driven approach outperformed the tool-driven approach
- Decision tree: starting from a symptom, which building block to reach for first
