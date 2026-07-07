# Proposed bullet rewrites — Staff-level framing

Same facts as the current README, reframed to surface scope/ownership rather
than just "what I did." Review before I apply these to the live README —
I've only reworded, not added new claims, but you know the real scope
(e.g. whether the DynamoDB redesign's access patterns were reused by other
teams) better than I do, so adjust anything that overclaims.

## Current

> - Redesigned a **DynamoDB schema across a 2TB dataset** — cut p95 read
>   latency from ~800ms to ~200ms (75%) and eliminated hot-partition failures.

## Proposed

> - **Owned the data-layer architecture decision** for a 2TB DynamoDB
>   migration — chose the access-pattern/partition-key redesign, wrote up
>   the trade-offs, and drove it end to end: cut p95 read latency 800ms→200ms
>   (75%) and eliminated hot-partition failures. *(If any other service/team
>   reused this access-pattern approach, say so explicitly here — that's the
>   single strongest edit you could make.)*

---

## Current

> - Diagnosed a stored procedure running synchronously for ~1 hour that was
>   timing out every API call after 120s; redesigned it as an async job,
>   cutting execution to ~20 minutes and API response time to 2–3 seconds.

## Proposed

> - **Root-caused a platform-wide reliability issue** (a synchronous ~1hr
>   stored procedure was silently timing out every dependent API call after
>   120s) and made the call to redesign it as an async job rather than patch
>   around it — cut execution to ~20 minutes and API response time to 2–3s,
>   removing a recurring failure mode rather than one incident.

---

## Current

> - Code-review gatekeeper for a team of 10; mentored 5+ engineers through
>   structured pairing, including coaching a QA engineer into a developer role.

## Proposed

> - **Set and enforced code-review/architecture standards for a team of 10**
>   — nothing merges without sign-off — and built a structured-pairing
>   program that ramped 5+ engineers, including a QA→developer transition.
>   *(A Staff-level committee will ask "did anyone outside your team adopt
>   this?" — if the pairing structure or review standards spread beyond your
>   immediate team, that's worth a sentence.)*

---

## New: strategic/direction-setting (only add if true)

The current bullets are all "I built/fixed X." Staff loops specifically probe
for at least one line like:

> - Authored the technical proposal for [X migration/decision], reviewed by
>   [N teams / architecture group], which became the standard approach for
>   [scope].

If you've written any design doc, RFC, or even a detailed Slack/Confluence
proposal that shaped a decision beyond your immediate task — even informally
— that's worth turning into an explicit bullet. It's usually the single
highest-leverage sentence on a Staff-track resume, and right now there isn't
one on yours.
