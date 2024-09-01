# hilabs_rag
Submission for hackathon
# PDF Chatbot with LLM and Table Extraction
This project implements a PDF chatbot that uses Language Model (LLM) integration and table extraction to provide intelligent responses to questions about PDF content. It combines vector search, keyword extraction, and table analysis to offer comprehensive answers.

![PDF Chatbot](https://github.com/yourusername/pdf-chatbot/blob/main/architecture.png)
## Features
- PDF text and table extraction
- Vector store creation for efficient similarity search
- Integration with Ollama for LLM-powered responses
- Dynamic query generation and multi-query processing
- Gradio-based user interface for easy interaction
## Requirements
- Python 3.7+
- PyPDF2
- pytesseract
- pdf2image
- langchain
- gradio
- pandas
- ollama
- tabula-py
## Installation
1. Clone this repository:
   
   git clone https://github.com/yourusername/pdf-chatbot.git
   cd pdf-chatbot
   
2. Install the required packages:
   
   pip install PyPDF2 pytesseract pdf2image langchain gradio pandas ollama tabula-py
   
3. Install Tesseract OCR on your system if not already installed:
   - For Ubuntu: sudo apt-get install tesseract-ocr
   - For macOS: brew install tesseract
   - For Windows: Download and install from [GitHub](https://github.com/UB-Mannheim/tesseract/wiki)
4. Install Ollama following the instructions on the [official website](https://ollama.ai/).
## Usage
1. Run the script:
   
   python pdf_chatbot.py
   
2. Open the Gradio interface in your web browser (the URL will be displayed in the console).
3. In the "Process PDF" tab:
   - Upload a PDF file
   - Click "Process PDF"
   - Wait for the "PDF processed successfully!" message
4. Switch to the "Ask Questions" tab:
   - Enter your question about the PDF content
   - Click "Ask"
   - View the JSON response containing the answer and related information
## How It Works
1. PDF Processing:
   - Extracts text using PyPDF2
   - Extracts tables using tabula
   - Creates a vector store using Chroma and HuggingFace embeddings
2. Question Answering:
   - Checks for specific codes or names in the question
   - Extracts keywords from the question
   - Performs unified retrieval combining similarity search and keyword-based search
   - Generates an initial answer using the LLM
3. Answer Quality Evaluation:
   - Evaluates the quality of the initial answer
   - If the quality is insufficient, generates multiple related queries
   - Processes each query and combines the results for a comprehensive answer
4. LLM Integration:
   - Uses Ollama to generate responses, extract keywords, and evaluate answer quality
5. User Interface:
   - Provides a Gradio-based interface for easy PDF processing and question answering
## Customization
- To use a different LLM, modify the LLMServer class in the script
- Adjust the chunk_size and chunk_overlap in the create_vectorstore function for different text splitting behavior
- Modify the prompts in various functions to change the LLM's behavior
## Limitations
- The current implementation assumes English language content
- Performance may vary depending on the PDF structure and content complexity
- Large PDFs may require significant processing time and memory
## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.
## License
This project is open-source and available under the MIT License.
