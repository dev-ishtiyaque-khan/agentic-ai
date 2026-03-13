# agentic-ai (LangChain Learning Repository)

This repository is a learning-focused collection of LangChain examples and guides.
It’s designed to help you understand how to build reliable, composable AI applications using modern LangChain patterns.

## Start Here (Top-Level Learning Path)

1. **Prerequisites first** — learn core concepts like tokens, prompting, embeddings, hallucinations, and validation.
   - Start from [prerequisites](docs/prerequisites/01_tokens_and_tokenization.md).
2. **Then read the LangChain component guides** — models, prompts, structured output, parsers, runnables, retrieval, and more.
   - Start from [models](docs/langchain/01_models/README.md) and follow the component path.
3. **Run the examples and iterate** — each section contains runnable snippets you can adapt.

## Primary Folders

- `prerequisites/` — foundational concepts you should know before building with LangChain.
- `langchain/` — component-level docs and example patterns for working with LangChain.

## Prerequisites
We do use Ollama's Models for examples, but the concepts and patterns apply to any LLM provider. To run the examples, you can either set up Ollama locally or adapt the code to your preferred provider (OpenAI, Azure, etc.) by changing the model initialization and API calls.

---

> Tip: If you're new to LLMs, reading the `prerequisites/` section first will make the LangChain docs much easier to follow.

---

## Local Model Setup (Ollama)

Most examples in this repository use **Ollama** to run models locally.

Install Ollama from: [https://ollama.com](https://ollama.com)

Pull the model used in examples:

```bash
ollama pull qwen2.5:7b-instruct
```

Start the Ollama server:

```bash
ollama serve
```

By default, Ollama runs at:

```
http://localhost:11434
```

---

## Debugging Requests with Reverse Proxy

In our examples we use a **reverse proxy** so that we can inspect the exact payload being sent to the model (prompts, messages, parameters, etc.).

We use **mitmproxy** for this.

Start the proxy:

```bash
mitmproxy --mode reverse:http://localhost:11434 -p 8080
```

Then configure the model to use the proxy:

```env
MODEL_NAME=qwen2.5:7b-instruct
MODEL_PROVIDER=ollama
MODEL_HOST=http://localhost:11434
REVERSE_PROXY_HOST=http://localhost:8080
```

Model initialization:

```python
model = init_chat_model(
    model=os.getenv("MODEL_NAME"),
    model_provider=os.getenv("MODEL_PROVIDER"),
    base_url=os.getenv("REVERSE_PROXY_HOST")
)
```

Request flow:

```
LangChain → mitmproxy (8080) → Ollama (11434)
```

This allows you to **inspect `/api/chat` requests and responses** directly in the mitmproxy interface for easier debugging.
