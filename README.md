# AI Call Agent - Twilio + ElevenLabs

An AI-powered phone call agent that makes outbound calls, converses naturally using AI, and speaks with a realistic voice.

## Features

- **Outbound Calls** — Initiate calls via Twilio
- **AI Conversation** — Groq/OpenAI for intelligent responses
- **Realistic Voice** — ElevenLabs text-to-speech
- **Speech Input** — Twilio speech recognition for real-time conversation
- **Customizable** — Set customer name, phone, and business context

## Tech Stack

- Python / Flask
- Twilio (voice calls + speech recognition)
- Groq / OpenAI (LLM)
- ElevenLabs (TTS)
- ngrok (tunneling for local dev)

## Setup

### 1. Install dependencies

```bash
pip install flask twilio openai groq requests flask-cors
```

### 2. Configure API keys

Edit `TwilioElevenLabsAIAgent.py` and replace:

```python
account_sid = 'YOUR_TWILIO_SID'
auth_token = 'YOUR_TWILIO_TOKEN'
openai_api_key = 'YOUR_OPENAI_KEY'
ELEVENLABS_API_KEY = 'YOUR_ELEVENLABS_KEY'
```

### 3. Start ngrok

```bash
ngrok http 5000
```

Update `app_public_url` with your ngrok URL.

### 4. Run

```bash
python TwilioElevenLabsAIAgent.py
```

## API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/start-call` | POST | Initiate a call with customer details |
| `/gather` | GET/POST | Gather speech input from caller |
| `/process-speech` | POST | Process speech and respond with AI |

## Usage

```bash
curl -X POST http://localhost:5000/start-call \
  -H "Content-Type: application/json" \
  -d '{"customer_name": "Ahmed", "customer_phonenumber": "+212600000000", "customer_businessdetails": "Web development services"}'
```

## License

MIT
