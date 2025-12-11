# Couchbase AI Services
A platform that helps you simplify, accelerate and operationalize enterprise grade agents.

It combines data pipelines, model serving, observability and end to end ecosystem integrations into a single, secure, data platform built for the agentic era of software.

## Why Enterprise Agents Need a New Platform
Software is entering the agentic era, where agents become the primary interface for computing. 

Agents:

1. Think – plan step by step strategies to achieve a user goal.

2. Act – call tools, APIs and databases.

3. Observe – review outcomes, update context, memory and refine next steps.

This loop repeats until the goal is met, and produces traces that need to be evaluated for debugging, monitoring and learning.

However, building these systems in production today is hard:

- Patchwork Architectures – a dozen specialized tools for ingestion, ETL, tracing, vector search, caching and analytics.

- DIY Pipelines – teams lose days wiring plumbing instead of building differentiated logic.

- Data Sprawl – context is fragmented across OLTP, vector stores, caches, analytics systems and log stores.

- Inference Friction – cross cloud latency, networking rules and slow inference loops.

- Slow Debugging – limited visibility into prompts, tools and traces slows time to market.

The result is slow, expensive, ungoverned and untrustworthy agents. To make agents enterprise grade, you first need the right data foundation.

## Core Services

The Couchbase AI Services Platform is the foundation for building production grade agents without stitching together a fragile toolchain.

Couchbase AI Services is composed of several integrated services:

1. **Model Service** – secure model hosting with caching, guardrails and NVIDIA NIM powered performance.

2. **Vectorization** – automatically embeds, indexes and keeps data up to date as it changes.

3. **Data Processing** – turns raw enterprise content into retrieval ready JSON and vectors.

4. **Agent Catalog** – governance, reuse and observability for prompts, tools and agents.

5. **AI Functions** – call AI models directly from SQL++ queries to enrich data and power analytics.

## Model Service

The Model Service makes it easy to bring raw AI models into production.

### Challenges

Challenges with out of the box model hosting include slow performance, high cost and lack of context. The Model Service addresses this by providing:

- Integrated Caching for faster responses.
- Fast Inference with async batching.
- Built‑in Guardrails.
- Dedicated Environments for models.
- Managed Infra (deployment, scaling, provisioning and monitoring).

### Deployment

You can deploy a model into production in a few steps:

1. Pick Model – open‑source LLMs, embedding models, or partner models.
2. Choose Compute – from extra small through extra large (e.g., 70B‑parameter models).
3. Configure Options – caching, guardrails, and runtime behavior.
4. Deploy – Couchbase manages scaling, provisioning, and monitoring.

Supported providers include Meta, NVIDIA, Mistral, DeepSeek, Snowflake.

### Connectivity
1. Public Endpoints
2. VPC Peering
3. Private Link 

Requests are routed to models with available capacity.
Caching is applied before inference, then responses flow back securely.

This enables enterprise‑grade model hosting without the pain:

- Hosted models in your data environment for privacy.
- Optimized performance using NVIDIA NIM.
- Built‑in guardrails and caching (up to ~5× faster responses with fewer model calls).
- Lower latency, stronger safety and data that does not leave your environment.

### Caching 

The platform provides multiple caching strategies to improve performance and reduce cost:

1. Standard cache – exact match caching for identical requests.
2. Semantic cache – detects when two queries mean the same thing and reuses answers, ideal for Q&A, search and recommendations.
3. Conversational cache – leverages recent chat history for multi turn dialogue so users do not need to repeat themselves.

These caches significantly reduce LLM calls, lowering time and cost while improving user experience.

## Vectorization

Vectorization turns processed content into high quality embeddings and manages vector indexes at scale.

- Automatically embeds and indexes data as it changes.
- Keeps vector indexes up to date so agents always retrieve from fresh context.
- Supports high performance vector search patterns (search, composite, hyperscale).

Couchbase vector indexes support multiple patterns:
1. Search vector – when vectors are used inline with a query that also contains other predicates, keywords, or geo‑coordinates.
2. Composite – when developers control all prompt and context variables.
3. Hyperscale – when a very large corpus of contextual data must be vectorized.

These patterns help you match index design to your application’s retrieval and scalability needs.

## Data Processing Service

The Data Processing Service prepares enterprise data for RAG and agents without DIY ETL.

### Data Sources

Ingest both unstructured and structured data from:

Files: PDF, PNG, JPG, DOC, DOCX, JSON
Object storage: raw data in S3 or preprocessed JSON
Existing Couchbase Capella buckets

### Pipeline

In just a few clicks you can:

1. Choose data source.
2. Configure transformations (including semantic chunking optimized for retrieval).
3. Select an embedding model.
4. Choose a destination collection and index.

The pipeline:

- Extracts text and metadata automatically for better filtering and retrieval.
- Transforms and chunks content for RAG.
- Vectorizes content using Capella‑hosted or external models.
- Writes into a high‑performance vector index, reindexing only changed content.

This delivers end‑to‑end RAG ETL pipelines in minutes, with zero DIY pipeline work.

## Agent Catalog

As organizations scale agents, they face tool explosion, inconsistent behavior and limited debugging visibility. The Agent Catalog brings governance and observability to agents.

### Capabilities

- Tool hub – central catalog of tools with semantic tool selection so agents only receive the tools they need for a given prompt.
- Prompt hub – versioned prompts with annotations and semantic search.
- Agent tracer – unified performance trace store and debugging view powered by SQL++.

### Lifecycle

1. Publish tools and prompts to the catalog.
2. Build and reuse agents using shared assets.
3. Test and debug with end‑to‑end trace analysis.
4. Deploy to production and monitor traces for reliability, performance, and compliance.

This creates a smooth, repeatable path from POC to production.

Prompts and tools stay in your own Git repositories, aligned with your SDLC and governance practices. Access is available via SDK, CLI and UI.

## AI Functions

AI Functions bring LLM power directly into Couchbase via SQL++, eliminating complex ETL jobs and custom pipelines.

Instead of exporting data to external systems and maintaining Spark or Flink pipelines, you can:

Define AI functions once.
Associate them with a model.
Run them directly in SQL++ queries.

### How it works

1. Choose an AI function.
2. Associate a model.
3. Choose the target database/bucket.
4. Write and run a query.

You can invoke AI models directly from SQL++ DML statements, with:

No‑code, predefined functions for sentiment analysis, summarization, and classification.

Prompt support to control the format, tone and style of responses.

Control plane management happens in the model service VPC alongside the model and gateway, while data stays in the data plane, simplifying compliance and security.

AI Functions help agents consume enriched, pre‑processed data and make it easy to automate data analysis tasks at scale.

## Agent Development Impact

By unifying data, models, and governance, Couchbase AI Services removes some of the slowest, hardest parts of building agents:

- RAG pipelines that used to take days or weeks can be built in minutes.
- Model serving with caching, guardrails, and security can be deployed in minutes.
- Observability and governance are built in rather than bolted on.

This lets teams focus on agent behavior and business logic instead of plumbing.

## Ecosystem

Couchbase AI Services integrates with a rich ecosystem, including:

- Agent & RAG frameworks – LangChain, LangGraph, LlamaIndex, Haystack, Crew, Couchbase MCP and MCP based tooling.
- Data & processing partners – Unstructured, Confluent, Vectorize, MOLO17 and others.
- GPU & model partners – NVIDIA (Nemotron, NIM) and leading model providers.

## Read More

- Blog – Capella AI Services: build enterprise‑grade agents: https://www.couchbase.com/blog/capellaaiservicesbuildenterprisegradeagents/
- Press release – Couchbase AI Services put enterprises in control of agentic AI: https://www.couchbase.com/pressreleases/couchbaseaiservicesputenterprisesincontrolofagenticai/
- Documentation – Products AI Services:  
https://www.couchbase.com/products/ai-services/