# RAG Assignment 2

This repository contains the implementation and evaluation of **Retrieval-Augmented Generation (RAG)** systems as part of Assignment 2. The project demonstrates the evolution from a naive baseline pipeline to an enhanced production-style system with reranking and query rewriting.

---

## Project Structure

```
naive_rag.ipynb          # Baseline RAG implementation (MiniLM, top-1 retrieval)
enhanced_rag.ipynb       # Enhanced RAG (larger embeddings, top-k, rerank, rewrite)
requirements.txt         # Dependencies with versions for reproducibility
results_grid.csv         # Evaluation results (EM/F1/latency across configs)
results_grids_ragas.csv  # RAGAS evaluation metrics
README.md                # This file
Documents.docx           # Written reports (Architecture Document + Technical Report)
```

---

## Setup Instructions

1. Clone the repository or download the files.
2. Create a Python environment (Python 3.10 recommended).

   ```bash
   python -m venv rag_env
   source rag_env/bin/activate   # On Windows: rag_env\Scripts\activate
   ```
3. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

---

## Running the Notebooks

* **Naive RAG:**
  Open and run `naive_rag.ipynb`. This notebook demonstrates the minimal baseline system with MiniLM embeddings, top-1 retrieval, and Flan-T5-base for generation.

* **Enhanced RAG:**
  Open and run `enhanced_rag.ipynb`. This notebook includes multiple configurations:

  * Embedding size: 384-d vs 768-d
  * Retrieval depth: top-1, top-3, top-5
  * Variants: baseline, rewrite, rerank

Results are automatically logged into CSV files for reproducibility.

---

## Evaluation

* **Lexical Metrics:** Exact Match (EM) and F1 are reported for each configuration in `results_grid.csv`.
* **Semantic Metrics:** RAGAS metrics (faithfulness, context precision/recall, answer relevance) are recorded in `results_grids_ragas.csv`.

Best configuration: **384-d embeddings + rerank**, achieving **F1 = 73.9**.

---

## Reproducibility

* All dependencies are pinned in `requirements.txt`.
* Notebooks are self-contained and can be rerun without external changes.
* Results CSVs allow verification of reported metrics.

---

## Reports

* **Architecture Document** and **Technical Report** are included in `Documents.pdf`.
* These reports describe system design, experiments, evaluation, limitations, and future work.
