# UniRAG Helpdesk (RAG-based AI FAQ Assistant)

## 1. Project Overview
UniRAG Helpdesk is an AI-powered question answering app that helps students quickly find accurate information from uploaded PDFs (course notes, assignment briefs, student handbook). It uses Retrieval-Augmented Generation (RAG) to answer questions with citations.

## 2. Problem Statement
Students often waste time searching across multiple documents and may misunderstand policies or assignment requirements. A searchable AI assistant grounded in official documents can improve clarity and reduce misinformation.

## 3. Target Users
- Diploma/University students
- Lecturers/Tutors
- Student affairs staff (optional)

## 4. Solution Overview
Users upload PDF documents, then ask questions in natural language. The app retrieves the most relevant text chunks from a vector database and generates an answer using an LLM, showing citations for traceability.

## 5. Tech Stack
- Python, Streamlit
- RAG framework: [LangChain / LlamaIndex]
- Vector store: Chroma
- Embeddings: [e.g., text-embedding model]
- LLM: Gemini API (or equivalent)

## 6. AI Integration (Why AI is Central)
This project requires AI to:
1) Understand the user’s natural language questions
2) Generate coherent answers
3) Stay grounded by retrieving relevant document chunks (RAG)
Without the LLM + RAG pipeline, the app cannot provide reliable answers.

## 7. Architecture Diagram
docs/architecture.png

## 8. Setup Instructions
### Prerequisites
- Python 3.10+

### Installation
```bash
git clone https://github.com/[yourname]/unirag-helpdesk.git
cd unirag-helpdesk
pip install -r requirements.txt
