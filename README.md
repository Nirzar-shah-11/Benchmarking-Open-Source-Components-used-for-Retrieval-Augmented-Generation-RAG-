# Benchmarking Open-Source Components for Retrieval-Augmented Generation (RAG)

A standardized RAG pipeline for benchmarking open-source components. The project divides documents into chunks, converts them into embeddings, uploads them to a vector store, and evaluates dense retrievers together with a generative model to ensure fair comparison.

**Repository structure**

- **english_dataset**: (dataset folder) English source documents used for experiments.
- **german_dataset**: (dataset folder) German source documents used for experiments.
- **multi_document_RAG**: Notebooks implementing multi-document RAG pipelines and generation examples:
	- [Chroma_RAGAS_Multidocument_RAG_With_Generation.ipynb](multi_document_RAG/Chroma_RAGAS_Multidocument_RAG_With_Generation.ipynb)
	- [FAISS_RAGAS_Multidocument_RAG_With_Generation.ipynb](multi_document_RAG/FAISS_RAGAS_Multidocument_RAG_With_Generation.ipynb)
- **single_document_RAG**: Single-document RAG example:
	- [single_document_rag.ipynb](single_document_RAG/single_document_rag.ipynb)
- **web_scraper**: Notebooks for scraping webpages and XML sources to build datasets:
	- [generalised_webpage_scraper.ipynb](web_scraper/generalised_webpage_scraper.ipynb)
	- [web_scraper_for_xml_file.ipynb](web_scraper/web_scraper_for_xml_file.ipynb)

- **evaluation_q&a_dataset**: Q&A evaluation datasets used to benchmark retrieval + generation. Files:
	- [raga_eval_dataset_english.json](evaluation_q&a_dataset/raga_eval_dataset_english.json)
	- [raga_eval_dataset_deutsch.json](evaluation_q&a_dataset/raga_eval_dataset_deutsch.json)

**Quick start**

1. Open the relevant notebook in JupyterLab / Jupyter Notebook / Colab.
2. Ensure required Python packages are installed (install per-notebook or add a `requirements.txt` if needed).
3. Place your documents in `english_dataset` or `german_dataset` and run the preprocessing/crafting cells in the notebook.

If you want, I can add a `requirements.txt` or brief run instructions per-notebook next.

**Dependencies**

- A `requirements.txt` is included for common Python dependencies; install with `pip install -r requirements.txt`.
