# PDF Assistant Application

A Python application that creates an AI assistant using Agentic RAG capable of reading, understanding, and answering questions about PDF documents. This implementation specifically uses a Thai recipes PDF as an example, but can be adapted for other PDF documents.

## Features

* PDF document processing and knowledge base creation
* Vector database storage using pgvector2
* Persistent chat history and assistant state using PostgreSQL
* Interactive CLI interface with markdown support
* Support for multiple user sessions and run IDs

## Prerequisites

* Python 3.7+
* PostgreSQL database with pgvector extension
* Groq API key

## Installation

1. Clone the repository.

2. Install the required dependencies using requirements.txt file.

3. Set up your environment variables in .evn file.

4. Set up PostgreSQL database:
   * Ensure PostgreSQL is running with pgvector extension
   * Create a database and user with appropriate permissions
   * Update the `db_url` in the code if needed

## Usage

Run the application:
```bash
python pdf_assistant.py
```

## How It Works

1. The application initializes a PDF knowledge base using the specified URL(s)
2. Vector embeddings are created and stored in PostgreSQL using pgvector2
3. Chat history and assistant state are persisted in PostgreSQL
4. Users can interact with the assistant through a CLI interface
5. The assistant can reference previous conversations and maintain context

## Database Schema

The application uses two main database components:
* Vector storage for document embeddings (pgvector2)
* Assistant storage for chat history and state

## Configuration

Key configuration points:
* Database URL: `postgresql+psycopg://ai:ai@localhost:5532/ai`
* PDF Source: `https://phi-public.s3.amazonaws.com/recipes/ThaiRecipes.pdf`
