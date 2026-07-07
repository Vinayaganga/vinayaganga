### Vinayaganga Panjaje

Full-Stack Engineer (Node.js/JavaScript) · Tech Lead & Staff Engineer · Cloud · System Design

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

- Redesigned a **DynamoDB schema across a 2TB dataset** — cut p95 read
  latency from ~800ms to ~200ms (75%) and eliminated hot-partition failures.
- Diagnosed a stored procedure running synchronously for ~1 hour that was
  timing out every API call after 120s; redesigned it as an async job,
  cutting execution to ~20 minutes and API response time to 2–3 seconds.
- Built a notification microservice processing **100,000+ notifications/day**
  with reliable retries and dead-letter queues, and an append-only
  audit-trail service with full replay capability for compliance.
- Code-review gatekeeper for a team of 10; mentored 5+ engineers through
  structured pairing, including coaching a QA engineer into a developer role.

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
*— what does a RAG engine look like end to end, and how do you know it's
actually working?*
Ingestion → embedding (Voyage AI) → retrieval → generation (Claude), plus a
hand-rolled evaluation harness (Hit@k, MRR, LLM-as-judge) and hybrid search
(BM25 + vector, fused via Reciprocal Rank Fusion, re-ranked with Voyage's
rerank API).

**[codebase-rag-assistant](https://github.com/Vinayaganga/codebase-rag-assistant)**
*— what happens when the documents are code, not prose?*
Chunks by function/class boundary via tree-sitter (WASM, no native
compilation) instead of fixed character windows.

**[agentic-rag-assistant](https://github.com/Vinayaganga/agentic-rag-assistant)**
*— what if the model decided when and how many times to search?*
A tool-use loop instead of a fixed one-shot retrieve — ask it something
that spans two topics and the trace shows two separate searches.

Full writeup — architecture decisions and the real bugs found building
them — in
**[rag-microservice/PORTFOLIO.md](https://github.com/Vinayaganga/rag-microservice/blob/main/PORTFOLIO.md)**.

## Skills

Node.js · TypeScript · C#/.NET Core · React · Angular · AWS (Lambda, DynamoDB, SNS/SQS, CloudWatch) · Azure (Service Bus, Key Vault) · Event-driven & microservice architecture · DynamoDB/SQL schema design · RAG & agentic tool-use

B.E. Computer Science, Visvesvaraya Technological University — AWS & Azure Fundamentals certified (Credly).
