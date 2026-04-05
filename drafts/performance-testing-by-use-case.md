# Performance Testing by Use Case

> This content was extracted from `awesome-performance-testing-tools.md` as part of the consolidation into a single awesome-list-compliant README.
> It is preserved here as a seed for a future article on idle-ti.me.

---

Tools are usually organized by **functional category** (load testing, benchmarking, chaos engineering). But real performance testing combines several categories in service of a specific use case. A complementary reading by use case makes tool selection more practical.

## The Use-Case View

| Use case | Categories involved | Key tools |
| -------- | ------------------- | --------- |
| **API load testing in CI/CD** | Load testing, CI/CD integration | k6, Gatling, Artillery |
| **Full-stack performance validation** | Load testing, browser perf, observability | k6, Lighthouse, Grafana |
| **Microservice resilience testing** | Chaos engineering, service virtualization | Litmus, Gremlin, WireMock |
| **Database performance benchmarking** | Benchmarking, data generation | HammerDB, sysbench, pgbench |
| **Frontend experience optimization** | Browser performance, RUM | Lighthouse, WebPageTest, Playwright |
| **Capacity planning & saturation testing** | Load testing, HTTP benchmarking | Gatling, wrk2, Vegeta |
| **Pre-production data realism** | Data generation, service virtualization | Faker, DataFaker, WireMock |

## Why This Matters

A load test without realistic data is theater. A benchmark without failure injection misses half the risk profile. A resilience test that doesn't measure user-observable latency isn't really measuring resilience.

Organizing tools by **use case** instead of category exposes the combinations that actually produce value. It also highlights where most teams under-invest: not in load generation (which is easy) but in the supporting pieces — data realism, observability correlation, failure injection, CI integration.

## Future Expansion Ideas for the Article

- For each use case, a minimal reproducible setup (docker-compose + scripts)
- Common failure modes for each use case (what goes wrong when you skip a category)
- Maturity ladder: what does each use case look like at "getting started" vs "mature" vs "world-class"
- Cost discussion: each use case has very different infrastructure and tooling costs
