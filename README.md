


# Document-QA using LLAMA-3.1.70B - RAG - ChromaDB

## Overview

This project implements a Retrieval-Augmented Generation (RAG) system utilizing Meta's LLAMA 3.1 70B model, integrated with ChromaDB as the vector store and LangChain for building a document-based question-answering system. The LLAMA 3.1 model is loaded with Groq, demonstrating the use of the `Chroma` library for creating a document database. The system leverages LLAMA language models for efficient document retrieval and QA, employing HuggingFace embeddings and Groq models for enhanced data processing and querying.

## Features

- **Document Database Creation**: Uses `Chroma` to store and manage documents.
- **Embedding Generation**: Converts documents into vector representations using HuggingFace embeddings.
- **Vector Database**: Builds a vector database for efficient similarity-based retrieval.
- **RetrievalQA Chain**: Implements a QA system using the LLAMA language model to answer queries based on document content.

## Project Structure

- **Load Data and Create Database**: Loads textual data, generates embeddings, and sets up the document database.
- **Query Processing**: Processes user queries using a retrieval-based approach to fetch relevant information from the document database.
- **Model Integration**: Integrates the LLAMA language model to provide accurate answers to user queries.

## How It Works

1. **Embeddings Creation**:
   - The project begins by generating embeddings for the input documents using the `HuggingFaceEmbeddings` class. These embeddings convert textual data into numerical vectors suitable for vector operations.

2. **Persisting Data**:
   - Creates a directory named `doc_db` to store vectorized documents. This directory ensures that embeddings and documents are saved and can be reused without recalculating embeddings.

3. **Vector Database Setup**:
   - Utilizes the `Chroma` library to create a vector database from the document embeddings. This database supports efficient similarity searches and retrieval operations.

4. **Retriever Setup**:
   - Initializes a retriever from the vector database to fetch relevant documents based on the similarity of query embeddings.

5. **LLAMA Model Integration**:
   - Integrates the LLAMA language model, specifically the `ChatGroq` implementation. Configures the model with `llama-3.1-70b-versatile` and a temperature setting of `0` for deterministic responses.

6. **QA Chain Creation**:
   - Constructs a QA chain using the `RetrievalQA` class. This chain combines the retriever and language model to process user queries and return answers along with the source documents.

7. **Query Execution**:
   - Invokes the QA chain with sample queries. The response includes the answer generated by the LLAMA model and the source document from which the information was retrieved.

## Getting Started

To set up and run the project, follow these steps:

1. **Clone this Repository**:
   ```bash
   git clone https://github.com/Ramnarayan-Choudhary/RAG_QNA.git
