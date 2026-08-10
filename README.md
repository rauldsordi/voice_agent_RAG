# Voice Agent + RAG (n8n)

A voice-enabled AI agent built with n8n that answers questions using Retrieval-Augmented Generation (RAG) instead of relying solely on the base model's training data.

## Overview

This workflow lets a user speak a question, which is transcribed, converted into an embedding, and matched against a custom knowledge base stored in a vector database. The most relevant context is retrieved and passed to the LLM, which generates a grounded, accurate response.

## 🧩 How it works

1. **Voice input** — the user's spoken question is captured and transcribed to text.
2. **Embedding generation** — the transcribed text is converted into a vector using the Gemini embedding model.
3. **Vector search** — the vector is queried against a Supabase Vector Store to retrieve the most semantically similar chunks from the knowledge base.
4. **Context-aware response** — the retrieved context is passed along with the question to Gemini, which generates an answer grounded in the retrieved data.
5. **Voice/text output** — the response is returned to the user.

## 📸 Demo


## 🛠️ Tech stack

- **n8n** — workflow orchestration
- **Gemini API** — embeddings + text generation
- **Supabase Vector Store** — vector storage and similarity search
- **Speech-to-text** (transcription) for voice input

## 📦 Setup

1. Import the workflow JSON into your n8n instance.
2. Configure credentials:
   - Gemini API key
   - Supabase project URL and service key
3. Create a Supabase table with `pgvector` enabled to store embeddings.
4. Load your knowledge base documents into the vector store (chunk → embed → insert).
5. Activate the workflow and connect your voice input trigger.

## 📄 License

MIT
