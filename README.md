# Module 5 — Hybrid Embedding Databases  
**Author:** Di Han  
**Email:** dihan9728@gmail.com  

---

## 📌 Description — What This Homework Is About
This homework implements a Hybrid Retrieval system that combines:

- **Semantic Vector Search (FAISS + embeddings)**
- **Keyword-based Search (BM25-like inverted index)**
- **A hybrid retrieval strategy mixing both results with adjustable alpha**

The goal is to optimize academic paper retrieval performance using various embedding, indexing, and hybrid scoring techniques.  
This notebook completes all required components:

### ✔ Part 1 — Embedding Database Construction  
- Uses `SentenceTransformer('all-MiniLM-L6-v2')`  
- Generates embeddings for all 1029 text chunks  
- Saves embeddings to `embeddings_text3_small.npy`  
- Builds and saves FAISS index (`faiss_index_text3_small.bin`)  
- Builds SQLite database `rag_hybrid.db` containing:
  - `papers` table  
  - `chunks` table  
  - `bm25_inverted` table  

### ✔ Part 2 — Implement Keyword (BM25-like) Search  
- Tokenization  
- Term frequency (TF)  
- Inverse document frequency (IDF)  
- Weighted BM25 scoring  
- SQL-based inverted index querying

### ✔ Part 3 — Implement Hybrid Search  
Formula:  
`hybrid_score = alpha * vector_score + (1 - alpha) * bm25_score`

- Supports configurable `alpha ∈ {0.3, 0.5, 0.7}`  
- Returns ranked chunk results

### ✔ Part 4 — Evaluation  
- Evaluates:
  - Vector-only search
  - Hybrid search (different alphas)
- Reports hit-rate@5 for 5 test queries  
- All versions reach **1.00 (5/5)** accuracy

---
## 👤 Primary Reviewer: ScottLL
---


## 📂 Project Structure

```
cs_module5_hybrid/
│
├── module5_hybrid.ipynb       → Week 5 full code
│   ├── Embedding generation (SentenceTransformers)
│   ├── FAISS vector search
│   ├── BM25 inverted index
│   ├── Hybrid search
│   └── Evaluation
│
├── README.md                  → Description, usage, reviewer info
│
└── data_cscl/
    ├── chunks.json            → Week 4 text chunks
    └── embeddings_text3_small.npy
                                → Generated embeddings for FAISS search
```




---
## 📝 Questions
_No additional questions for this homework._

---

## ✅ Submission Notes
- All required outputs (embeddings, FAISS index, SQLite DB) are included.  
- Results are reproducible directly by running the notebook.  

- Evaluation matches expected accuracy from the Week 5 instructions.
