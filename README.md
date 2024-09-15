# Document-Q&A-RAG-App

Here’s a sample `README.md` file for your Document Q&A RAG app built with Streamlit, Groq, and Gemini. This document covers project setup, requirements, usage instructions, and a high-level overview of the functionality.

---

# Document Q&A RAG App

This project is a **Document Question-and-Answer Retrieval Augmented Generation (RAG) app** built with Streamlit, Groq (Gemma model), and Google Generative AI embeddings. It allows users to upload a set of documents, create vector embeddings using Google Generative AI, and ask questions about the documents, retrieving relevant answers using Groq's Gemma model.

## Features

- **Document Loading**: Upload documents in PDF format for ingestion.
- **Vector Embeddings**: Create embeddings for documents using Google Generative AI.
- **Document Retrieval**: Retrieve relevant document sections using FAISS for question answering.
- **Question-Answering**: Use Groq's Gemma model to answer questions based on the retrieved context.
- **Streamlit Interface**: A user-friendly web interface built with Streamlit for easy interaction.

## Project Structure

```bash
.
├── app.py               # Main entry point for the Streamlit app
├── us_census/
│   ├── different.pdf 
├── .env                 # Stores API keys (Groq, Google Generative AI)
├── requirements.txt     # Python dependencies
└── README.md            # Project documentation
```

## Images of chatbot
![image1](<Screenshot 2024-09-15 220130.png>)
![image2](<Screenshot 2024-09-15 220223.png>)
![alt text](<Screenshot 2024-09-15 220242.png>)

### Prerequisites

Ensure you have the following installed:

- **Python 3.12** or later
- **Conda** (for environment management)
- **Groq API key** and **Google Generative AI API key** (add these to `.env`)

### Clone the Repository

```bash
git clone https://github.com/your-username/Document-Q-A-RAG-App.git
cd Document-Q-A-RAG-App
```

### Create and Activate Virtual Environment

```bash
conda create -n rag_doc python=3.12 -y
conda activate rag_doc
```

### Install Dependencies

Install the required Python packages using `pip`:

```bash
pip install -r requirements.txt
```

### Set Up Environment Variables

Create a `.env` file in the root directory with the following content:

```bash
GROQ_API_KEY=your_groq_api_key
GOOGLE_API_KEY=your_google_api_key
```

Replace `your_groq_api_key` and `your_google_api_key` with your actual API keys.

### Run the App

Run the Streamlit app:

```bash
streamlit run app.py
```

This will start a local web server, and you can access the app in your browser at `http://localhost:8501`.

## Usage

1. **Upload Documents**: Place your documents (PDF format) in the `us_census` directory or modify the path in `vectorstore.py`.
2. **Create Vector Store**: Use the interface to create a vector store from the uploaded documents.
3. **Ask Questions**: Enter your question, and the app will retrieve relevant document sections and provide an answer using the Groq Gemma model.

## Code Overview

- **app.py**: The main entry point for the Streamlit app, containing the UI and logic to handle user inputs and outputs.
- **core/document_loader.py**: Contains logic for loading PDF documents and splitting them into manageable chunks using `RecursiveCharacterTextSplitter`.
- **core/vectorstore.py**: Contains logic for creating vector embeddings using Google Generative AI and FAISS for document retrieval.
  
## Dependencies

All dependencies are listed in `requirements.txt`. Here’s a breakdown of key libraries:

- **Streamlit**: For building the web interface.
- **Langchain**: Provides utility for managing document chains and embedding generation.
- **FAISS**: For creating the vector store used for document retrieval.
- **GoogleGenerativeAIEmbeddings**: Embeddings generation using Google Generative AI.
- **PyPDF**: For loading and parsing PDF documents.


## Troubleshooting

- **Missing API Keys**: Make sure your `.env` file is correctly configured with Groq and Google API keys.
- **Vector Store Initialization Errors**: Ensure all documents are correctly loaded and split before creating embeddings.
- **Streamlit Session Issues**: Check if variables are properly initialized in `st.session_state`.

## Future Improvements

- Add support for more file types (e.g., DOCX, TXT).
- Implement caching for faster question-answering.
- Enhance the interface for batch document uploads.

## License

This project is licensed under the MIT License.

---
