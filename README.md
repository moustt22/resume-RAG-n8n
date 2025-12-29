# Resume RAG Chatbot (n8n + Lovable)

A multi-user Resume chatbot using Retrieval-Augmented Generation (RAG).
Users upload a PDF resume and ask natural language questions.
Session-based vector isolation prevents document mixing.

## Features
- PDF resume upload
- Semantic search with embeddings
- Per-session vector namespaces
- Multi-user safe
- No data leakage

## Tech Stack
- Frontend: Lovable
- Backend: n8n
- Vector DB: Pinecone
- LLM: OpenRouter / OpenAI
- Embeddings: OpenAI-compatible

## Architecture
1. Lovable generates a session_id
2. PDF is uploaded to n8n
3. Resume is chunked and embedded
4. Chunks stored in Pinecone namespace per session
5. Queries retrieve only session-specific data

## Setup
1. Import workflow from `/n8n`
2. Create Pinecone index (1536 dimensions)
3. Copy `env.example` → `.env`
4. Add your API keys
5. Deploy frontend using Lovable

## Demo
https://chatwithyourresume.lovable.app

## Notes
Each session uses its own vector namespace to ensure isolation.
