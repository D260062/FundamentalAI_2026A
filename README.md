flowchart LR
  U[Student] -->|Upload course PDFs| UI[Streamlit UI]
  UI --> P[PDF Parser]
  P --> C[Chunker]
  C --> E[Embeddings Model]
  E --> VS[(Vector Store: Chroma/FAISS)]

  U -->|Ask a question| UI
  UI --> R[Retriever Top-K]
  R --> VS
  R --> CTX[Context Builder]
  CTX --> LLM[LLM: Gemini / Equivalent]
  LLM --> ANS[Answer + Citations]
  ANS --> UI
