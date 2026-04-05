# Coordinated Omission: Why Your Latency Numbers Lie

> This content was extracted from `awesome-performance-testing-tools.md` as part of the consolidation into a single awesome-list-compliant README.
> It is preserved here as a seed for a future article on idle-ti.me.

---

## The Callout (as it appeared in the list)

> **A note on coordinated omission:** Many benchmarking tools (including wrk, ab, and hey) report misleadingly optimistic latencies because they don't account for queuing delay when the server is overloaded. Tools like wrk2, Vegeta (constant-rate mode), and Hyperfoil explicitly address this. For serious latency analysis, this matters. See [Gil Tene's talk](https://www.youtube.com/watch?v=lJ8ydIuPFeU) for the full explanation.

## What to Expand Into an Article

### The Problem

Coordinated omission is one of the most pervasive and least-understood failure modes in HTTP benchmarking. Most benchmarking tools operate on a simple loop:

1. Send request
2. Wait for response
3. Record latency
4. Repeat

When the server is healthy, this loop runs smoothly and the reported latencies are accurate. But when the server slows down, the tool *also* slows down — because it's waiting synchronously. The tool stops sending requests during the slowdown. Those requests that *would have been sent* simply vanish from the measurement. The result: the tool reports only the latencies it managed to measure, not the latencies that real users would have experienced.

This is coordinated omission: the tool is inadvertently coordinating with the server to hide bad latency.

### Why It Matters for Tail Latency

Average latency is mostly immune to coordinated omission (slow requests are rare). But **p99, p99.9, and p99.99 latencies** — the ones that matter for user experience at scale — are precisely where coordinated omission distorts the picture the most. A tool that reports p99 = 50ms under load may be hiding the fact that real users experienced p99 = 2000ms during the same test.

### The Fix: Constant Request Rate

The solution is to drive load at a constant rate regardless of server response time:

- **wrk2** — Gil Tene's fix for wrk, uses HdrHistogram to capture true latency distributions
- **Vegeta** — constant-rate mode, clean Go library
- **Hyperfoil** — distributed benchmarking framework designed from the ground up to avoid coordinated omission

When a request can't be sent because the previous ones are still in flight, constant-rate tools still *count* the missed opportunities — and the resulting latency includes the queuing delay.

### Further Reading

- [Gil Tene — "How NOT to Measure Latency"](https://www.youtube.com/watch?v=lJ8ydIuPFeU) — The definitive talk. Watch it.
- [HdrHistogram](http://hdrhistogram.org/) — The data structure that makes honest latency measurement tractable
- The original wrk vs. wrk2 discussion on GitHub

## Why This Deserves a Full Article

Coordinated omission is not an academic concern. It has caused production incidents at major companies because load tests passed (p99 looked fine) and then real users saw p99 spikes 10× higher in production. Any performance engineer who writes benchmarks should understand this phenomenon at a deep level — and most don't.
