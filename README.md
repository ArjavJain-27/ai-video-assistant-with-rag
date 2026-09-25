# 🎥 AI Video Assistant with RAG

An AI-powered video assistant that transforms videos and meeting recordings into searchable, interactive knowledge.

The application can **transcribe video/audio, generate summaries, extract action items, and answer questions about the video using Retrieval-Augmented Generation (RAG).**

## ✨ Features

* 🎙️ **Video/Audio Transcription**

  * Extracts speech from uploaded videos or YouTube videos.
  * Converts spoken content into text.

* 📝 **AI Summarization**

  * Generates concise summaries from long video or meeting transcripts.

* ✅ **Action Item Extraction**

  * Identifies important tasks, decisions, and follow-up actions from conversations.

* 💬 **Chat with Your Video**

  * Ask questions about the video content.
  * Get answers based on the actual transcript.

* 🔎 **RAG-Based Question Answering**

  * Transcript is processed and stored as searchable chunks.
  * Relevant context is retrieved before generating an answer.

* 📚 **Context-Aware Responses**

  * The assistant uses retrieved transcript content instead of relying only on the language model's general knowledge.

* 🌐 **Streamlit Interface**

  * Simple web interface for interacting with the assistant.

---

## 🧠 How It Works

```text
                Video / YouTube URL
                         │
                         ▼
                ┌─────────────────┐
                │ Audio Extraction│
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │   Transcription │
                │     (Whisper)   │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ Text Processing │
                │  & Chunking     │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ Vector Database │
                │    (ChromaDB)   │
                └────────┬────────┘
                         │
                         ▼
                  User Question
                         │
                         ▼
                ┌─────────────────┐
                │ Semantic Search │
                │   + Retrieval   │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │       LLM       │
                │ Context + Query │
                └────────┬────────┘
                         │
                         ▼
                  AI Response
```

---

## 🛠️ Tech Stack

| Technology | Purpose                              |
| ---------- | ------------------------------------ |
| Python     | Core application                     |
| Streamlit  | Web interface                        |
| Whisper    | Speech-to-text transcription         |
| LangChain  | RAG pipeline and document processing |
| ChromaDB   | Vector database                      |
| Mistral    | Large Language Model                 |
| yt-dlp     | YouTube media extraction             |
| FFmpeg     | Audio/video processing               |

---

## 📂 Project Structure

```text
ai-video-assistant-with-rag/
│
├── core/
│   ├── ...
│   └── Core AI / RAG components
│
├── utils/
│   ├── ...
│   └── Utility functions
│
├── app.py
│   └── Streamlit application
│
├── main.py
│   └── Application entry point / processing logic
│
├── requirements.txt
│   └── Python dependencies
│
├── packages.txt
│   └── System-level packages required for deployment
│
├── .env.example
│   └── Environment variable template
│
├── .gitignore
│
└── README.md
```

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/ArjavJain-27/ai-video-assistant-with-rag.git
cd ai-video-assistant-with-rag
```

### 2. Create a virtual environment

Using Python:

```bash
python -m venv .venv
```

Activate it on Windows:

```powershell
.venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

Or, if you use `uv`:

```bash
uv pip install -r requirements.txt
```

---

## 🔐 Environment Variables

Create a `.env` file based on `.env.example`.

Example:

```env
MISTRAL_API_KEY=your_mistral_api_key
```

> **Important:** Never commit your real API keys to GitHub.

The `.env` file should remain inside `.gitignore`.

---

## 🎬 Running the Application

Start the Streamlit application:

```bash
streamlit run app.py
```

The application will open in your browser.

You can then provide a supported video/YouTube source and interact with the generated transcript.

---

## 💡 Example Use Cases

### 🎓 Students

Upload a lecture and ask:

> "What are the main concepts explained in this lecture?"

### 💼 Meetings

Process a meeting recording and ask:

> "What action items were assigned?"

### 📺 YouTube Videos

Provide a YouTube video and ask:

> "Summarize the key points discussed in this video."

### 📚 Learning

Ask questions such as:

> "Explain the topic discussed between these sections."

---

## 🔍 RAG Pipeline

The project follows a Retrieval-Augmented Generation workflow:

### 1. Ingestion

The video/audio source is processed and converted into text.

### 2. Transcription

Speech is converted into a transcript using Whisper.

### 3. Chunking

The transcript is divided into smaller chunks so that relevant sections can be retrieved efficiently.

### 4. Embeddings

Text chunks are converted into vector representations.

### 5. Vector Storage

The embeddings are stored in ChromaDB.

### 6. Retrieval

When the user asks a question, the system searches for the most relevant transcript chunks.

### 7. Generation

The retrieved context is provided to the LLM along with the user's question.

### 8. Response

The model generates an answer grounded in the retrieved video content.

---

## 🚀 Deployment

The application can be deployed using platforms that support Streamlit applications.

For deployment, make sure that:

1. All Python dependencies are listed in `requirements.txt`.
2. Required system packages are listed in `packages.txt`.
3. API keys are configured as deployment environment variables.
4. `.env` and other secrets are **not** uploaded to the repository.

---

## 🔒 Security

Never expose API keys in:

* Source code
* GitHub commits
* README files
* Screenshots
* Frontend code

Use environment variables instead:

```env
MISTRAL_API_KEY=your_api_key
```

---

## 📌 Future Improvements

* [ ] Timestamp-based answers
* [ ] Speaker identification
* [ ] Multi-video knowledge base
* [ ] Conversation history
* [ ] Better citation/source references
* [ ] Support for additional LLM providers
* [ ] Improved transcript search
* [ ] User authentication
* [ ] Persistent vector storage
* [ ] Multiple file format support

---

## 👨‍💻 Author

**Arjav Jain**

Computer Science Engineering Student | AI & Backend Developer

* GitHub: https://github.com/ArjavJain-27
* LinkedIn: https://www.linkedin.com/in/arjav-jain-af/
* LeetCode: https://leetcode.com/u/Arjavjain-af/

---

## ⭐ Support

If you find this project useful, consider giving the repository a ⭐ on GitHub.

---

## 📄 License

This project is available for educational and personal use.
