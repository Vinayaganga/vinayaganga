### Hi, I'm Vinayaganga

Currently building out a series of RAG (Retrieval-Augmented Generation)
systems projects, each digging into a different piece of how production RAG
actually works — chunking strategy, evaluation, agentic retrieval, and
hybrid search.

## Featured: RAG Systems

Three connected repos, built in sequence:

- **[rag-microservice](https://github.com/Vinayaganga/rag-microservice)** —
  the base RAG engine: ingestion, embedding (Voyage AI), retrieval,
  generation (Claude), a hand-rolled evaluation harness, and hybrid search
  (BM25 + vector, fused via Reciprocal Rank Fusion, re-ranked with Voyage's
  rerank API).
- **[codebase-rag-assistant](https://github.com/Vinayaganga/codebase-rag-assistant)** —
  swaps fixed-size chunking for AST-aware chunking (tree-sitter), so
  retrieval works over function/class boundaries instead of arbitrary
  character windows.
- **[agentic-rag-assistant](https://github.com/Vinayaganga/agentic-rag-assistant)** —
  swaps the fixed retrieve-then-generate pipeline for a tool-use loop, so
  the model decides for itself whether and how many times to search.

See **[rag-microservice/PORTFOLIO.md](https://github.com/Vinayaganga/rag-microservice/blob/main/PORTFOLIO.md)**
for the architecture decisions behind these (Reciprocal Rank Fusion over
score normalization, hand-rolled eval over RAGAS, WASM tree-sitter over
native bindings) and the real bugs found building them.
