# 📌 SoundNotesAI

**Multilingual Audio Recorder & Summarizer for Meetings and Notes**

> *SoundNotesAI* is a Python-based web application that records, transcribes, and summarizes audio notes in English and Hungarian. The application is built with Flask and Bootstrap and follows the Model-Control-Presenter (MCP) architectural pattern to maintain a clean and modular structure.

---

## ✨ Features

* 🎙 **In-browser Audio Recording** (microphone + system audio)
* 🧠 **Automatic Transcription** using Whisper (supports EN/HU)
* 📝 **Time-stamped Summaries** generated with transformer-based models
* 🔒 **Privacy-by-design**: audio files are deleted after processing
* 🌍 **Language Support**: English and Hungarian
* 📄 **Downloadable Transcripts** in `.txt` or `.pdf` format (planned)
* 📱 **Responsive UI** with Bootstrap 5

---

## 🧱 Architecture – Model-Control-Presenter (MCP)

* **Model** – Handles business logic: audio transcription and summarization
* **Control** – Flask backend: routing, file handling, session management
* **Presenter** – Jinja2 + Bootstrap frontend: user interaction and view rendering

```
[User]
  ↓
[Presenter: Jinja2 templates + JS]
  ↓
[Control: Flask routes / API endpoints]
  ↓
[Model: transcriber.py / summarizer.py]
```

---

## 📂 Project Structure

```
soundnotesai/
├── app/
│   ├── static/              # CSS, JS (Bootstrap, Recorder)
│   ├── templates/           # Jinja2 templates (index, result, error)
│   ├── uploads/             # Temporary audio file storage (auto-deleted)
│   ├── model/
│   │   ├── transcriber.py   # Whisper transcription logic
│   │   ├── summarizer.py    # NLP-based summarization logic
│   ├── control/
│   │   └── routes.py        # Flask routes & controller logic
│   ├── presenter/
│   │   └── views.py         # Template rendering, formatting helpers
│   └── app.py               # Main entry point for Flask app
├── requirements.txt
├── README.md
```

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/soundnotesai.git
cd soundnotesai
```

### 2. Create and activate virtual environment

```bash
python3 -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

Dependencies include:

* `Flask`
* `openai-whisper`
* `transformers`
* `torch`
* `langdetect`
* `pydub`
* `jinja2`
* `flask-bootstrap` *(optional)*

### 4. Run the app

```bash
python app/app.py
```

Visit `http://localhost:5000` in your browser.

---

## 🧠 Technology Stack

| Component        | Tech Used                    |
| ---------------- | ---------------------------- |
| Web Framework    | Flask (Python)               |
| Frontend UI      | HTML5, Bootstrap 5           |
| Templates        | Jinja2                       |
| Audio API        | MediaRecorder (JS)           |
| Transcription    | Whisper (OpenAI)             |
| Summarization    | HuggingFace Transformers     |
| Language Support | English 🇬🇧, Hungarian 🇭🇺 |

---

## 📄 Workflow Overview

1. User records or uploads an audio file via browser
2. Flask receives and stores the audio temporarily
3. Whisper transcribes the audio with timestamps
4. Transformer model generates a concise summary
5. Transcript and summary are shown on the result page
6. Audio file is securely deleted from the server

---

## 🔐 Privacy and Security

* No audio data is permanently stored
* All temporary files are auto-deleted after processing
* HTTPS is strongly recommended for production
* CORS protection enabled for the API

---

## 📌 TODO / Roadmap

* [ ] PDF export for transcript and summary
* [ ] Optional speaker diarization
* [ ] WebSocket support for real-time transcription
* [ ] LLM-based summarization refinement (OpenAI API or local LLMs)
* [ ] Language-switchable UI (EN/HU)

---

## 🧪 Testing

To run unit tests:

```bash
pytest tests/
```

(coming soon – includes tests for `transcriber.py` and `summarizer.py`)

---

## 📬 Contact

For feedback, bugs or feature requests:

* GitHub Issues: [create new](https://github.com/yourusername/soundnotesai/issues)
* Email: `youremail@example.com`

---

## 📄 License

MIT License. See `LICENSE` file for details.

---
