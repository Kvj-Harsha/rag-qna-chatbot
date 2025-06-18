

# 💬 RAG-QnA Chatbot

A **Retrieval-Augmented Generation (RAG)** based chatbot built using **Streamlit**, **ChromaDB**, and **OpenAI API**, designed to ingest documents and answer user queries contextually.

---

![diagram (6)](https://github.com/user-attachments/assets/52257720-ffd0-47b0-ab9a-11d1f1623b05)

---

## 📁 Project Structure

```bash
├── main.py                          # Streamlit app entry point
├── pages/
│   ├── ingest_page.py              # Handles document upload and ingestion
│   └── chatbot_page.py             # Handles QnA interface
├── services/
│   ├── chroma_services.py         # Vector DB operations using Chroma
│   └── genai_services.py          # OpenAI API interaction
├── data/
│   └── data.txt                    # Sample source document
├── .env                            # Environment variables (template)
├── requirements.txt                # Python dependencies
├── README.md                       # Project overview
```

---

## 🚀 Getting Started

### 1. Clone the Repo

```bash
git clone https://github.com/your-username/rag-qna-chatbot.git
cd rag-qna-chatbot
```

### 2. Set Up Environment

Create a `.env` file based on the `template.env` and add your API keys and config:

```env
OPENAI_API_KEY=your_openai_key
CHROMA_DB_PATH=./data
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the App

```bash
streamlit run main.py
```

---

## 🔍 Features

- 📄 **Document Ingestion**: Upload documents via the **Ingest Page** (`pages/ingest_page.py`)
- 💡 **Semantic Search**: Retrieves context from documents using **ChromaDB**
- 🧠 **Answer Generation**: Uses **OpenAI API** to answer questions with contextual awareness
- 📊 **Modular Layers**:
  - Presentation Layer: Streamlit UI
  - Service Layer: Vector DB + GenAI handling
  - Data Layer: Source documents and embeddings

---

## 🛠️ Internals

### Streamlit Entry (`main.py`)
- Registers both `Ingest` and `Chatbot` pages.
- Entry point of the app.

### Ingest Page
- Lets user upload `.txt` files.
- Extracts embeddings and stores in **ChromaDB** using `chroma_services.py`.

### Chatbot Page
- Allows users to ask questions.
- Retrieves relevant context via `chroma_services.py`.
- Sends context + question to OpenAI using `genai_services.py`.

### Service Layer
- `chroma_services.py`: Stores, queries, and retrieves embeddings.
- `genai_services.py`: Calls OpenAI's completion endpoint.

---

## 🧪 Sample Data

A sample document is included at `data/data.txt` for quick testing.

---

## 📄 Dependencies

Make sure these are included in your `requirements.txt`:

```txt
streamlit
chromadb
openai
python-dotenv
```

---

## 📘 Documentation

- Project Overview: [`README.md`](README.md)
- Setup Guide: [`requirements.txt`](requirements.txt)
- Environment Configs: [`template.env`](template.env)

---

## 📬 Contact

For questions, issues, or contributions, please raise an issue or PR on GitHub.
