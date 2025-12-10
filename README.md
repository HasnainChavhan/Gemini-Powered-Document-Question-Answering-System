📄 Gemini-Powered Document Question Answering System
<p align="center"> <img src="https://img.shields.io/badge/Version-1.0-blue?style=for-the-badge" /> <img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python" /> <img src="https://img.shields.io/badge/Streamlit-App-FF4B4B?style=for-the-badge&logo=streamlit" /> <img src="https://img.shields.io/badge/Gemini-API-4285F4?style=for-the-badge&logo=google" /> <img src="https://img.shields.io/badge/Database-SQLite-003B57?style=for-the-badge&logo=sqlite" /> <img src="https://img.shields.io/badge/LLM-Gemini_Pro-brightgreen?style=for-the-badge" /> <img src="https://img.shields.io/badge/Status-Active-brightgreen?style=for-the-badge" /> </p>
📌 Overview

The Gemini Document Question Answering System is an AI assistant that reads documents, extracts knowledge, and answers complex questions using Google Gemini models.

This system supports:

📄 Multi-document upload (PDF/TXT)

🧩 Semantic chunking

🔢 Embedding-based RAG retrieval

🤖 Gemini-Pro reasoning

🔍 Citation-backed answers

🎤 Voice input

🔊 Voice output

🗂 Query logging + analytics

🖥 Streamlit-based modern UI

Perfect for:

✔ Legal workflows
✔ Academic research
✔ Enterprise documentation
✔ Compliance analysis
✔ Knowledge extraction

✨ Key Features
🧠 Gemini-Powered Reasoning

High accuracy using Gemini-Pro and Gemini-Pro-Vision models.

📂 Multi-Document Upload

Supports multiple PDFs/TXT files at once.

🔍 RAG + Embeddings

Retrieves only the most relevant segments using embeddings + cosine similarity.

🎤 Voice Input & 🔊 Output

Hands-free AI interaction.

🛡 SQLite Database

Stores embeddings, logs, and metadata.

🔐 Gemini API Setup
1️⃣ Get Your API Key

👉 https://aistudio.google.com/app/apikey

2️⃣ Create .env File
GENAI_API_KEY=your_api_key_here

3️⃣ Load API Key in Code
import os
from dotenv import load_dotenv
import google.generativeai as genai

load_dotenv()
genai.configure(api_key=os.getenv("GENAI_API_KEY"))

🧩 System Architecture (Fixed Mermaid Diagram)
flowchart TB

A([Upload PDF/TXT]) --> B[Document Loader]
B --> C[Text Cleaning & Normalization]
C --> D[Chunking into Semantic Units]

D --> E[Generate Embeddings]
E --> F[Store Embeddings + Metadata in SQLite]

F --> G[Semantic Retriever - Cosine Similarity]
G --> H[Gemini LLM - RAG Pipeline]
H --> I[Generate Answer with Citations]

I --> J[Voice Output - Text to Speech]
A --> K[Voice Input - Speech to Text]

classDef process fill:#61A5FF,stroke:#1A4C8F,color:white;
classDef db fill:#7ED957,stroke:#2E8B2D,color:black;
classDef voice fill:#FFB347,stroke:#A65B00,color:white;

class B,C,D,E process;
class F,G,H process;
class J,K voice;

🔁 RAG Pipeline (Fixed Mermaid Diagram)
flowchart TD

A[User Query] --> B[Embed Query]
B --> C[Search Similar Chunks in SQLite]
C --> D[Retrieve Context]

D --> E[Build Prompt with Context + Query]
E --> F[Gemini LLM - generate_content\(\)]
F --> G[Final Answer + Citations]

classDef step fill:#61A5FF,stroke:#1A4C8F,color:white;
classDef llm fill:#4285F4,stroke:#0F3BA3,color:white;

class A,B,C,D,E step;
class F,G llm;

🗂 Project Structure
Gemini-Document-QA/
│── app.py                        # Main Streamlit app
│── rag_engine.py                 # RAG pipeline logic
│── embedding_utils.py            # Chunking + embeddings
│── voice_functions.py            # Speech-to-text + TTS
│── database.py                   # SQLite helper
│── app.db                        # Local database
│── requirements.txt              # Dependencies
│── .env                          # Environment variables
│
├── uploaded_docs/                # User-uploaded files
├── pages/                        # Additional UI screens
└── models/                       # Optional embedding models

⚙️ Installation
1️⃣ Clone Repo
git clone https://github.com/your-username/Gemini-Document-QA.git
cd Gemini-Document-QA

2️⃣ Create Virtual Environment
python -m venv venv
source venv/bin/activate
# Windows:
venv\Scripts\activate

3️⃣ Install Dependencies
pip install -r requirements.txt

4️⃣ Add Gemini API Key

Create .env file:

GENAI_API_KEY=your_key_here

5️⃣ Run App
streamlit run app.py


Open in browser:
👉 http://localhost:8501

🧪 Example Usage
Step 1 — Upload Document

Upload Contract.pdf

Step 2 — Ask a Question

“What are the termination clauses?”

Step 3 — Result

✔ Extracts relevant document chunks
✔ Processes them through Gemini-Pro
✔ Provides citations
✔ Optional audio output

🛠 Tech Stack
Layer	Technology
UI	Streamlit
LLM	Gemini-Pro / Gemini-Pro-Vision
Embeddings	Gemini Embeddings
Vector Search	SQLite + Cosine Similarity
Backend	Python
Voice	SpeechRecognition + TTS
Parsing	PyPDF2, LangChain loaders
🗺 Roadmap

 Highlight referenced text inside PDF

 Multi-user authentication

 Admin dashboard

 Chat history export

 GCP/Railway/Render deployment

 Hybrid mode → Gemini + Local LLM

🛡 License

MIT License.

👤 Author — Hasnain Chavhan

AI & Data Science Engineer
Machine Learning • GenAI • MLOps

🌟 Support

If you found this project helpful, please ⭐ the repo!
Your support motivates future updates. 🚀
