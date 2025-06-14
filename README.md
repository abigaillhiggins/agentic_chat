# Emotional Voice Response System

This project implements an interactive voice-based conversational agent using LangChain, Vosk for speech-to-text, and ElevenLabs for text-to-speech. The system processes voice input, generates responses using an LLM, and converts the responses to natural-sounding speech.

## Features

- Real-time speech-to-text using Vosk
- Natural, expressive text-to-speech using ElevenLabs (emotion-aware)
- LLM-based emotion detection for each sentence
- Conversational memory using LangChain
- Web search capabilities using DuckDuckGo
- Interactive voice-based conversation

## Setup

1. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Install ffmpeg (includes ffplay, required for TTS playback):
- **macOS:**
  ```bash
  brew install ffmpeg
  ```
- **Linux (Debian/Ubuntu):**
  ```bash
  sudo apt update && sudo apt install ffmpeg
  ```
- **Other Linux distros:**
  Use your package manager to install `ffmpeg`.

4. Create a .env file:
```bash
cp .env.template .env
```

5. Add your API keys to the .env file:
- OPENAI_API_KEY: Your OpenAI API key
- ELEVENLABS_API_KEY: Your ElevenLabs API key

6. Download Vosk model:
```bash
# Download the small model for English
wget https://alphacephei.com/vosk/models/vosk-model-small-en-us-0.15.zip
unzip vosk-model-small-en-us-0.15.zip
```

## Usage

Run the main script:
```bash
python main2.py
```

The system will:
1. Listen for voice input
2. Convert speech to text using Vosk
3. Process the text through the LangChain agent
4. Generate a response
5. Detect the emotion of each sentence in the response using an LLM
6. Convert each sentence to expressive speech using ElevenLabs, matching the detected emotion
7. Play the expressive response through your speakers

## Requirements

- Python 3.8+
- Microphone for voice input
- Speakers for voice output
- Internet connection for API access

## Note

Make sure your microphone is properly configured and working before running the script. The system will automatically detect and use your default microphone. 