# RAG - Retrieval-Augmented Generation

A local RAG (Retrieval-Augmented Generation) system that lets you query your documents using natural language. It loads documents, generates embeddings, stores them in a FAISS vector database, and uses Google Gemini LLM to summarize relevant context.

## How It Works

1. **Load** - Ingest documents (PDF, TXT, CSV, Excel, Word, JSON)
2. **Chunk** - Split documents into manageable text chunks
3. **Embed** - Generate vector embeddings using Sentence Transformers
4. **Store** - Index embeddings in FAISS for fast similarity search
5. **Query** - Retrieve relevant chunks and summarize with Google Gemini

## Setup

### Prerequisites

- Python 3.12+
- A Google API key (for Gemini LLM)

### Installation

```bash
# Clone the repository
git clone https://github.com/Aayan216/RAG-p1.git
cd RAG-p1

# Install dependencies
pip install -r requirements.txt

# Create a .env file with your API key
echo 'GOOGLE_API_KEY=your_api_key_here' > .env
```

### Usage

1. Place your documents in the `data/` folder (supported: PDF, TXT, CSV, Excel, Word, JSON)
2. Run the app:

```bash
python app.py
```

3. Edit the query in `app.py` or import and use programmatically:

```python
from src.search import RAGSearch

rag = RAGSearch()
result = rag.search_and_summarize("Your question here", top_k=3)
print(result)
```

## Project Structure

```
RAG-p1/
├── app.py                 # Main entry point
├── src/
│   ├── data_loader.py     # Multi-format document loading
│   ├── embedding.py       # Text chunking + embedding pipeline
│   ├── vectorstore.py     # FAISS vector store management
│   └── search.py          # RAG search + LLM summarization
├── data/
│   └── text_files/        # Sample text documents
├── requirements.txt
└── pyproject.toml
```

## Technologies

- **LangChain** - Document loading and text splitting
- **FAISS** - Vector similarity search
- **Sentence Transformers** - Text embeddings (`all-MiniLM-L6-v2`)
- **Google Gemini** - LLM for summarization

---

## Author

**Mohammed Aayan**  
B.Tech — Computer Science & Information Technology
