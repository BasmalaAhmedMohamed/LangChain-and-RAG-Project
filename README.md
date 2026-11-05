# Generative AI Project

This project is a Jupyter notebook exploring practical LangChain and retrieval-augmented generation (RAG) patterns. The notebook uses OpenAI chat and embedding models and a small local text document as its knowledge base.

## Project files

- `project.ipynb` — notebook with five exercises.
- `Doc.txt` — source text loaded by the RAG and retrieval exercises.
- `.env.example` — template for the required OpenAI configuration.

## Notebook exercises

1. **Structured profile generation** — extract a person's name, age, email, and country into a validated Pydantic model.
2. **Streaming and batch calls** — stream a response and request country capitals in a batch.
3. **Mini RAG Q&A** — split `Doc.txt`, index its chunks in FAISS, retrieve relevant context, and answer questions from that context.
4. **Retriever comparison** — compare similarity, maximal marginal relevance (MMR), and a BM25/dense ensemble retriever.
5. **Tool-using assistant** — let an agent call tools for the current timestamp, word counting, and knowledge-base search.

## Requirements

- Python 3.12 or later (the notebook uses Python 3.12-style f-strings).
- Jupyter Notebook or JupyterLab.
- An OpenAI API key with access to the chat and embedding models you configure.

Install the notebook's Python dependencies:

```bash
python -m pip install jupyter python-dotenv pydantic "pydantic[email]" langchain langchain-classic langchain-community langchain-core langchain-openai langchain-text-splitters faiss-cpu rank-bm25
```

## Configuration

Copy `.env.example` to `.env`, then fill in the values. 

```dotenv
openai_key=your_openai_api_key
openai_model=your_chat_model_name
openai_embedding_model=your_embedding_model_name
```

The notebook calls `load_dotenv()` and reads these exact variable names. Choose model names available to your OpenAI account.

## Run

From the project directory, start Jupyter:

```bash
jupyter notebook Ass_4.ipynb
```

Run the cells from top to bottom. The RAG and retriever exercises expect `Doc.txt` to remain in the project directory. The last exercise's time tool returns a Unix timestamp; it does not format the timestamp as a local clock time.
