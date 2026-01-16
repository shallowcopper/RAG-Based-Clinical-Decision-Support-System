# RAG-Based Clinical Decision Support System

## 📌 Project Overview
This project addresses the challenge of information overload in healthcare by developing a **Retrieval-Augmented Generation (RAG)** system. It allows healthcare professionals to query a vast knowledge base (the **Merck Manuals**) using natural language and receive accurate, grounded medical protocols, diagnostic assistance, and treatment plans.

The system leverages **Mistral-7B** for generation and **ChromaDB** for vector storage, ensuring that answers are derived strictly from trusted medical texts rather than model hallucinations.

## 🚀 Features
* **Medical QA:** Answers questions on diagnostics, drug information, treatment plans, and critical care protocols.
* **RAG Pipeline:** Combines vector search with generative AI to retrieve relevant medical context before answering.
* **Groundedness Check:** Implements an "LLM-as-a-judge" evaluation step where the model self-evaluates if its answer is fully supported by the retrieved context.
* **Quantized Inference:** Uses `llama-cpp-python` to run the Mistral-7B model efficiently on local GPUs (e.g., T4).

## 🛠️ Technologies Used
* **LLM:** `TheBloke/Mistral-7B-Instruct-v0.2-GGUF` (Quantized).
* **Embeddings:** `all-MiniLM-L6-v2` via HuggingFace.
* **Vector Database:** ChromaDB.
* **Orchestration:** LangChain.
* **PDF Processing:** PyMuPDF (`pymupdf`) for high-fidelity text extraction.
* **Environment:** Python 3.10+, Jupyter Notebook/Google Colab.

## 📊 Evaluation
The project includes an automated evaluation step using the **LLM-as-a-judge** method. The model evaluates its own responses based on two metrics:
1.  **Groundedness:** Is the answer fully supported by the provided context?
2.  **Relevance:** Does the answer directly address the user's question?

## 🔮 Future Improvements
* **Web Interface:** Deploying the backend via Streamlit or Flask for a user-friendly chat interface.
* **Hybrid Search:** Implementing a re-ranker to combine keyword and semantic search for higher accuracy.
* **Multimodal Capabilities:** Integrating vision models to interpret medical imaging alongside text protocols.
