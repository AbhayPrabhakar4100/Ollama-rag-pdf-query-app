
# Local-RAG-Document-Query-App-with-Ollama-LLM

## 📝 Overview
This project is a lightweight **retrieval-augmented generation (RAG)** system that combines a vector database with a large language model (LLM).  
The application lets users upload PDF files, transform them into embeddings, and query their contents through natural language questions. Answers are generated using the retrieved context from the document.

---

## ⚡ Core Components
- **Streamlit** → front-end interface for interaction  
- **ChromaDB** → persistent vector database for embeddings  
- **Ollama** → provides both embeddings and LLM responses  
- **LangChain** → handles loading, chunking, and orchestration of documents  
- **PyMuPDF** → efficient PDF parsing and content extraction  
- **CrossEncoder** → improves result ranking by relevance  
- **hydralit_components** → adds custom UI elements to Streamlit  

---

## 🔎 Capabilities
- **Upload PDFs** → Parse and split documents into smaller chunks  
- **Vector Indexing** → Store embeddings in ChromaDB for similarity search  
- **Efficient Retrieval** → Query top-matching chunks for a given question  
- **Re-Ranking** → Apply CrossEncoder to refine the order of retrieved results  
- **Context-Aware Responses** → Ollama LLM generates structured, human-like answers based on relevant chunks  
- **Expandable Results** → View supporting documents alongside answers  

---

## 🔄 End-to-End Flow
1. **Upload Document** → User selects a PDF file in Streamlit  
2. **Preprocessing** → Split into text chunks and embed with Ollama  
3. **Vector Storage** → Save embeddings into ChromaDB  
4. **Ask a Question** → User submits a query  
5. **Retrieve + Rank** → Relevant chunks pulled, re-ranked with CrossEncoder  
6. **Generate Answer** → Ollama LLM produces the final response  

---

## 🖼 Example
**Scenario:** Upload a PDF with product specifications  
- **Query:** *“List the main product features.”*  
- **Output:** Retrieves matching sections → ranks them → produces a concise summary with Ollama  

---

## 🧑‍💻 Code Structure
- `process_document()` → Converts uploaded PDFs into chunks  
- `get_vector_collection()` → Creates/retrieves a ChromaDB collection  
- `add_to_vector_collection()` → Adds chunks + metadata into the vector store  
- `query_collection()` → Searches collection for relevant chunks  
- `re_rank_cross_encoders()` → Reorders results by relevance  
- `call_llm()` → Generates final answers using Ollama’s chat model  

---

## ⚙️ Setup & Installation
Install required packages:
```bash
pip install streamlit chromadb ollama langchain sentence-transformers hydralit-components
