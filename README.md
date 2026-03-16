## Simple RAG Demo with Local Models

This repo contains a minimal **Retrieval-Augmented Generation (RAG)** demo built in a single Jupyter notebook.

We use:
- **`my_knowledge.txt`**: a tiny “Company Policy Manual” text file
- **`main.ipynb`**: an end‑to‑end RAG pipeline:
  - Chunk the text with LangChain's `RecursiveCharacterTextSplitter`
  - Embed chunks using `sentence-transformers` (`all-MiniLM-L6-v2`)
  - Index embeddings with **FAISS** for similarity search
  - Answer questions with **`google/flan-t5-base`** via `transformers`

---

## Getting started

1. **Create and activate an environment** (example using `conda`):

```bash
conda create -n rag-demo python=3.10 -y
conda activate rag-demo
```

2. **Install dependencies** (you can also just run the first cell in the notebook):

```bash
pip install transformers sentence-transformers faiss-cpu langchain
```

3. **Open the notebook**:

```bash
jupyter notebook main.ipynb
```

Run the cells from top to bottom to:
- Inspect how the text is chunked
- See the embeddings and FAISS index
- Ask questions like _“What is the WFH policy?”_ or _“What is the company's dental plan?”_

---

## Files

- `main.ipynb` – RAG demo notebook with explanations in markdown cells
- `my_knowledge.txt` – example knowledge base used by the notebook

---

## Customizing

- **Replace the knowledge base**: edit `my_knowledge.txt` or point the notebook to your own `.txt` file.
- **Change the model**: swap `google/flan-t5-base` for another encoder–decoder model supported by `transformers`.
- **Tweak retrieval**: adjust chunk sizes, overlaps, and the number of retrieved neighbours `k` in the FAISS search.

This makes a lightweight, self-contained example you can extend into a proper RAG service or API.

