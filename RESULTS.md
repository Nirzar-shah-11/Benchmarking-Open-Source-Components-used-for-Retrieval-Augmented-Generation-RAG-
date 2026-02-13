
# 📊 Experimental Results – RAG Benchmarking

This document presents the **detailed experimental results and observations** for benchmarking open-source components used in **Retrieval-Augmented Generation (RAG)** systems.  
The results are based on experiments conducted across **English and German datasets**, multiple **embedding models**, **vector databases**, and **LLMs**.

---

## 🧪 Experimental Setup

- **Embeddings:** MiniLM, Paraphrase, DistilUSE, E5-Large  
- **Vector Stores:** FAISS, ChromaDB  
- **LLMs:** LLaMA-3.1-8B, Ministral, DeepSeek  
- **Datasets:** English & German  
- **Metrics:** Faithfulness, Semantic Similarity, Semantic MRR, Context Recall, Context Precision, Retrieval Time, Generation Time  

---

## 📈 Generation Time Analysis

### German Dataset
- FAISS consistently shows **lower generation time** than ChromaDB.
- E5-Large yields the **highest latency** but strongest semantic performance.
- Ministral is slower than LLaMA across most embeddings.

**Observation:**  
FAISS is better suited for **low-latency multilingual RAG pipelines**.

---

### English Dataset
- DeepSeek-based pipelines incur **very high generation time**.
- MiniLM and Paraphrase embeddings offer faster responses.
- ChromaDB adds noticeable overhead compared to FAISS.

---

## ✍️ Faithfulness Results

### English Dataset
- **E5-Large achieves the highest faithfulness** (up to ~0.92).
- ChromaDB provides more consistent grounding.
- DistilUSE underperforms across most setups.

### German Dataset
- Faithfulness scores drop compared to English.
- FAISS + LLaMA performs best with DistilUSE.
- ChromaDB shows stability but lower peak scores.

**Key Insight:**  
Larger embeddings improve hallucination resistance, especially in multilingual settings.

---

## 🔍 Semantic Similarity Analysis

### English Dataset
- E5-Large consistently achieves **semantic similarity > 0.85**.
- MiniLM provides a good balance between speed and semantic quality.
- DistilUSE performs weakest.

### German Dataset
- Smaller embeddings struggle with semantic alignment.
- E5-Large remains robust across languages.

---

## ⚖️ Trade-off Analysis

### Semantic Quality vs Generation Time
- FAISS enables faster generation with slight quality loss.
- ChromaDB improves semantic scores at the cost of latency.

### Semantic MRR vs Retrieval Time
- E5-Large achieves the **highest MRR** but slowest retrieval.
- MiniLM provides the **best speed–quality trade-off**.

---

## 🧠 RAGAS-Style Radar Analysis

Radar plots evaluate:
- Context Precision
- Context Recall
- Semantic MRR

**Results:**
- E5-Large dominates across all dimensions.
- MiniLM remains balanced.
- DistilUSE consistently underperforms.

---

## 🏆 Summary of Findings

| Objective | Best Choice |
|---------|------------|
| Best Overall Quality | E5-Large + ChromaDB |
| Lowest Latency | MiniLM + FAISS |
| Multilingual Robustness | E5-Large |
| Production Deployment | MiniLM + FAISS |
| Research Benchmarking | E5-Large + ChromaDB |

---

## 📌 Notes

- All plots are generated using Matplotlib.
- Raw numerical results are stored in `/results` as CSV files.
- Experiments are fully reproducible via provided notebooks.

---

**Author:** Nirzar Shah  
**Domain:** AI · NLP · Retrieval-Augmented Generation
