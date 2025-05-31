# Insurellm RAG Chatbot with Vector Store and Visualization

This project implements an **Expert Knowledge Worker**: a question-answering assistant for Insurellm, an Insurance Tech company. The assistant uses **Retrieval Augmented Generation (RAG)** with a vector database to provide accurate, context-aware answers to employee queries.

---

## Features

- **Retrieval Augmented Generation (RAG):**  
  Combines LLMs with a vector database to ground answers in your company’s knowledge base.
- **Document Ingestion:**  
  Loads and splits documents from the `knowledge-base` directory (supports multiple types: products, employees, contracts, company info).
- **Vector Embeddings:**  
  Supports both OpenAI and HuggingFace embeddings for flexibility and cost control.
- **Vector Store:**  
  Uses ChromaDB to store and retrieve document chunks by semantic similarity.
- **Visualization:**  
  Visualizes document embeddings in 2D and 3D using t-SNE and Plotly for insight into your knowledge base.
- **Conversational Memory:**  
  Maintains chat history for multi-turn, context-aware conversations.
- **LangChain Integration:**  
  Uses LangChain’s ConversationalRetrievalChain for seamless LLM + retrieval workflow.
- **Gradio Chat UI:**  
  Provides a simple web interface for employees to interact with the assistant.

---

## How It Works

1. **Document Loading:**  
   All Markdown files in `knowledge-base` subfolders are loaded and split into overlapping chunks.
2. **Embedding & Vector Store:**  
   Each chunk is embedded and stored in a Chroma vector database.
3. **Querying:**  
   When a user asks a question, the most relevant chunks are retrieved and provided as context to the LLM.
4. **Answer Generation:**  
   The LLM (e.g., `gpt-4o-mini`) generates an answer grounded in the retrieved context.
5. **Visualization:**  
   Embeddings can be visualized in 2D/3D to understand document relationships.

---

## Setup

1. **Clone the repository and install dependencies:**
    ```bash
    pip install langchain langchain-openai langchain-chroma openai python-dotenv plotly scikit-learn matplotlib
    ```

2. **Prepare your `.env` file:**
    ```
    OPENAI_API_KEY=your-openai-api-key
    ```

3. **Organize your knowledge base:**
    ```
    knowledge-base/
      employees/
      products/
      contracts/
      company/
    ```
    Place Markdown (`.md`) files in the appropriate folders.

4. **Run the notebook:**
    - Open `day5.ipynb` in Jupyter or VS Code.
    - Execute cells to build the vector store, visualize embeddings, and launch the chat UI.

---

## Usage

- **Chatbot:**  
  Launches a Gradio chat interface for employees to ask questions and get accurate, context-aware answers.
- **Visualization:**  
  Explore the structure of your knowledge base via interactive 2D/3D plots.

---

## Customization

- **Embeddings:**  
  Switch between OpenAI and HuggingFace embeddings by changing a single line.
- **LLM:**  
  Use OpenAI models or swap in a local model (e.g., via Ollama) for privacy/cost reasons.
- **Vector Store:**  
  Easily extend to other vector databases if needed.

---

## Example

![Vector Store Visualization Example](vectorstore_example.png)

---

## License

MIT License

---

**Created for educational purposes. Adapt and extend for your own enterprise RAG solutions!**
