EcoGraph-RAG: AI Climate Intelligence Agent 🌍📄 

Project OverviewThis project implements an advanced Graph-Augmented Retrieval (GraphRAG) system designed to extract structured climate intelligence from multi-format data (PDF reports and CSV metrics). The goal is to answer complex, multi-hop policy questions that standard vector search alone cannot handle.This project demonstrates expertise in Generative AI (GenAI), advanced retrieval techniques, data governance, and containerized MLOps deployment.

🧠 Architecture Highlights

The pipeline integrates three distinct technologies to achieve high accuracy and complex reasoning:
1) Semantic Retrieval (Vectors): Uses vector similarity (embeddings) to find relevant text snippets from the documents.
2) Structural Retrieval (GraphRAG): Uses graph traversal to find explicit relationships between entities (e.g., Policy $\rightarrow$ Emission Value $\rightarrow$ Country).
3) Fusion: The LLM combines the semantic text and the structural path for a grounded, traceable answer.

🛠️ Technical Stack

Component,Tool / Model,Rationale / Skill Demonstrated
Framework (Orchestration),LangChain (Python),"Connects all data loaders, vector stores, and the LLM via defined components."
LLM Generator,Ollama (Llama 3 / Gemma),"Cost Management: Local inference eliminates API costs, ensuring fast development and cost-effective deployment."
Embeddings,HuggingFace / Ollama (Local),"Zero-cost vector creation, supporting high-quality semantic search."
Vector Store (Indexing),ChromaDB,"Lightweight, file-based storage for fast semantic indexing."
Graph Database (Structural),NetworkX (Logic) → Neo4j (Planned Deployment),Demonstrates GraphRAG capability for multi-hop reasoning.
Deployment (MLOps),FastAPI & Docker,Creates a production-ready API wrapper with environment parity.


✅ Implementation Status: Week 1 & 2 Complete

Phase,Output Achieved,Key Takeaways & Skills
1. Data Ingestion,"Documents loaded (PyPDFLoader, CSVLoader) and combined.",Mastery of multi-format data handling and ingestion pipelines.
2. Data Cleaning,"48k-row CSV cleaned for sparsity (e.g., co2, gdp).",Implemented Grouped Median Imputation (by Country) and fixed the SettingWithCopyWarning bug.
3. Graph Construction,"NetworkX Graph (G) built with Nodes (COUNTRY, YEAR, METRIC) and Edges (SHOWS_EMISSIONS).",Successfully used Ollama/Gemma and Structured Prompting to execute complex Entity/Relationship extraction.
4. Graph Traversal,Multi-Hop Query logic proven.,"Demonstrated ability to query relationships (e.g., finding nodes 2 steps away) — the core advantage of GraphRAG."


🛣️ Week 3: Finalizing for Production

The focus now shifts entirely to deployment and making the project reusable and fully scalable.

1. Advanced MLOps & Persistence
Dockerization: Write the Dockerfile and docker-compose.yml to package the entire RAG pipeline (Python code + Ollama model access + FastAPI) into a deployable image.

API Finalization: Wrap the GraphRAG logic into a stable FastAPI service.

Neo4j Integration: Define the steps to migrate the NetworkX graph to a persistent Neo4j database instance running in a Docker container (using the neo4j-admin import tool).

2. Full Project Deployment
Demonstrate that the Docker image can be run anywhere and serve queries, proving environment parity (the "Works on my machine" problem is solved).

