# Chat with Multiple PDFs using Gemini AI

This Streamlit application allows users to upload multiple PDF files and interact with the content through a conversational AI chatbot powered by Google Gemini AI. The application processes PDF files, extracts text, indexes the content using FAISS, and enables conversational question-answering using Google Generative AI.

---

## Features

- **Upload PDFs**: Supports uploading multiple PDF files.
- **Text Extraction**: Extracts text content from uploaded PDFs using `PyPDF2`.
- **Text Chunking**: Splits large texts into manageable chunks for efficient processing.
- **Vector Store Creation**: Indexes text chunks using FAISS and Google Generative AI embeddings.
- **Conversational AI**: Answers user queries based on the indexed content using Google Gemini AI.

---

## Prerequisites

### 1. **API Key for Google Generative AI**
   - Set up your Google API Key and enable access to Google Gemini AI.

### 2. **Python Libraries**
   Install the following Python libraries:

   ```bash
   pip install -r requirements.txt
   ```

---

## Setup Instructions

1. **Clone the Repository**:
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```

2. **Set Environment Variables**:
   - Create a `.env` file in the project root and add your Google API Key:
     ```
     GOOGLE_API_KEY=<your_google_api_key>
     ```

3. **Run the Application**:
   ```bash
   streamlit run app.py
   ```

4. **Access the Application**:
   - Open your web browser and navigate to `http://localhost:8501`.

---

## How to Use

1. **Upload PDFs**:
   - Drag and drop one or more PDF files into the sidebar file uploader.

2. **Process PDFs**:
   - Click the "Submit & Process" button to extract, split, and index the text.

3. **Ask Questions**:
   - Enter your query in the text input box, and the chatbot will provide answers based on the indexed PDF content.

---

## Code Overview

### 1. **Text Extraction**
   - `get_pdf_text(pdf_docs)`: Extracts text from the uploaded PDFs.

### 2. **Text Chunking**
   - `get_text_chunks(text)`: Splits large text into smaller chunks for easier indexing and retrieval.

### 3. **Vector Store Management**
   - `get_vector_store(text_chunks)`: Creates and saves a FAISS vector store using Google Generative AI embeddings.

### 4. **Conversational AI Chain**
   - `get_conversational_chain()`: Configures the AI model and custom prompt for question-answering.

### 5. **User Interaction**
   - `user_input(user_question)`: Handles user queries, retrieves relevant document chunks, and generates a response.

### 6. **Streamlit UI**
   - **Main Page**: Accepts user queries.
   - **Sidebar**: Allows PDF uploads and triggers processing.

---

## Folder Structure

```
.
├── app.py              # Main application file
├── .env                # Environment variables
├── faiss_index/        # Local FAISS vector store
├── requirements.txt    # List of dependencies
└── README.md           # Project documentation
```

---

## Future Enhancements

- Add support for more file formats (e.g., DOCX, TXT).
- Include summarization for large documents.
- Optimize FAISS indexing for scalability.
- Add a downloadable chat history feature.

---

## License

This project is open-source and available under the [MIT License](LICENSE).

---

## Contributing

Feel free to submit issues or pull requests to enhance the functionality of this application.

---

## Acknowledgements

- [Google Generative AI](https://developers.google.com/generative-ai)
- [FAISS](https://github.com/facebookresearch/faiss)
- [Streamlit](https://streamlit.io/)
- [PyPDF2](https://pypi.org/project/PyPDF2/)
