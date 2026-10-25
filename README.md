# Sloth Mode

Sloth Mode is a lightweight local document summarizer powered by Ollama and Streamlit. It reads `.txt` files from your personal documents folder, summarizes them with a local AI model, and lets you review or download the result.

## What it does

- Scans `~/sloth-mode/documents` for text files
- Shows a preview of the selected document
- Sends the document to a local Ollama model for summarization
- Produces a concise summary with:
  - Quick summary
  - Important points
  - Action items and deadlines
- Lets you download the final summary as a text file

## Requirements

- Python 3.10+
- Ollama installed and running locally
- A model available in Ollama, such as `qwen2.5:3b`

## Setup

1. Install Python dependencies:

   ```bash
   pip install -r requirements.txt
   ```

2. Make sure Ollama is running:

   ```bash
   ollama serve
   ```

3. Pull the model used by the app if needed:

   ```bash
   ollama pull qwen2.5:3b
   ```

4. Add your text documents to:

   ```bash
   ~/sloth-mode/documents
   ```

   Use `.txt` files.

## Run the app

### Streamlit UI

```bash
streamlit run ui.py
```

### CLI version

```bash
python app.py
```

## Notes

- The app expects to talk to Ollama at `http://localhost:11434/api/generate`.
- If Ollama is not running, the summarization step will fail with a connection error.
- The project is designed for local, private use and does not require cloud services.
