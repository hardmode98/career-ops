# Story Bank — Master STAR+R Stories

This file accumulates your best interview stories over time. Each evaluation (Block F) adds new stories here. Instead of memorizing 100 answers, maintain 5-10 deep stories that you can bend to answer almost any behavioral question.

## How it works

1. Every time `/career-ops oferta` generates Block F (Interview Plan), new STAR+R stories get appended here
2. Before your next interview, review this file — your stories are already organized by theme
3. The "Big Three" questions can be answered with stories from this bank:
   - "Tell me about yourself" → combine 2-3 stories into a narrative
   - "Tell me about your most impactful project" → pick your highest-impact story
   - "Tell me about a conflict you resolved" → find a story with a Reflection

## Stories

### [Scale] Order-Relay Platform at 1M+/month
**Source:** Report #022 — Atlassian — Software Engineer
**S:** 28,000+ outlets, peaks of 600,000+ daily orders flowing through Restroworks' order pipeline.
**T:** Relay orders reliably at 1M+/month without dropping or duplicating.
**A:** Architected Golang microservices; two-tier caching (in-memory L1 + Redis L2), gRPC for internal calls, connection pooling; Bloom Filters (membership) + Count-Min Sketch (frequency) to cut DB load at peak.
**R:** 99.999% relay success; cut hot-path latency by 75ms.
**Reflection:** At scale, probabilistic data structures beat brute force — exact counts weren't needed, so Count-Min cut DB load cheaply.
**Best for questions about:** distributed systems, scale, performance optimization, reliability, "most impactful project."

### [Reliability] SQS Event-Driven Decoupling
**Source:** Report #022 — Atlassian — Software Engineer
**S:** Tightly coupled order pipeline caused cascading failures under burst traffic.
**T:** Isolate processing stages so one slow consumer couldn't take down the relay.
**A:** Decoupled order processing with Amazon SQS + Redis; async consumers with retry and backpressure.
**R:** Maintained 99.99%+ availability through burst traffic from high-volume aggregators.
**Reflection:** Decoupling is cheap insurance; I'd add a DLQ + replay path earlier next time.
**Best for questions about:** event streaming/messaging, fault tolerance, system design, backpressure, "a time you improved reliability."

### [Ownership] 300K-Line Node 6→22 Migration in 25 Days
**Source:** Report #022 — Atlassian — Software Engineer
**S:** 300K+ line legacy codebase on Node 6, risky to upgrade.
**T:** Migrate to Node 22 without breaking production.
**A:** Built a Claude-as-primary-dev harness — tests as ground truth, TDD (tests first), human gate on every PR.
**R:** Completed in 25 days.
**Reflection:** Ownership at scale means automating the grind while keeping a human gate on every change.
**Best for questions about:** ownership, ambiguity, delivery under pressure, AI-augmented engineering, large refactors.

### [Leadership] Onboarding Ramp 5mo → 2mo
**Source:** Report #022 — Atlassian — Software Engineer
**S:** New engineers took ~5 months to become productive.
**T:** Raise team throughput by shortening ramp.
**A:** Led 9 engineers; standardized onboarding, introduced XP/TDD and pair programming.
**R:** Cut ramp-up from 5 months to 2 months.
**Reflection:** Influence is a system (process), not a personality.
**Best for questions about:** collaboration, influence, leadership, mentorship, process improvement.
