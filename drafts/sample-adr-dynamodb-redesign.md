# Sample ADR: DynamoDB Access-Pattern Redesign

This is a **template**, not a finished document — filled in with the facts
already on your resume (the numbers), with `[placeholders]` for the actual
technical specifics only you know. Fill those in with what you actually did;
don't let me guess at your partition-key design or GSI choices, since you'll
need to defend the real details if this comes up in an interview.

Two things to check before publishing this anywhere public:
1. **Accuracy** — every placeholder below should reflect what you actually
   built, not a plausible-sounding guess.
2. **Confidentiality** — check whether Intelex/Fortive has any policy on
   describing internal system architecture publicly. If in doubt, either
   get it reviewed, or genericize identifying details (don't need to say
   "Intelex" — "a compliance SaaS platform at ~3.5M users" carries the same
   signal).

---

## Context

The platform's core dataset (~2TB) was served from a DynamoDB table whose
[original partition key design / access pattern — e.g. "single partition
key without sort-key distribution" or "hot customer IDs concentrated on a
small number of partitions"] was causing:

- p95 read latency of ~800ms
- Recurring hot-partition throttling under peak load

## Decision drivers

- [What made this urgent — e.g. approaching a customer SLA breach, or
  capacity limits ahead of a specific growth milestone]
- [What made it hard — e.g. couldn't take downtime, had N consumers of the
  existing schema, migration had to be backward-compatible during rollout]

## Options considered

1. **[Option A, e.g. "Vertical scaling / provisioned throughput increase"]**
   — rejected because [reason, e.g. "treats the symptom, hot partitions
   persist regardless of total throughput"].
2. **[Option B, e.g. "Add a GSI for the hot access pattern"]** — [why this
   wasn't sufficient alone, if applicable].
3. **[Option C — what you actually chose, e.g. "Redesign the partition key
   to include a distribution suffix / composite key on {customer, shard}"]**
   — chosen because [the real reasoning].

## Decision

[The actual redesign — partition key structure, sort key, any GSIs added,
whether a dual-write/backfill migration strategy was used, how you handled
in-flight writes during cutover.]

## Consequences

- p95 read latency: ~800ms → ~200ms (75% reduction)
- Hot-partition throttling eliminated
- [Any trade-off accepted — e.g. slightly higher write complexity, an extra
  GSI to maintain, migration required X weeks of dual-write]
- [If this pattern was then reused elsewhere — the strongest line you can
  add, if true]

## Rollout

[How you validated before full cutover — e.g. shadow traffic, a canary
percentage, a rollback plan if p95 regressed.]
