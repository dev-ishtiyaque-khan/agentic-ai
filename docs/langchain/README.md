# LangChain: Components Overview (high level)

This repository teaches LangChain's core components and how they fit together. Below is a concise summary of each component we cover, with links to the component README files for deeper details.

If a component README is temporarily removed (05_chains → 13_end_to_end_agents), it is marked "coming soon" and will be restored when ready.

## Components (short summary + link)

- **Models** — The model adapters and LLM interfaces (providers, streaming, batching). See [01_models](01_models/README.md).
- **Prompts** — Templates, chat prompts, placeholders and best practices for building effective prompts. See [02_prompts](02_prompts/README.md).
- **Structured Output** — LLM-native structured output patterns (TypedDict, Pydantic, JSON Schema). See [03_structured_output](03_structured_output/README.md).
- **Output Parsers** — Client-side parsers (JSON/Pydantic/StructuredOutputParser) and integration patterns. See [04_output_parsers](04_output_parsers/README.md).
- **Chains** — Coming soon (README temporarily removed). High-level: compose multiple steps into workflows.
- **Runnables** — Modern composable building blocks that replace older chain patterns. See [06_runnables](06_runnables/README.md).
- **Document Loaders** — Ingest documents from files, web, and databases. See [07_document_loaders](07_document_loaders/README.md).
- **Text Splitters** — Chunking strategies for long documents to fit model context windows. See [08_text_splitters](08_text_splitters/README.md).
- **Vector Stores** — Embedding storage and indexing backends (FAISS, Milvus, Pinecone, etc.). See [09_vector_store](09_vector_store/README.md).
- **Retrievers** — Retrieval strategies and hybrid retrievers for RAG workflows. See [10_retrievers](10_retrievers/README.md).
- **RAG** — Retrieval-Augmented Generation patterns and prompt/document grounding. See [11_rag](11_rag/README.md).
- **Tools & Tool Calling** — How agents call external tools and manage tool responses. See [12_tools_and_tool_calling](12_tools_and_tool_calling/README.md).
- **End-to-End Agents** — Coming soon (README temporarily removed). High-level: agent orchestration, tool use, and production considerations.

## How to use this repo

1. Start with `01_models` and `02_prompts` to learn how to call models and craft prompts.
2. Read `03_structured_output` and `04_output_parsers` when you need reliable structured responses.
3. Explore `06_runnables` and `07_document_loaders` for composing workflows and ingesting data.
4. Progress to retrievers, vector stores, and RAG for production retrieval pipelines.
