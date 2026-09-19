📌 Project Overview
This project implements a complete end-to-end RAG ecosystem divided into two core pipelines:

Knowledge Ingestion Pipeline: Ingests document datasets (e.g., PDF files like master-food-recipe.pdf), chunks and extracts text using a Default Data Loader, embeds content using OpenAI models, and stores vectors into a Pinecone vector database.

Conversational RAG AI Agent: A chat agent powered by Google Gemini, backed by Simple Memory for context retention, and integrated with Pinecone Vector Store as a tool to deliver accurate, context-aware responses.

  **🛠️ System Architecture & Workflow**
  
**1. Document Ingestion Workflow**
When a document (e.g., PDF) is submitted via form trigger:
**Trigger**: Form submission event.
**Data Processing**: Default Data Loader parses and chunks document text.
**Vector Embedding**: text-embedding-3-small / OpenAI Embeddings converts text into numerical vector representations.
**Vector Indexing**: High-dimensional vectors are stored in Pinecone under the target index (master-food-recipie).

2. RAG Query & Chat Execution Workflow
When a chat message is received from a user:
**Trigger**: Chat trigger input.
**Orchestration**: AI Agent queries the Pinecone Vector Store to retrieve top matching contexts.
**Memory Management**: Simple Memory maintains active session context across multi-turn user queries.
**LLM Synthesis**: Google Gemini receives the user query + retrieved context chunks + conversational history to generate accurate answers.

📊 Live Demonstration & Proof of Execution
Vector Index (Pinecone Dashboard)
Processed documents stored as indexed vector embeddings with metadata references (such as PDF source, character lines, and creation details).

**In-Context Recipe Query Test**
Querying the agent regarding content indexed strictly inside master-food-recipe.pdf:

**Grounded Retrieval & Answer Generation**
The RAG agent successfully fetches context from Pinecone and synthesizes structured output containing exact ingredient amounts and step-by-step preparation rules:

<img width="1489" height="713" alt="image" src="https://github.com/user-attachments/assets/06414eaf-f91e-4f49-821c-448590cb36ff" />

<img width="1525" height="715" alt="image" src="https://github.com/user-attachments/assets/3be47af7-6961-48c1-94a3-7fda9af9a235" />

<img width="1594" height="774" alt="image" src="https://github.com/user-attachments/assets/9150ea26-14e2-4955-888a-49aaa8490452" />

<img width="505" height="680" alt="image" src="https://github.com/user-attachments/assets/2cfbae47-0cf9-4d12-a23e-c6ec0f88cbff" />

<img width="509" height="686" alt="image" src="https://github.com/user-attachments/assets/45a02c5c-582f-47c0-ba38-d21ea4b0a9af" />




