# Multimodal Local Chat App

## Overview

The **Multimodal Local Chat App** is an advanced conversational AI application designed to handle text, audio, PDF, and image inputs, providing a seamless and interactive user experience. Built with **Streamlit**, it integrates local models (such as **LLaVA**) for privacy, offering secure and robust multimodal capabilities. Chat sessions are stored in an **SQLite3 database**, allowing users to revisit, manage, and delete conversations.

---

## 🌟 Features

- **Text, Audio, PDF, and Image Support**:
  - **Text**: Users can type queries and get context-aware responses.
  - **Audio**: Upload or record audio queries, which are transcribed into text for processing.
  - **PDF**: Upload PDF documents; the bot extracts, processes, and responds to queries based on the content.
  - **Image**: Upload images, and the app uses **LLaVA** (Language and Vision Assistant) to analyze and respond contextually.
- **Session Management**:
  - Save, view, and delete chat sessions stored in an SQLite3 database.
  - Seamlessly switch between sessions to maintain conversation history.
- **Local Model Inference**:
  - Ensures privacy and fast performance using local models for processing text, audio, PDFs, and images.
- **Streamlit Interface**:
  - User-friendly interface with drag-and-drop file uploads and live audio recording capabilities.

---

## 🛠️ Tech Stack

### Backend:
- **Python**: Core programming language.
- **Streamlit**: Interactive UI for the chatbot.
- **SQLite3**: Database for storing chat sessions.

### AI & ML Libraries:
- **LangChain**: For conversational chains and retrieval logic.
- **LLaVA Model**: For processing image-based inputs and generating responses.
- **Transformers**: For leveraging transformer-based generative and embedding models.
- **SpeechRecognition**: For converting audio queries into text.
- **PyPDF2**: For extracting text from PDF files.

### Additional Tools:
- **Streamlit-Mic-Recorder**: For live audio recording and playback.
- **ChromaDB**: (Optional) For efficient embedding storage and retrieval.

---

## 📂 Folder Structure

```plaintext
├── chat_icons/                # Icons for chat interface
├── chat_sessions/             # SQLite database files for chat sessions
├── chroma_db/                 # Optional vector database for embeddings
├── models/                    # Local AI models for inference
│   ├── llava/                 # LLaVA model for image-based queries
│   ├── model1/                # Other local models for inference
│   ├── model2/
├── src/                       # Core source code
│   ├── audio_handler.py       # Processes and handles audio input
│   ├── chat_api_handler.py    # Backend API logic for managing queries
│   ├── database_operations.py # Manages SQLite3 operations for sessions
│   ├── html_templates.py      # Generates dynamic HTML templates
│   ├── pdf_handler.py         # Handles PDF extraction and chunking
│   ├── image_handler.py       # Handles image-based queries with LLaVA
│   ├── utils.py               # Utility functions for various tasks
│   ├── vectordb_handler.py    # Manages embeddings (optional)
├── .env                       # Environment variables
├── app.py                     # Main Streamlit app file
├── requirements.txt           # Python dependencies
├── config.yaml                # Configuration for text splitting, models, etc.
└── README.md                  # Documentation
```

---

## ⚙️ Application Workflow

1. **User Interaction**:
   - Users interact with the app via the Streamlit UI.
   - Inputs can be text, audio, PDF, or images.

2. **File Upload Handling**:
   - **Text**: Queries are directly processed by the chatbot.
   - **Audio**: Audio files are converted to text using **SpeechRecognition**.
   - **PDF**: Extracts text from documents using **PyPDF2** and processes it into chunks.
   - **Images**: Image inputs are processed using the **LLaVA model**, which combines vision and language understanding to generate contextual responses.

3. **Session Management**:
   - Sessions are stored in an **SQLite3 database**, allowing users to:
     - View previous chats.
     - Switch between sessions.
     - Delete unnecessary sessions.

4. **Local Model Inference**:
   - The app utilizes local models, such as LLaVA for images, ensuring offline and secure inference.

5. **Response Delivery**:
   - Responses are displayed dynamically in the chat interface, designed for a ChatGPT-like experience.

---

## 🔄 Code Flow

1. **PDF Preprocessing**:
   - `pdf_handler.py` extracts and processes text from PDFs into chunks for retrieval and response generation.

2. **Image Processing**:
   - `image_handler.py` leverages the **LLaVA model** to process uploaded images.
   - Outputs are combined with conversational logic to provide relevant responses.

3. **Audio Processing**:
   - `audio_handler.py` transcribes audio queries to text, which are then processed as standard queries.

4. **Session Management**:
   - `database_operations.py` handles CRUD operations for chat sessions in the SQLite3 database.

5. **Frontend Integration**:
   - `app.py` ties together all features, enabling file uploads, chat interactions, and session management via the Streamlit interface.

---

## 🌟 User Interface

### Key Features:
- **Session Selector**:
  - View, select, and delete chat sessions.
- **File Upload**:
  - Drag and drop support for audio, PDFs, and images.
- **Audio Recording**:
  - Live audio recording with playback support.
- **Dynamic Responses**:
  - Context-aware replies based on multimodal inputs.

---

## 🔧 Setup Instructions

### Prerequisites
1. **Python 3.10 or later**
2. **Streamlit** installed globally or in a virtual environment.

### Steps

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-repo
   cd Multimodal-AI-Chat-App
   ```

2. **Install Dependencies**:
   - Create a virtual environment (optional but recommended):
     ```bash
     python -m venv env
     source env/bin/activate  # For Linux/Mac
     env\Scripts\activate     # For Windows
     ```
   - Install required libraries:
     ```bash
     pip install -r requirements.txt
     ```

3. **Run the App**:
   ```bash
   streamlit run app.py
   ```

4. **Access the Interface**:
   Open your browser and navigate to:
   ```
   http://localhost:8501/
   ```

---

## 🚀 Future Enhancements

1. **Advanced Image Understanding**:
   - Enhance the LLaVA model to provide more detailed image-based insights.
2. **Speech-to-Text Improvements**:
   - Integrate more robust libraries for handling noisy or accented audio inputs.
3. **Real-time Collaboration**:
   - Enable multiple users to interact with the bot simultaneously.
4. **Improved PDF Analysis**:
   - Add summary generation for uploaded PDFs.

---

## 🤝 Contributing

Contributions are welcome! Feel free to fork the repository, create a feature branch, and submit a pull request.

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

Enjoy using the **Multimodal Local Chat App**! 🚀 Let us know if you have any feedback or suggestions.