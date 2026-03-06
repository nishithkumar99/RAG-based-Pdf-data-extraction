Local PDF RAG with LangChain & Ollama
This repository contains a Jupyter Notebook implementing a Retrieval-Augmented Generation (RAG) pipeline that allows you to chat with PDF documents locally. The system uses Ollama for both embeddings and the LLM, ensuring your data never leaves your machine.

🚀 Features
Local Processing: Powered by Ollama (llama3.1) for privacy and cost-efficiency.

Vector Store: Uses ChromaDB for persistent document indexing.

Tool-Augmented Agent: Implements a LangChain agent capable of using a retrieval tool to find context before answering.

Smart Chunking: Utilizes RecursiveCharacterTextSplitter to maintain context across document segments.

🛠️ Tech Stack
Orchestration: LangChain

LLM & Embeddings: Ollama (Model: llama3.1:latest)

Vector Database: Chroma

PDF Parsing: PyPDF

📋 Prerequisites
Ollama Installed: Download and install from ollama.com.

Model Pulled: Run the following command in your terminal:

Bash
ollama pull llama3.1
Python Environment: Python 3.11+ recommended.

🔧 Installation & Setup
Clone the repository:

Bash
git clone <your-repo-url>
cd <your-repo-name>
Install dependencies:

Bash
pip install langchain-community pypdf langchain-ollama chromadb langchain-chroma langchain
Add your PDF:
Place your PDF file in the root directory. (The notebook is currently configured to look for Think-And-Grow-Rich_2011-06.pdf).

📖 Notebook Workflow
The main.ipynb follows these logical steps:

Loading: Uses PyPDFLoader to ingest the document.

Chunking: Splits the text into 1000-character chunks with a 200-character overlap.

Vectorization: Generates embeddings using Ollama and stores them in a local ./chroma_db directory.

Tool Creation: Defines a retrieve_context tool that performs similarity searches.

Agent Execution: An AI Agent receives a query, decides to use the retrieval tool, and provides an answer based on the PDF's content.

⚠️ Troubleshooting
Connection Error:
If you see a ConnectionError: Failed to connect to Ollama, ensure the Ollama application is running in the background and that you have pulled the llama3.1 model.
