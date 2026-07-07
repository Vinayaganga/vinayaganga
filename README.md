### Vinayaganga Panjaje

Full-Stack Engineer (Node.js/JavaScript) · Staff Engineer · Cloud · System Design

[vinayaganga@gmail.com](mailto:vinayaganga@gmail.com) · [linkedin.com/in/vinayaganga](https://linkedin.com/in/vinayaganga) · Bangalore, India

![Node.js](https://img.shields.io/badge/Node.js-ESM-339933?logo=node.js&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-Lambda_%7C_DynamoDB_%7C_SQS-FF9900?logo=amazonaws&logoColor=white)
![Azure](https://img.shields.io/badge/Azure-Service_Bus_%7C_Key_Vault-0078D4?logo=microsoftazure&logoColor=white)

12 years in, with deep roots in Node.js and the JavaScript/TypeScript
ecosystem and full-stack range across React, Angular, and cloud-native
backend architecture. I own problems end to end — from requirement
discussions through system design to production on-call — and make sure
the people around me grow along the way.

## What I'm doing day to day

At **Intelex Technologies (Fortive)**, migrating a production SaaS platform
serving **1,400+ organisations and 3.5 million users** off a legacy .NET
monolith onto event-driven Node.js microservices on AWS.

A few of the numbers behind that:

- **Owned the data-layer architecture decision** for a 2TB DynamoDB
  migration — chose the access-pattern/partition-key redesign, wrote up
  the trade-offs, and drove it end to end: cut p95 read latency 800ms→200ms
  (75%) and eliminated hot-partition failures.
- **Root-caused a platform-wide reliability issue** (a synchronous ~1hr
  stored procedure was silently timing out every dependent API call after
  120s) and made the call to redesign it as an async job rather than patch
  around it — cut execution to ~20 minutes and API response time to 2–3s,
  removing a recurring failure mode rather than one incident.
- Built a notification microservice processing **100,000+ notifications/day**
  with reliable retries and dead-letter queues, and an append-only
  audit-trail service with full replay capability for compliance.
- **Set and enforced code-review/architecture standards for a team of 10**
  — nothing merges without sign-off — and built a structured-pairing
  program that ramped 5+ engineers, including a QA→developer transition.

Before this: led an 8-engineer team through a monolith-to-microservices
migration on a manufacturing EHS platform (ThoughtFocus), and built KYC/
payment-gateway integrations handling idempotent retries in financial
workflows (Novigo Solutions).

## Currently building: RAG systems, from scratch, one layer at a time

![Claude](https://img.shields.io/badge/Claude-Sonnet-D97757?logo=anthropic&logoColor=white)
![Voyage AI](https://img.shields.io/badge/Embeddings-Voyage_AI-6E56CF)

Three connected repos, each answering one question a typical "retrieve
top-k, ask an LLM" tutorial glosses over:

**[rag-microservice](https://github.com/Vinayaganga/rag-microservice)**
_— what does a RAG engine look like end to end, and how do you know it's
actually working?_
Ingestion → embedding (Voyage AI) → retrieval → generation (Claude), plus a
hand-rolled evaluation harness (Hit@k, MRR, LLM-as-judge) and hybrid search
(BM25 + vector, fused via Reciprocal Rank Fusion, re-ranked with Voyage's
rerank API).

**[codebase-rag-assistant](https://github.com/Vinayaganga/codebase-rag-assistant)**
_— what happens when the documents are code, not prose?_
Chunks by function/class boundary via tree-sitter (WASM, no native
compilation) instead of fixed character windows.

**[agentic-rag-assistant](https://github.com/Vinayaganga/agentic-rag-assistant)**
_— what if the model decided when and how many times to search?_
A tool-use loop instead of a fixed one-shot retrieve — ask it something
that spans two topics and the trace shows two separate searches.

Full writeup — architecture decisions and the real bugs found building
them — in
**[rag-microservice/PORTFOLIO.md](https://github.com/Vinayaganga/rag-microservice/blob/main/PORTFOLIO.md)**.

## Skills

Node.js · TypeScript · C#/.NET Core · React · Angular · AWS (Lambda, DynamoDB, SNS/SQS, CloudWatch) · Azure (Service Bus, Key Vault) · Event-driven & microservice architecture · DynamoDB/SQL schema design · RAG & agentic tool-use

B.E. Computer Science, Visvesvaraya Technological University — AWS & Azure Fundamentals certified (Credly).
