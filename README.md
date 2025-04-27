# PDF Question Answering System

A powerful tool that allows you to upload PDF documents and ask questions about their content using natural language. This system leverages large language models and vector embeddings to provide accurate answers from your documents.

## Overview

This application combines several key technologies:
- **Document Processing**: Extracts and chunks text from PDFs
- **Vector Embeddings**: Creates searchable embeddings using Hugging Face models
- **Retrieval-Augmented Generation (RAG)**: Finds relevant passages and generates answers
- **Conversational Memory**: Maintains context throughout a conversation

## Features

- 📄 PDF document upload and processing
- 🔍 Semantic search using vector embeddings
- 💬 Natural language question answering
- 🧠 Conversation history tracking
- 🤖 Powered by Mixtral-8x7B language model

## Requirements

- Python 3.8+
- Google Colab (recommended for easy setup)
- Hugging Face API token

## Installation

1. Open the notebook in Google Colab
2. Add your Hugging Face API token as a secret
3. Run the installation cells to set up dependencies

```python
import os
from google.colab import userdata
os.environ["HUGGINGFACEHUB_API_TOKEN"] = userdata.get('HF_TOKEN')
```

## Usage

1. Run the notebook cells to initialize the system
2. Upload your PDF document when prompted
3. Ask questions about the document content
4. Type 'quit' to exit the question-answering loop

## How It Works

1. **Document Loading**: The PDF is loaded and text is extracted
2. **Text Chunking**: The document is split into manageable chunks with overlaps
3. **Vector Embedding**: Each chunk is transformed into a vector representation
4. **Retrieval**: When you ask a question, the system finds the most relevant chunks
5. **Generation**: The language model generates an answer based on the retrieved context

## Code Structure

- `load_and_process_document()`: Handles PDF loading and text chunking
- `setup_qa_system()`: Sets up the vector store and QA chain
- `main()`: Orchestrates the workflow and user interaction loop

## Example

```
Please upload a PDF file:
[File upload widget appears]

Processing document...
Setting up QA system...

Ask a question about the document (or 'quit' to exit): What are the key findings in the report?

Answer: [System generates an answer based on document content]

Ask a question about the document (or 'quit' to exit): quit
```

## Troubleshooting

- **Memory Issues**: If you encounter memory errors, try reducing chunk size
- **Model Access**: Ensure your Hugging Face API token has access to the required models
- **PDF Extraction**: For PDFs with complex formatting, results may vary

## Customization

You can modify the following parameters to tune the system:
- `chunk_size`: Controls the size of text chunks (default: 1000)
- `chunk_overlap`: Controls the overlap between chunks (default: 200)
- `temperature`: Controls randomness in responses (default: 0.1)
- `max_new_tokens`: Controls maximum response length (default: 512)

## License

This project is provided as-is for educational and research purposes.

## Acknowledgments

This system uses the following libraries and models:
- LangChain for the RAG framework
- Hugging Face for embedding and language models
- PyPDF for PDF text extraction
- Chroma for vector storage