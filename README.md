# Benchmarking Open-Source Components for Retrieval-Augmented Generation (RAG)

This repository provides a standardized RAG pipeline for benchmarking open-source components. It covers document chunking, embedding generation, vector store ingestion, and evaluation of dense retrievers paired with generative models.

Repository contents

- english_dataset: English source documents used for experiments.
- german_dataset: German source documents used for experiments.
- multi_document_RAG: Multi-document RAG notebooks
	- [Chroma_RAGAS_Multidocument_RAG_With_Generation.ipynb](multi_document_RAG/Chroma_RAGAS_Multidocument_RAG_With_Generation.ipynb)
	- [FAISS_RAGAS_Multidocument_RAG_With_Generation.ipynb](multi_document_RAG/FAISS_RAGAS_Multidocument_RAG_With_Generation.ipynb)
- single_document_RAG: Single-document RAG example
	- [single_document_rag.ipynb](single_document_RAG/single_document_rag.ipynb)
- web_scraper: Scraping notebooks for building datasets
	- [generalised_webpage_scraper.ipynb](web_scraper/generalised_webpage_scraper.ipynb)
	- [web_scraper_for_xml_file.ipynb](web_scraper/web_scraper_for_xml_file.ipynb)
- evaluation_q&a_dataset: Q&A evaluation datasets
	- [raga_eval_dataset_english.json](evaluation_q&a_dataset/raga_eval_dataset_english.json)
	- [raga_eval_dataset_deutsch.json](evaluation_q&a_dataset/raga_eval_dataset_deutsch.json)
- results: CSV outputs from previous runs

Quick start

1. Create and activate a Python environment (recommended Python 3.10+). Example with `venv`:

	 python3 -m venv .venv
	 source .venv/bin/activate

2. Install dependencies:

	 pip install -r requirements.txt

3. Start Jupyter and open the notebook you want to run:

	 pip install "jupyterlab"
	 jupyter lab

4. Put your documents into `english_dataset/` or `german_dataset/` and run the cells in the preprocessing and RAG notebooks.

Notes and recommendations

- The notebooks expect you to configure any API keys or model endpoints inside the notebook cells or via environment variables.
- Use the `multi_document_RAG` notebooks to compare different vector stores (Chroma, FAISS) and retrieval strategies.
- Evaluation datasets are in `evaluation_q&a_dataset/` and can be used to reproduce the reported metrics.

Dependencies

- See `requirements.txt` for the main Python packages used in the project. Install with:

	pip install -r requirements.txt

