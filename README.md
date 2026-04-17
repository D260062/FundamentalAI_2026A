# CourseMate AI – Course Materials Finder Assistant (RAG)

## 1) Overview
CourseMate AI helps students find the right course materials (lecture slides, notes, assignment briefs) in seconds.
Users upload PDFs and ask questions in natural language. The system uses Retrieval-Augmented Generation (RAG) to produce answers grounded in the uploaded documents with citations.

## 2) Problem Statement
Course materials are often scattered across LMS, drives, chats, and multiple PDF files. Students waste time searching and may miss important requirements (deadlines, rubrics, submission rules). A document-grounded AI assistant can improve clarity and reduce mistakes.

## 3) Target Users
- Students (primary)
- Tutors/Lecturers (secondary)
- Course administrators (optional)

## 4) Solution Overview
1. Upload course PDFs (notes/handbook/assignment brief).
2. The app parses and chunks text, creates embeddings, and stores them in a vector database.
3. When a user asks a question, the app retrieves the most relevant chunks (Top-K).
4. An LLM generates the final response using retrieved context and shows citations.

## 5) Key Features
- PDF upload & document library
- RAG-based Q&A
- Citations for traceability (document/page/chunk)
- Simple, clean UI

## 6) Tech Stack
- Python, Streamlit
- RAG framework: [LangChain / LlamaIndex]
- Vector store: [Chroma / FAISS]
- Embeddings: [model name]
- LLM: Gemini API (or equivalent)

## 7) AI Integration (Why AI is Central)
AI is central to the solution:
- The LLM understands natural language questions and generates coherent answers.
- RAG retrieves relevant document chunks to ground the response and reduce hallucinations.
Without LLM + retrieval, the system cannot reliably answer questions from course materials.

## 8) Architecture Diagram
```mermaid
flowchart LR
  U[Student] -->|Upload PDFs| UI[Streamlit UI]
  UI --> P[PDF Parser] --> C[Chunker] --> E[Embeddings] --> VS[(Vector Store)]
  U -->|Ask| UI --> R[Retriever Top-K] --> VS --> CTX[Context Builder] --> LLM[LLM] --> ANS[Answer + Citations] --> UI
