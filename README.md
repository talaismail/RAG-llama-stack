# RAG with Llama Stack on OpenShift AI
This repository provides an example of how to build a Retrieval-Augmented Generation (RAG) pipeline using Llama Stack on OpenShift AI. It walks through how to deploy, connect, and use Llama models (inference + embeddings), integrate vector storage, and perform end-to-end RAG inside a Jupyter Notebook.

---
## What This Project Covers
This repo demonstrates how to:
- Deploy and use Llama models via Model-as-a-Service (MaaS) on OpenShift AI
- Use the Llama Stack client to send inference and embedding requests
- Generate embeddings from documents and store them in a vector database (e.g., Milvus or VectorDB)
- Build a minimal RAG pipeline:
   - Ingest documents
   - Generate embeddings
   - Query vector store
   - Use relevant chunks to ground LLM responses
- Run the entire workflow inside a Jupyter Notebook (rag.ipynb)

## What is RAG?
Retrieval-Augmented Generation (RAG) improves LLM answers by grounding them in external, domain-specific knowledge.
Instead of the model answering from pure parametric memory, it retrieves relevant documents and uses them as context.
In this repo your RAG flow looks like this:
- Document ingestion → convert raw text/PDF into chunks
- Embedding generation → represent each chunk as a vector
- Vector search → retrieve the top-k similar chunks for a user query
- Llama inference → generate an answer grounded in retrieved knowledge

## What is Llama Stack?
Llama Stack is the official Meta framework that provides:
- A unified client API
- Easy access to Llama models (inference + embeddings)
- Built-in capabilities for RAG and vector search
- Model-as-a-Service integrations
- Support for on-prem or cloud deployments
In OpenShift AI, the Llama Stack client communicates with a deployed Llama MaaS endpoint.

## What is OpenShift AI?

OpenShift AI (RHOAI) provides a secure, scalable environment for:
- Managing data science projects
- Deploying notebooks
- Hosting models via MaaS
- Integrating storage, networking, and GPUs
- Running end-to-end AI workloads in enterprise environments

Here we use OpenShift AI to run:
- The Jupyter Notebook
- The Llama model endpoint
- Optional vector database components
- The entire RAG pipeline
