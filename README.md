# RAG-based QA Bot with Interactive Interface



## Overview
This application allows users to upload financial documents, such as Profit and Loss (P&L) statements, and ask financial queries. 
Using a combination of vector database indexing and a Retrieval-Augmented Generation (RAG) model, the app generates real-time, contextually accurate responses to user queries. 
It also displays the specific data segments used to formulate the answers, enhancing transparency.


## Features
Frontend Interface: 
   Built using Streamlit/Gradio for simplicity and accessibility
Users can:
   Upload PDF documents containing P&L data.
Input queries like "What is the gross profit for Q3 2024?" or "What is the total revenue for the year?"
Retrieve answers along with references to relevant financial data.

## Backend Integration
Data Processing:
   Extracts and preprocesses financial data from uploaded PDFs.Converts the data into embeddings for efficient vector search.
   
Query Resolution:
   Uses a RAG pipeline to retrieve relevant financial data and generate precise, context-aware responses.
   
Efficient Retrieval:
   Stores embeddings in a vector database (Pinecone) for high-speed similarity searches.

## How to Use the Application

1. Clone the repository:

   ```bash
   

2. Install the required Python dependencies:

   ```bash
   pip install -r requirements.txt

3. Configure your Pinecone and OpenAI API keys:

   ```bash
   PINECONE_API_KEY=your_pinecone_api_key
   OPENAI_API_KEY=your_openai_api_key
    
4. Run the app deployed on docker:
   You will have to have docker installed in your system to run the application.
   
   ```bash
   Step 1:
    docker build -t all .

    Step 2:
    docker run -dp 127.0.0.1:8501:8501 -p 8000:8000 all

    Step 3:
    Open "127.0.0.1:8501" on browser
   
## Uploading Documents:

On the app's homepage, click the "Upload PDF" button.
Select a PDF file containing P&L statements or similar financial data.
Asking Queries:
   Enter a financial query into the provided text input field.
   
Examples:
   "What is the gross profit for Q3 2024?"
   "What are the total expenses for the year?"

Interpreting Results:
   View the generated answer alongside the referenced segments from the P&L statement.

## Example Interactions
Upload:
   User uploads "Sample_Financial_Statement.pdf".
Query:
   Input: "What is the net income for 2023?"
   Response: "The net income for 2023 is $45,000. Referenced from "  "
   
