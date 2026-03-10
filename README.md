# IBM Voice Assistant — Powered by OpenAI GPT & Watson Speech

A full-stack voice assistant web application built with Flask, OpenAI's GPT model, and IBM Watson's Speech-to-Text and Text-to-Speech services. Developed as part of IBM's AI Developer course on Cognitive Class.

![Voice Assistant Screenshot](1773110013722_image.png)

## Overview

This project creates a virtual assistant that can:
- Accept voice input from the user via microphone
- Convert speech to text using IBM Watson Speech-to-Text
- Send the transcribed text to OpenAI's GPT model for a response
- Convert the GPT response back to speech using IBM Watson Text-to-Speech
- Play the audio response back to the user

The app also supports typed text input and includes both light and dark mode.

## Features

- Voice input via microphone recording
- Speech-to-Text powered by IBM Watson
- AI responses powered by OpenAI GPT
- Text-to-Speech powered by IBM Watson
- Light/dark mode toggle
- Choice of voice for audio responses
- Responsive frontend with Bootstrap, Font Awesome, and jQuery

## Technologies Used

- **Python** / **Flask** — backend server
- **OpenAI API** — GPT model for generating responses
- **IBM Watson Speech-to-Text** — transcribes user voice input
- **IBM Watson Text-to-Speech** — converts AI responses to audio
- **HTML / CSS / JavaScript** — frontend interface
- **Bootstrap** — UI styling
- **Docker** — containerized deployment

## Project Structure

```
chatapp-with-voice-and-openai/
├── server.py
├── worker.py
├── requirements.txt
├── Dockerfile
├── certs/
│   └── rootCA.crt
├── static/
│   ├── script.js
│   └── style.css
└── templates/
    └── index.html
```

## Installation & Setup

1. Clone the repository:
```bash
git clone https://github.com/awjenson/IBM_chatapp-with-voice-and-openai.git
cd IBM_chatapp-with-voice-and-openai
```

2. Set your OpenAI API key as an environment variable:
```bash
export OPENAI_API_KEY=your_api_key_here
```

3. Build the Docker image:
```bash
docker build . -t voice-chatapp-powered-by-openai
```

4. Run the container:
```bash
docker run -p 8000:8000 voice-chatapp-powered-by-openai
```

5. Visit `http://127.0.0.1:8000` in your browser.

## How It Works

1. The user types or speaks a message in the web interface
2. If voice input, the audio is sent to the `/speech-to-text` endpoint and transcribed via IBM Watson
3. The transcribed text is sent to the `/process-message` endpoint
4. Flask passes the message to OpenAI's GPT model and receives a response
5. The response text is converted to audio via IBM Watson Text-to-Speech
6. Both the text and audio response are returned to the frontend and played back to the user

## Acknowledgements

- Built as part of the [IBM AI Developer course](https://cognitiveclass.ai/) on Cognitive Class
- Project outline provided by [IBM Developer Skills Network](https://github.com/ibm-developer-skills-network/bkrva-chatapp-with-voice-and-openai-outline)
- Speech services by [IBM Watson](https://www.ibm.com/watson)
- AI responses by [OpenAI](https://openai.com)
