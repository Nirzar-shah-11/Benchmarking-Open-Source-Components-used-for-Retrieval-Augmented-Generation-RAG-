
# 📊 Benchmarking Open-Source Components for Retrieval-Augmented Generation (RAG)

This repository presents a comprehensive benchmarking study of **open-source components used in Retrieval-Augmented Generation (RAG)** systems.  
The project evaluates **retrieval quality, generation quality, and efficiency trade-offs** across different embeddings, vector databases, and LLMs using **English and German datasets**.

---

## 🧠 Project Motivation

Retrieval-Augmented Generation (RAG) is a key technique to ground Large Language Models (LLMs) in external knowledge.  
However, design choices such as **embedding models**, **vector stores**, and **LLMs** significantly affect:

- Retrieval accuracy
- Hallucination rate
- Latency
- Multilingual robustness

This repository provides a **reproducible benchmarking framework** to analyze these trade-offs in a systematic way.

---

## 📁 Repository Structure

```
Benchmarking-Open-Source-Components-used-for-RAG/
├── README.md              # Project overview & methodology
├── RESULTS.md             # Detailed benchmark results & analysis
├── english_dataset/
├── german_dataset/
├── single_document_RAG/
├── multi_document_RAG/
├── evaluation_q&a_dataset/
├── web_scraper/
├── results/               # CSV files with raw metrics
├── requirements.txt
```

📊 **Detailed experimental results and plots are documented in [RESULTS.md](RESULTS.md).**

---

## 📊 Evaluation Metrics

### 🔍 Retrieval Metrics
- **Semantic MRR**
- **Context Recall**
- **Context Precision**

These metrics evaluate retrieval ranking quality and coverage (Recall@k-style evaluation).

---

### ✍️ Generation Metrics
- **Faithfulness** – Measures hallucination resistance
- **Semantic Similarity** – Measures answer alignment with reference responses

---

### 🧠 RAGAS-Style Metrics
- Faithfulness
- Context Precision
- Context Recall
- Semantic MRR

All metrics are normalized to **[0, 1]** (higher is better).

---

## ⏱️ Efficiency Metrics
- Retrieval Time (seconds)
- Generation Time (seconds)

Used to analyze **quality vs latency trade-offs**.

---

## 🧪 Experimental Setup (Summary)

- **Embeddings:** MiniLM, Paraphrase, DistilUSE, E5-Large  
- **Vector Stores:** FAISS, ChromaDB  
- **LLMs:** LLaMA-3.1-8B, Ministral, DeepSeek  
- **Datasets:** English & German  

---

## 🏆 Key Takeaways

✔ **Best Overall Quality:** E5-Large + ChromaDB  
✔ **Best Latency-Optimized Pipeline:** MiniLM + FAISS  
✔ **Best Multilingual Embedding:** E5-Large  
✔ **Best Production Trade-off:** MiniLM + FAISS  

Full quantitative analysis, plots, and discussions are available in **[RESULTS.md](RESULTS.md)**.

---



---

## 🚀 Quick Start

Create and activate a Python environment (recommended **Python 3.10+**).

Example using `venv`:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### Install dependencies

```bash
pip install -r requirements.txt
```

### Start Jupyter Lab

```bash
pip install jupyterlab
jupyter lab
```

Open the notebook you want to run from:
- `single_document_RAG/`
- `multi_document_RAG/`

### Prepare datasets

- Place your documents into:
  - `english_dataset/` or
  - `german_dataset/`
- Run the preprocessing cells first, followed by the RAG pipeline cells in the notebooks.

---

## 📝 Notes & Recommendations

- Configure **API keys or model endpoints** inside notebook cells or via environment variables.
- Use **multi_document_RAG** notebooks to compare:
  - Vector stores (FAISS vs ChromaDB)
  - Retrieval strategies
- Evaluation datasets are available in `evaluation_q&a_dataset/` and can be used to **reproduce reported metrics**.
- For detailed quantitative analysis and plots, see **[RESULTS.md](RESULTS.md)**.

---

## 📦 Dependencies

Main Python dependencies are listed in `requirements.txt`.

Install them using:

```bash
pip install -r requirements.txt
```

## 🔁 Reproducibility

- All raw numerical results are stored in `/results` as CSV files.
- Plots are generated using Matplotlib.
- Experiments are fully reproducible using the provided notebooks.

---


**Author:** Nirzar Shah  
**Domain:** AI · NLP · Retrieval-Augmented Generation
