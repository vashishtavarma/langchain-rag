# LangChain RAG System

A Retrieval-Augmented Generation (RAG) system built with LangChain, Google Gemini, and LangGraph for querying professional profile information.

## 🚀 Features

- **Document Processing**: Load and process professional profile documents
- **Vector Store**: In-memory vector storage with Google Generative AI embeddings
- **RAG Pipeline**: Complete retrieval-augmented generation workflow
- **Question Answering**: Interactive Q&A system for professional information
- **LangGraph Integration**: State-based application flow management

## 🛠️ Tech Stack

- **LangChain**: Document processing and RAG pipeline
- **Google Gemini**: Language model (gemini-2.5-flash)
- **Google Generative AI**: Embeddings (gemini-embedding-001)
- **LangGraph**: Application state management
- **Python**: Core programming language
- **Jupyter Notebook**: Interactive development environment

## 📋 Prerequisites

- Python 3.8+
- Google API Key for Gemini access
- Virtual environment (recommended)

## 🔧 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/vashishtavarma/langchain-rag.git
   cd langchain-rag
   ```

2. **Create virtual environment**
   ```bash
   python -m venv venv
   source venv/Scripts/activate  # Windows
   # source venv/bin/activate    # macOS/Linux
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**
   - Obtain a Google API key from [Google AI Studio](https://makersuite.google.com/app/apikey)
   - The notebook will prompt you to enter the API key when running

## 📖 Usage

### Running the Notebook

1. **Start Jupyter**
   ```bash
   jupyter notebook main.ipynb
   ```

2. **Run cells sequentially**:
   - Cell 1: Set up Google API key
   - Cell 2: Initialize Gemini language model
   - Cell 3: Set up embeddings
   - Cell 4: Create vector store
   - Cell 5: Load document and create RAG pipeline
   - Cell 6: Test with questions

### Example Questions

```python
# Test the RAG system with these questions:
questions = [
    "What GitHub achievements does Vashishta have?",
    "How many repositories does Vashishta have?",
    "What is Vashishta's primary programming language?",
    "Explain the Huffman coding implementation",
    "What web technologies are used in the projects?",
    "What are Vashishta's specialized areas?",
    "What kind of applications has Vashishta built?"
]
```

## 📁 Project Structure

```
langchain-rag/
├── main.ipynb           # Main Jupyter notebook with RAG implementation
├── document.txt         # Professional profile document for testing
├── requirements.txt     # Python dependencies
├── README.md           # Project documentation
├── LICENSE             # MIT license
└── .gitignore          # Git ignore patterns
```

## 🔄 RAG Pipeline Components

### 1. Document Loading
- Reads professional profile from `document.txt`
- Creates LangChain Document objects with metadata

### 2. Text Splitting
- Uses `RecursiveCharacterTextSplitter`
- Chunk size: 500 characters
- Overlap: 100 characters

### 3. Vector Store
- In-memory vector storage
- Google Generative AI embeddings
- Similarity search for retrieval

### 4. LangGraph Workflow
- **State Management**: Question, context, and answer tracking
- **Retrieve Function**: Similarity search for relevant documents
- **Generate Function**: LLM-based answer generation

## 🧪 Testing

The system includes comprehensive test questions covering:
- **Personal Information**: GitHub profile, achievements, repositories
- **Technical Skills**: Programming languages, frameworks, tools
- **Project Details**: HuffComp, AI News Analysis, blockchain projects
- **Implementation Details**: Algorithms, architectures, technologies

## 🚀 Advanced Usage

### Custom Document Loading
```python
# Load your own documents
with open("your_document.txt", "r", encoding="utf-8") as file:
    content = file.read()

docs = [Document(
    page_content=content,
    metadata={"source": "your_document.txt", "type": "custom"}
)]
```

### Adjusting Chunk Size
```python
# Modify text splitting parameters
text_splitter = RecursiveCharacterTextSplitter(
    chunk_size=1000,  # Larger chunks
    chunk_overlap=200  # More overlap
)
```

### Enhanced Retrieval
```python
# Retrieve more documents for context
def retrieve(state: State):
    retrieved_docs = vector_store.similarity_search(
        state["question"], 
        k=5  # Retrieve top 5 documents
    )
    return {"context": retrieved_docs}
```

## 🔒 Security

- **API Key Management**: Secure handling of Google API keys
- **Environment Variables**: No hardcoded credentials
- **Local Processing**: Documents processed locally

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [LangChain](https://langchain.com/) for the RAG framework
- [Google AI](https://ai.google.dev/) for Gemini models and embeddings
- [LangGraph](https://langchain-ai.github.io/langgraph/) for workflow management

## 📞 Contact

- **GitHub**: [@vashishtavarma](https://github.com/vashishtavarma)
- **LinkedIn**: [M Vashishta Varma](https://www.linkedin.com/in/m-vashishta-varma-134b1529a/)

---

⭐ **Star this repository if you find it helpful!**
