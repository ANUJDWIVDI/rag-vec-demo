# RAG Multi-Language System - Setup Guide

## 📋 Prerequisites

1. **Python 3.8+** installed on your system
2. **Google Gemini API Key** - Get from [Google AI Studio](https://makersuite.google.com/app/apikey)
3. **Pinecone API Key** - Get from [Pinecone Console](https://www.pinecone.io/)

## 🚀 Quick Start

### Step 1: Install Dependencies
```bash
pip install streamlit google-generativeai PyPDF2 pinecone-client sentence-transformers langdetect
```

### Step 2: Get API Keys

1. **Gemini API Key:**
   - Go to [Google AI Studio](https://makersuite.google.com/app/apikey)
   - Click "Get API Key"
   - Create a new API key
   - Copy the key

2. **Pinecone API Key:**
   - Sign up at [Pinecone](https://www.pinecone.io/)
   - Create a new project
   - Go to "API Keys" section
   - Copy your API key and environment

### Step 3: Configure the Script

Open the Python script and replace these values:
```python
GOOGLE_API_KEY = "your_actual_gemini_api_key_here"
PINECONE_API_KEY = "your_actual_pinecone_api_key_here"
PINECONE_ENVIRONMENT = "your_pinecone_environment"  # e.g., "gcp-starter"
```

### Step 4: Run the Application
```bash
streamlit run app.py
```

## 🎯 Key Features

### 1. Document Processing
- **PDF Upload**: Upload any PDF document
- **Text Extraction**: Automatic text extraction using PyPDF2
- **Chunking**: Intelligent text splitting with overlap
- **Embeddings**: Convert text to vectors using SentenceTransformers

### 2. Multi-Language Support
- **Auto-Detection**: Automatic language detection
- **8 Languages**: English, Spanish, French, German, Italian, Portuguese, Chinese, Japanese
- **Native Responses**: AI responds in the detected language

### 3. RAG Pipeline
- **Vector Storage**: Store embeddings in Pinecone
- **Semantic Search**: Find relevant document chunks
- **Context Building**: Combine relevant chunks for AI
- **Response Generation**: Generate answers using Gemini

### 4. User Interface
- **Clean Design**: Modern Streamlit interface
- **Real-time Chat**: Interactive chat experience
- **Memory Management**: Session persistence
- **Export Options**: Download conversation history

## 📚 How It Works

### 1. Document Processing Flow
```
PDF Upload → Text Extraction → Chunking → Embeddings → Pinecone Storage
```

### 2. Query Processing Flow
```
User Query → Language Detection → Query Embedding → Similarity Search → Context Retrieval → AI Response
```

### 3. Multi-Language Agent
```
Query → Language Detection → Language-Specific Prompt → Gemini API → Response in Target Language
```

## 🔧 Troubleshooting

### Common Issues:

1. **Import Errors**
   ```bash
   pip install --upgrade streamlit google-generativeai PyPDF2 pinecone-client sentence-transformers langdetect
   ```

2. **API Key Errors**
   - Ensure API keys are correctly replaced in the script
   - Check if keys are active and have proper permissions

3. **Pinecone Errors**
   - Make sure Pinecone environment matches your account
   - Check if you have enough quota for vector operations

## 💡 Tips for Best Results

1. **Document Quality**: Use clear, well-formatted PDFs
2. **Question Style**: Ask specific questions about the document
3. **Language**: The system works best with clear, grammatically correct questions
4. **Context**: Follow-up questions work well due to conversation memory

## 🔐 Security Notes

- Never commit API keys to version control
- Use environment variables in production
- Consider using Streamlit secrets for deployment

## 📈 Performance Optimization

1. **Caching**: The system caches embeddings and processed documents
2. **Chunking**: Adjust chunk size based on your document type
3. **Batch Processing**: Process multiple queries efficiently

## 🌟 Advanced Usage

### Custom Prompts
You can modify the language-specific prompts in the `MultiLanguageAgent` class to customize AI behavior.

### Embedding Models
Try different SentenceTransformer models:
- `all-MiniLM-L6-v2` (current, fast)
- `all-mpnet-base-v2` (better quality, slower)
- `paraphrase-multilingual-MiniLM-L12-v2` (multilingual)

### Vector Database
The system uses Pinecone, but you can adapt it for other vector databases like:
- Chroma
- Weaviate
- Qdrant

## 📞 Support

If you encounter issues:
1. Check the console for error messages
2. Verify your API keys are correct
3. Ensure all dependencies are installed
4. Try with a simpler PDF first

## 📄 License

This is an educational project. Feel free to use and modify for learning purposes.