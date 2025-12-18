# Code Companion

Code Companion is a conversational coding assistant that helps learners discover practice problems through a chat-first interface and then work through them in an integrated workspace. The presentation introduces the motivation (navigating overwhelming problem lists), the chat-centric user flow, and the planned IDE-like solving experience including problem generation, test execution, and competitive modes.

## Technical Architecture
- **Frontend:** React + TypeScript (Vite) app in `ChatBoxUI/` that provides authentication, chat, message history, and attachment-ready UI components.
- **Backend:** Flask API in `flask/` exposing chat and auth endpoints, brokering requests to the OpenAI API via an `/api/chat` route.
- **Data flow:** Browser UI → Flask server → OpenAI GPT model; responses stream back to the UI, which maintains session history and status indicators.
- **Environment:** CORS enabled for local development; .env controls secrets such as `OPENAI_API_KEY`.

## Reproducible Installation
### Prerequisites
- Node.js 18+
- Python 3.8+
- An OpenAI API key

### Backend setup
```bash
cd flask
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
cp env.example .env   # then set OPENAI_API_KEY in the file
python app.py
```
The server runs on `http://localhost:5000`.

### Frontend setup
Open a new terminal:
```bash
cd ChatBoxUI
npm install
npm run dev
```
The UI is available at `http://localhost:3000` and will call the Flask backend on port 5000.

## Project Overview for Presentations
- **Goal:** Reduce friction in finding tailored coding problems by starting with a natural-language chat.
- **Experience:** Users describe the problem they want, receive a generated prompt with edge cases, and transition into an IDE-style layout to run and submit solutions.
- **Roadmap highlights:** Chat-driven problem discovery, code execution sandbox, submission history, and competitive modes.

## Group Members & Roles
- **Maya Swaminathan** — Frontend lead (UI flows, TypeScript components).
- **Raaghav Pillai** — Backend lead (Flask services, API integration).
- **sharngi2** — Authentication and API glue between frontend and backend.
- **varni03** — Testing, documentation, and developer experience.

## Repository Structure
- `ChatBoxUI/` – React + TypeScript frontend.
- `flask/` – Python Flask backend with OpenAI integration.
- `SETUP.md` and `INTEGRATION_GUIDE.md` – Additional setup and architecture notes.
