# Buildathon Chat Server

A chat server built with Bun that integrates with OpenAI API to provide chat functionality for the fitness tracking app.

## Setup

1. Install dependencies:
```bash
bun install
```

2. Create a `.env` file in the server directory:
```bash
OPENAI_API_KEY=your_openai_api_key_here
PORT=3001
```

3. Run the server:
```bash
bun run dev
```

Or for production:
```bash
bun run start
```

## API Endpoints

- `POST /chat` - Send chat messages and get AI responses with personalized fitness suggestions
  - Request body: 
    ```json
    {
      "messages": [{ "role": "user" | "assistant", "content": "string" }],
      "stepCount": number (optional),
      "goal": number (optional),
      "avatarState": "fat" | "normal" | "fit" (optional)
    }
    ```
  - Response: `{ message: string, role: 'assistant' }`
  - The server uses step count, goal, and avatar state to provide personalized fitness advice and suggestions

- `GET /health` - Health check endpoint

## Environment Variables

- `OPENAI_API_KEY` (required) - Your OpenAI API key
- `PORT` (optional) - Server port, defaults to 3001

## Frontend Integration

The frontend expects the chat API to be available at `http://localhost:3001` by default, or you can set `VITE_CHAT_API_URL` in the client's `.env` file.
