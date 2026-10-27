# Open-Source RAG & Agentic AI Roadmap

A practical map of the tools and concepts behind modern retrieval-augmented generation (RAG) and agentic AI. Use it as a menu for building skills—not a checklist of tools to master all at once.

## On this page

- [RAG foundations](#rag-foundations)
- [Knowledge and multimodal RAG](#knowledge-and-multimodal-rag)
- [Agentic AI](#agentic-ai)
- [Production engineering](#production-engineering)
- [A production-oriented reference stack](#a-production-oriented-reference-stack)
- [Suggested learning path](#suggested-learning-path)

## RAG foundations

### 1. RAG frameworks and orchestration

These frameworks coordinate the RAG pipeline: ingestion → retrieval → reranking → generation.

- LangChain
- LangGraph
- LlamaIndex
- Haystack
- RAGFlow
- LightRAG
- txtai
- DSPy
- Embedchain
- FlashRAG
- R2R
- RAGLite
- Kotaemon
- Quivr
- Langroid
- Semantic Kernel
- Spring AI
- Pathway

For production-focused learning, start with LangChain and LangGraph, LlamaIndex, Haystack, RAGFlow, or DSPy. LangGraph is especially useful when RAG workflows need stateful orchestration.

### 2. Document loaders, ingestion, and ETL

Use these tools to bring PDFs, office documents, web pages, and data sources into a pipeline.

- Unstructured
- Docling
- Apache Tika
- PyMuPDF
- pdfplumber
- pypdf
- Marker
- MinerU
- Pandoc
- Trafilatura
- BeautifulSoup
- Scrapy
- Playwright
- Firecrawl OSS
- Airbyte
- Apache NiFi
- Meltano
- LangChain loaders
- LlamaIndex readers
- Haystack converters

For a document-heavy RAG project, Docling, Unstructured, and PyMuPDF make a useful starting combination.

### 3. Chunking

Learn the trade-offs between chunking strategies instead of relying on only one splitter:

- Fixed-size chunking
- Recursive chunking
- Sentence chunking
- Paragraph chunking
- Markdown/header chunking
- Semantic chunking
- Token-based chunking
- Parent-child chunking
- Small-to-big retrieval
- Sliding-window chunking
- Late chunking
- Proposition-based chunking
- Agentic chunking
- Document-structure and layout-aware chunking

Useful tools include LangChain text splitters, LlamaIndex node parsers, Chonkie, Docling, and Unstructured.

### 4. Open embedding models

Embedding models are central to local and self-hosted semantic search.

**Model families**

- BGE and BGE-M3
- E5 and multilingual-e5
- GTE
- Nomic Embed
- Jina Embeddings
- Sentence Transformers
- Instructor
- ModernBERT-based embedding models

**Ways to run them**

- sentence-transformers
- Hugging Face Transformers
- TEI (Text Embeddings Inference)
- ONNX Runtime
- vLLM, where supported

### 5. Vector databases and vector search

Common open-source and open-core options include:

- Qdrant
- Milvus
- Weaviate
- Chroma
- pgvector
- FAISS
- LanceDB
- Vespa
- OpenSearch
- Elasticsearch-compatible search stacks
- Redis-compatible vector search implementations
- Typesense
- Meilisearch

A useful progression for hands-on projects is:

**FAISS → Chroma → Qdrant → pgvector → Milvus**

This moves from local experimentation toward production-oriented architectures.

### 6. Sparse retrieval and keyword search

Sparse retrieval complements semantic search with exact-term matching.

- BM25
- BM25S
- TF-IDF
- SPLADE
- Elasticsearch-style lexical search
- OpenSearch
- Lucene
- Tantivy
- Pyserini

A common production pattern is:

**BM25 + dense embeddings → reciprocal rank fusion (RRF) → reranker**

### 7. Hybrid retrieval

Combine retrieval signals and strategies to improve recall and relevance:

- Dense + sparse retrieval
- BM25 + embeddings
- Reciprocal rank fusion (RRF)
- Weighted fusion
- Query fusion
- Multi-query retrieval
- Metadata filtering
- Self-query retrieval
- Parent-document retrieval
- Multi-vector retrieval

BM25 + dense retrieval + RRF is a strong starting design.

### 8. Open-source rerankers

Rerankers refine an initial set of retrieved results so the most relevant context reaches the model.

- BGE Reranker
- Jina Reranker models
- ColBERT and ColBERTv2
- FlashRank
- RankLLM
- SentenceTransformers CrossEncoder
- MonoT5
- RankT5
- cross-encoder/MS-MARCO models

A typical flow is:

**Query → retrieve 50 → hybrid retrieval/RRF → rerank → select top 5 → LLM**

### 9. Advanced RAG patterns

Understand the patterns and when they are useful:

- Naive RAG
- Advanced RAG
- Modular RAG
- Hybrid RAG
- Agentic RAG
- Self-RAG
- Corrective RAG (CRAG)
- Adaptive RAG
- Graph RAG
- HyDE
- Multi-query RAG
- Fusion RAG
- Parent-child RAG
- Recursive retrieval
- Small-to-big retrieval
- Contextual retrieval
- Long-context RAG
- Conversational RAG
- Multimodal RAG
- SQL RAG
- Web RAG
- Knowledge-graph RAG

## Knowledge and multimodal RAG

### 10. Graph RAG and knowledge graphs

**Tools**

- Microsoft GraphRAG
- LightRAG
- Neo4j Community
- NetworkX
- Apache AGE
- Kùzu
- RDFLib
- FalkorDB
- ArangoDB Community
- Memgraph
- LlamaIndex Knowledge Graph
- LangChain graph integrations

Graph RAG is useful when questions depend on relationships and multi-hop reasoning, rather than similarity search alone.

### 11. Multimodal RAG

Explore approaches for documents with images, tables, diagrams, and scanned pages:

- ColPali
- ColQwen
- CLIP
- SigLIP
- Docling
- MinerU
- OCR pipelines
- Vision-language models
- Page-image retrieval
- Table retrieval
- Image-and-text retrieval

## Agentic AI

### 12. Agent frameworks

Major frameworks and SDKs include:

- LangGraph
- CrewAI
- Pydantic AI
- Google ADK
- Microsoft Agent Framework
- OpenAI Agents SDK
- Strands Agents
- smolagents
- Agno
- Mastra
- LlamaIndex Agent Workflows
- Semantic Kernel
- Langroid

LangGraph is a strong option for explicit stateful workflows; Pydantic AI is suited to typed Python systems, and CrewAI supports role-oriented multi-agent applications. Microsoft's newer Agent Framework is worth considering when evaluating the Microsoft ecosystem.

### 13. Agent architectures

Learn the design patterns as well as the frameworks:

- ReAct
- Plan-and-Execute
- Router agent
- Supervisor agent
- Worker agents
- Planner/executor
- Reflection
- Critic agent
- Evaluator/optimizer
- Sequential agents
- Parallel agents
- Hierarchical agents
- Multi-agent collaboration
- Human-in-the-loop
- Event-driven agents
- Stateful agents
- Agentic RAG
- Memory-enabled agents

### 14. Tool calling

Agents can use tools that interact with:

- Python functions
- REST APIs
- Databases and SQL
- Vector databases
- Web search and browsers
- Filesystems and shells
- Code execution
- MCP

A simplified tool cycle is:

**User → agent → decide → tool → result → reason → tool or answer**

### 15. MCP (Model Context Protocol)

Learn the protocol's core concepts and operational concerns:

- MCP server, client, and host
- Tools, resources, and prompts
- Sampling and transports
- Authentication and authorization
- Remote MCP
- Tool discovery
- MCP gateways
- MCP security

Servers can be implemented with the Python or TypeScript SDKs and FastMCP-style frameworks.

### 16. Agent and RAG memory

**Open-source options and techniques**

- Mem0 OSS
- Zep-related OSS components
- Letta
- LangGraph persistence and checkpoints
- Redis
- PostgreSQL
- SQLite
- Qdrant
- Knowledge graphs

Understand the progression:

**Short-term → conversation → episodic → semantic → long-term memory**

## Production engineering

### 17. RAG evaluation

Evaluate retrieval and generation separately rather than relying on one overall score.

**Open and open-core tools**

- Ragas
- DeepEval
- TruLens
- Arize Phoenix
- Opik
- Giskard
- ARES
- RAGChecker
- AutoRAG
- Tonic Validate
- continuous-eval
- Evidently

**Common metrics**

Hit Rate, Precision@K, Recall@K, MRR, MAP, nDCG, Context Precision, Context Recall, Faithfulness, Answer Relevance, and Correctness.

### 18. Agent evaluation

Measure whether agents complete tasks reliably and efficiently:

- Task completion and goal completion
- Tool selection and argument accuracy
- Trajectory correctness
- Step efficiency and planning quality
- Hallucination
- Recovery after tool failure
- Latency, token usage, and cost
- Safety violations

Useful tools include DeepEval, Ragas, Phoenix, Opik, Langfuse, and custom LLM-as-judge pipelines.

### 19. Observability and tracing

**Open and open-core tools**

- Langfuse
- Arize Phoenix
- Opik
- OpenTelemetry
- OpenLLMetry
- OpenInference
- OpenLIT
- LangWatch
- Helicone
- Prometheus
- Grafana
- Loki
- Tempo
- Jaeger

A production observability path might look like:

**LangGraph → OpenTelemetry → Langfuse or Phoenix → Prometheus → Grafana**

Langfuse, Phoenix/OpenInference, and OpenTelemetry-style instrumentation are particularly relevant to RAG and agent traces.

### 20. Guardrails and security

**Tools**

- NeMo Guardrails
- Guardrails AI
- LLM Guard
- Presidio
- Garak
- PyRIT
- DeepTeam
- Prompt-injection defenses, including Rebuff-style approaches

**Topics**

PII → prompt injection → jailbreaks → toxic content → secrets → tool permissions → data leakage → output validation

### 21. Structured output and validation

Structured output is especially important for reliable agent workflows:

- Pydantic
- Instructor
- Outlines
- Guidance
- JSON Schema
- Constrained decoding
- Grammar-constrained generation

### 22. Local open models

Model families worth understanding include:

- Llama
- Qwen
- Mistral
- Gemma
- DeepSeek
- Phi
- Granite

Open weights and open source are not always the same. Check each model's license before using it.

### 23. Inference engineering

**Serving tools**

- vLLM
- SGLang
- Hugging Face TGI
- llama.cpp
- Ollama
- TensorRT-LLM
- ONNX Runtime
- Triton Inference Server

**Core concepts**

Continuous batching → KV cache → PagedAttention → prefix caching → quantization → speculative decoding → tensor parallelism → pipeline parallelism

### 24. API and serving

- FastAPI
- Flask
- Django
- gRPC
- BentoML
- Ray Serve
- LitServe
- Streamlit
- Gradio

### 25. Deployment, MLOps, and LLMOps

**Open-source stack**

- Docker
- Kubernetes
- Helm
- Terraform / OpenTofu
- Argo CD
- Jenkins and other GitHub Actions alternatives
- MLflow
- DVC
- MinIO
- Airflow
- Prefect
- Dagster
- Prometheus
- Grafana

## A production-oriented reference stack

```text
Documents
   ↓
Docling / Unstructured
   ↓
Semantic + parent-child chunking
   ↓
BGE-M3 embeddings
   ↓
┌─────────────────┬──────────────┐
│ BM25 / sparse   │ Qdrant dense │
└────────┬────────┴──────┬───────┘
         ↓               ↓
             RRF
              ↓
        BGE Reranker
              ↓
      Context compression
              ↓
          LangGraph
              ↓
          Agentic RAG
         ↙     ↓     ↘
       SQL    Web    MCP tools
              ↓
       Local / open model
         vLLM / SGLang
              ↓
           FastAPI
```

**Surrounding capabilities**

- **Evaluation:** Ragas, DeepEval, Phoenix
- **Observability:** Langfuse, OpenTelemetry, Prometheus, Grafana
- **Security:** LLM Guard, Presidio, NeMo Guardrails
- **Infrastructure:** Docker, Kubernetes, Redis, PostgreSQL, MLflow

## Suggested learning path

Build one project incrementally instead of trying to learn every tool in the list:

1. Ingest and parse documents.
2. Compare chunking strategies and embedding models.
3. Add vector search, then combine it with BM25 using RRF.
4. Add a reranker and evaluate retrieval quality.
5. Build a stateful RAG workflow and introduce tools or MCP.
6. Add evaluation, tracing, security controls, and deployment.

Choose one tool for each job first; expand the stack only when a project requirement justifies it.
