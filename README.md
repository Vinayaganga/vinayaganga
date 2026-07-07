### Hi, I'm Vinayaganga

I've been taking RAG (Retrieval-Augmented Generation) apart piece by piece —
not just building "a RAG app," but treating each layer (chunking,
retrieval, evaluation, agentic search) as its own thing worth getting right
and being able to explain.

![Node.js](https://img.shields.io/badge/Node.js-ESM-339933?logo=node.js&logoColor=white)
![Claude](https://img.shields.io/badge/Claude-Sonnet-D97757?logo=anthropic&logoColor=white)
![Voyage AI](https://img.shields.io/badge/Embeddings-Voyage_AI-6E56CF)
![Express](https://img.shields.io/badge/Express-API-000000?logo=express&logoColor=white)

## The arc: three repos, one question each

Each project exists to answer one specific question a plain "retrieve top-k,
ask Claude" tutorial glosses over.

**[rag-microservice](https://github.com/Vinayaganga/rag-microservice)**
*— what does a RAG engine look like end to end, and how do you know it's
actually working?*
Ingestion → embedding (Voyage AI, asymmetric query/document vectors) →
retrieval → generation, plus a hand-rolled evaluation harness (Hit@k, MRR,
LLM-as-judge) and hybrid search (BM25 + vector, fused via Reciprocal Rank
Fusion, re-ranked with Voyage's rerank API).

**[codebase-rag-assistant](https://github.com/Vinayaganga/codebase-rag-assistant)**
*— what happens when the documents are code, not prose?*
Chunks by function/class boundary via tree-sitter (WASM, no native
compilation) instead of fixed character windows — so retrieval returns a
whole coherent function, not an arbitrary slice of one.

**[agentic-rag-assistant](https://github.com/Vinayaganga/agentic-rag-assistant)**
*— what if the model decided when and how many times to search, instead of
a fixed one-shot retrieve?*
A tool-use loop: ask it something that spans two topics and watch the trace
show two separate searches, not one confused one.

## Some of what actually broke

The interesting part usually isn't the feature — it's the bug that revealed
an assumption was wrong:

- The codebase chunker silently collapsed **every exported function** in a
  file into one giant "leftover" chunk, because `export function foo() {}`
  parses as an `export_statement` wrapping the real node, not a bare
  `function_declaration`. Only caught by ingesting real code and noticing
  the chunk counts didn't add up.
- A vector-vs-hybrid-search comparison came back a **flat tie** — both
  scored 100% Hit@5. Not a bug: the test corpus was still too small for the
  two methods to ever disagree. Wrote that down instead of hiding it.
- Free-tier embedding APIs cap you at 3 requests/minute, which you will not
  find out until you try to ingest more than two documents at once.

Full writeup, with the reasoning behind each architecture choice, in
**[rag-microservice/PORTFOLIO.md](https://github.com/Vinayaganga/rag-microservice/blob/main/PORTFOLIO.md)**.
