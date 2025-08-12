# 🏛️ ADGM Compliance Review Tool

A **Streamlit-based AI application** that reviews legal documents for **ADGM (Abu Dhabi Global Market)** compliance.  
It uses **Azure OpenAI (GPT-4o + Embeddings)** for Retrieval-Augmented Generation (RAG) against uploaded **reference PDFs**,  
classifies uploaded `.docx` legal documents, detects compliance issues, annotates them with inline suggestions,  
and outputs a **structured JSON report**.

---

## 🚀 Features
- **Upload ADGM reference PDFs** (used as knowledge base).
- **Upload legal `.docx` documents** for review.
- Automatically **classifies document type** based on content.
- Uses **RAG with Azure OpenAI** to detect compliance issues.
- Inserts **highlighted inline comments** at relevant sections in `.docx`.
- Detects **missing required documents** for the chosen ADGM process.
- Generates **clean JSON output** in the format:

```json
{
  "process": "Company Incorporation",
  "documents_uploaded": 4,
  "required_documents": 5,
  "missing_document": "Register of Members and Directors",
  "issues_found": [
    {
      "document": "Articles of Association",
      "section": "Clause 3.1",
      "issue": "Jurisdiction clause does not specify ADGM",
      "severity": "High",
      "suggestion": "Update jurisdiction to ADGM Courts."
    }
  ]
}
```


📸 Screenshots
Upload & Run Review
<img width="1919" height="929" alt="image" src="https://github.com/user-attachments/assets/b255a0e7-a51d-43b3-9383-9d9513809567" />


JSON Output
<img width="1919" height="933" alt="image" src="https://github.com/user-attachments/assets/dc1e0382-37e8-4c82-8a8c-fec63c06ac4d" />
<img width="1918" height="925" alt="image" src="https://github.com/user-attachments/assets/f217339e-9757-4808-b6f5-1b72eb825d2a" />



Reviewed DOCX with Comments
<p align="center">
  <img width="775" height="816" alt="image" src="https://github.com/user-attachments/assets/1ac835a9-a9f2-40d7-8dba-31cf9544a700" />
</p>





📂 Project Structure

📁 ADGM-Compliance-Review

│── code.py              # Main Streamlit application

│── requirements.txt    # Python dependencies

│── .env.example        # Environment variable template

│── README.md           # This file





⚙️ Setup Instructions


1️⃣ Clone the Repository

  git clone https://github.com/yourusername/ADGM-Compliance-Review.git
  cd ADGM-Compliance-Review


2️⃣ Create Virtual Environment
  
  python -m venv venv
  source venv/bin/activate       # Mac/Linux
  venv\Scripts\activate          # Windows


3️⃣ Install Dependencies

  pip install -r requirements.txt


4️⃣ Configure Environment Variables

Create a .env file in the root folder:
  AZURE_OPENAI_API_KEY=your_azure_openai_api_key
  AZURE_OPENAI_API_BASE=https://your-endpoint.cognitiveservices.azure.com/
  AZURE_OPENAI_API_VERSION=2024-12-01-preview
  AZURE_OPENAI_EMBEDDING_DEPLOYMENT=text-embedding-3-small
  AZURE_OPENAI_CHAT_DEPLOYMENT=gpt-4o


▶️ Running the App

  streamlit run app.py







🖥 Usage

Upload ADGM Reference PDFs
These serve as the compliance rulebook.

Upload Legal .docx Files
These are the documents you want reviewed.

Click "Run Review"

Documents are classified

Compliance issues are detected

Missing required documents are identified

Inline comments are added

JSON summary is generated

Download Reviewed .docx Files or copy the JSON Report.






📦 Requirements

Python 3.9+

Streamlit

LangChain

Azure OpenAI access




