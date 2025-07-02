# ZeroVoice: Real-time Speech-to-Speech Communication

ZeroVoice is a real-time speech-to-speech communication application built with modern web technologies. It allows users to interact with an AI voice assistant through natural language, featuring voice activity detection, speech-to-text transcription, large language model integration for responses, and text-to-speech synthesis.

## Features

*   **Real-time Speech-to-Speech**: Seamless bidirectional audio communication.
*   **Voice Activity Detection (VAD)**: Intelligently detects speech segments using Silero VAD.
*   **Automatic Speech Recognition (ASR)**: Transcribes user's speech to text using HuggingFace Transformers.js (Whisper base model).
*   **Large Language Model (LLM) Integration**: Generates conversational responses using the SmolLM2-1.7B-Instruct model.
*   **Text-to-Speech (TTS)**: Synthesizes AI responses into natural-sounding speech using KokoroTTS.
*   **Responsive UI**: Built with React and Tailwind CSS for a modern and adaptive user experience.
*   **Voice Selection**: Users can choose from various available voices for the AI assistant.
*   **Call Timer**: Tracks the duration of the conversation.

## Technologies Used

*   **Frontend**:
    *   [React](https://react.dev/): A JavaScript library for building user interfaces.
    *   [Tailwind CSS](https://tailwindcss.com/): A utility-first CSS framework for rapid UI development.
    *   [Vite](https://vitejs.dev/): A fast frontend build tool.
*   **Speech Processing & AI**:
    *   [@huggingface/transformers.js](https://huggingface.co/docs/transformers.js/index): For VAD (Silero VAD), ASR (Whisper), and LLM (SmolLM2-1.7B-Instruct).
    *   [KokoroTTS](https://github.com/huggingface/kokoro-js): For high-quality text-to-speech synthesis.
    *   Web Audio API & AudioWorklets: For real-time audio processing in the browser.

## Project Structure

*   `src/App.jsx`: The main React component, handling UI, audio stream management, and state logic.
*   `src/worker.js`: A Web Worker responsible for handling speech processing (VAD, ASR, LLM, TTS) to offload heavy computations from the main thread.
*   `src/constants.js`: Defines various constants used across the application, especially for audio processing parameters.
*   `src/play-worklet.js`: AudioWorklet for managing audio playback buffering.
*   `src/vad-processor.js`: AudioWorklet for Voice Activity Detection processing.
*   `public/`: Static assets like `logo.png`.

## Setup and Installation

To get the project up and running on your local machine, follow these steps:

1.  **Clone the repository**:
    ```bash
    git clone https://github.com/your-repo/zerovoice.git # Replace with actual repo URL if available
    cd zerovoice
    ```

2.  **Install dependencies**:
    ```bash
    npm install
    ```

3.  **Start the development server**:
    ```bash
    npm run dev
    ```
    This will typically start the application on `http://localhost:5173` (or another available port).

4.  **Open in your browser**:
    Navigate to the URL provided by Vite in your web browser.

5.  **Demo**:
    You can try out a live demo here: [https://biswatma.github.io/zerovoice/](https://biswatma.github.io/zerovoice/)

## Usage

*   Once the application loads, ensure the "Loading..." message disappears and "Ready!" is displayed, indicating that all AI models have been loaded.
*   Click the "Start call" button to begin interaction. You may be prompted to grant microphone access.
*   Speak naturally, and the AI assistant will respond in real-time.
*   You can select different voices for the AI assistant using the dropdown menu.
*   To end the conversation, click the "End call" button.

## Linting

This project uses ESLint for code quality and consistency. You can run the linter using:

```bash
npm run lint
