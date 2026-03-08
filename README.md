# Gemini Chatbot (Streamlit)

A simple web-based chatbot built with Streamlit that uses Google's Gemini API to answer user questions in a chat-style interface.

## Features

- Streamlit web UI
- Real-time chat with Gemini
- Conversation history displayed in the app
- API key loaded securely from a `.env` file

---

## Requirements

- Python 3.9+ (recommended)
- pip (Python package manager)
- A Google Gemini (Generative AI) API key

Python dependencies are listed in `requirements.txt`, including:

- `streamlit`
- `google-generativeai`
- `python-dotenv`

---

## Setup

1. **Clone or open the project**

   Make sure you are in the project directory:

   ```powershell
   cd "c:\Users\sahil\OneDrive\Desktop\semester 5\notes_of_generative_Ai\gemini_chat_bot"
   ```

2. **Create and activate a virtual environment (recommended)**

   ```powershell
   python -m venv .venv
   .\.venv\Scripts\activate
   ```

3. **Install dependencies**

   ```powershell
   pip install -r requirements.txt
   ```

---

## Configure the Gemini API Key

1. Get your API key from Google AI Studio (Gemini).
2. Create a `.env` file in the project root (if it does not already exist).
3. Add the following line to `.env`:

   ```env
   GOOGLE_API_KEY="your_real_api_key_here"
   ```

The app reads this key via:

```python
from dotenv import load_dotenv
load_dotenv()
...
genai.configure(api_key=os.getenv("GOOGLE_API_KEY"))
```

---

## Running the App

From the project directory, with the virtual environment activated:

```powershell
streamlit run chat.py
```

Streamlit will show a local URL in the terminal (for example: `http://localhost:8501`). Open this URL in your browser.

---

## Using the Chatbot

- Type your question in the **“Ask a question:”** text box.
- Click **“Ask question”**.
- Your question and the bot’s response will be appended to the **Chat History**.

---

## Project Structure

```text
gemini_chat_bot/
  chat.py          # Main Streamlit app
  requirements.txt # Python dependencies
  .env             # Environment variables (API key)
  README.md        # Project documentation
```

---

## Troubleshooting

- **`ModuleNotFoundError`**: Ensure you ran `pip install -r requirements.txt` inside the virtual environment.
- **API key errors or empty responses**:
  - Check that `.env` is in the project root.
  - Verify `GOOGLE_API_KEY` is set correctly (no extra spaces, valid key).
- **Streamlit not found**:
  - Install it manually: `pip install streamlit`.
.
