# llmDemos

Jupyter notebooks working through semantic search, prompt engineering, RAG and agents with LLMs.

## Notebooks

| Notebook | What it covers |
|---|---|
| [02_semantic_search.ipynb](02_semantic_search.ipynb) | Semantic search with OpenAI embeddings and Pinecone, re-ranking with a cross-encoder, an open-source embedding comparison, and the start of fine-tuning a re-ranker. |
| [03_prompt_engineering.ipynb](03_prompt_engineering.ipynb) | Prompting basics: plain instructions, few-shot examples, personas and style, output validation with a zero-shot classifier, and the effect of temperature and top-p. |
| [04_rag_retrieval.ipynb](04_rag_retrieval.ipynb) | The retrieval half of RAG: embed web pages, store them in a Pinecone index and query them. |
| [04_rag_generate.ipynb](04_rag_generate.ipynb) | The generation half of RAG: a `RagBot` that answers from retrieved context, cost tracking in Supabase, and swapping in Llama-3 or Command-R as the generator. |
| [04_agent.ipynb](04_agent.ipynb) | An agent that picks tools (Python REPL, Google search, Pinecone lookup, stock balance, Stable Diffusion) to answer questions. |

## Setup

```bash
python3 -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
```

Set the API keys the notebooks you run need:

| Variable | Used for |
|---|---|
| `OPENAI_API_KEY` | all notebooks |
| `PINECONE_API_KEY` | 02, 04 |
| `COHERE_API_KEY` | 03 |
| `SUPABASE_URL`, `SUPABASE_KEY` | 04 (cost tracking) |
| `SERP_API_KEY` | 04_agent (Google search) |
| `PAPER_ALPACA_API_KEY`, `PAPER_ALPACA_API_SECRET` | 04_agent (stock balance, paper trading) |
| `HF_ENDPOINT_URL`, `HF_TOKEN` | 04_rag_generate (Llama-3 endpoint) |

Some cells need extras beyond `requirements.txt`: a GPU for Stable Diffusion and Command-R, and `pip install` lines inside the notebooks for packages like `diffusers` and `alpaca-trade-api`.
