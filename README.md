# Dashboard

A modern, full-stack dashboard for SAP Ariba event analysis and conversational AI insights.

## Overview

This project provides a dashboard to fetch, view, and analyze SAP Ariba event data, with a conversational AI assistant powered by Gemini 2.5 Flash. Users can fetch event data by Task ID, view it in JSON, generate AI summaries, and chat with the data for insights and recommendations.

## Features
- Fetch SAP Ariba event data by Task ID
- View event, workspace, and RFX document data in JSON format
- Download AI-generated summaries
- Conversational AI chat (context-aware, multi-turn) using Gemini 2.5 Flash
- Draggable, resizable chat and summary modals
- Responsive, modern UI with infinite scroll

## Project Structure
- `midnight-data-portal/` — Frontend (React + Vite + Tailwind)
- `server.js` — Backend (Express, Ariba API, Gemini integration)

## Setup Instructions

### 1. Clone the Repository
```sh
git clone <your-repo-url>
cd SAP_ARIBA_UI
```

### 2. Backend Setup
- Ensure Node.js 18+ is installed.
- Create a `.env` file in the project root with the following variables:

```
ARIBA_CLIENT_ID=your_ariba_client_id
ARIBA_CLIENT_SECRET=your_ariba_client_secret
ARIBA_API_KEY=your_ariba_api_key
ARIBA_REALM=your_ariba_realm
ARIBA_OAUTH_URL=https://your-ariba-oauth-url
ARIBA_BASE=https://your-ariba-base-url
GEMINI_API_KEY=your_gemini_api_key
PORT=3001
```

- Install backend dependencies:
```sh
npm install express cors axios dotenv @google/generative-ai
```
- Start the backend:
```sh
node server.js
```

### 3. Frontend Setup
- Go to the frontend directory:
```sh
cd midnight-data-portal
```
- Install frontend dependencies:
```sh
npm install
```
- Start the frontend:
```sh
npm run dev
```
- Open [http://localhost:5173](http://localhost:5173) in your browser.

## Usage
1. **Fetch Data:** Click "Fetch Data" and enter a valid SAP Ariba Task ID. The dashboard will display the event data in JSON format.
2. **AI Summary:** (If enabled) Generate and download an AI summary of the data.
3. **Chat with Data:** Click "Chat with Data" to open the conversational AI assistant. Ask questions about the data; the chat is context-aware and multi-turn.

## Environment Variables
- All backend secrets and API keys are managed in the `.env` file at the project root.
- The frontend does not require special environment variables for API access (uses hardcoded backend URL).

## Troubleshooting
- **Failed to fetch:** Ensure both backend (`node server.js`) and frontend (`npm run dev`) are running. Check `.env` values.
- **CORS errors:** The backend uses CORS; ensure both servers are on the same machine/network.
- **Gemini/Ariba errors:** Check your API keys and credentials in `.env`.
- **Port conflicts:** Change `PORT` in `.env` or frontend API URL if needed.

## Customization
- Update the UI, prompts, or backend logic as needed for your workflow.
- To change the AI model, update the model name in `server.js`.

## License
MIT (or your chosen license) 