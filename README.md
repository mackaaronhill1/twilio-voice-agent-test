# Twilio Voice Agent Test Project

This project provides a testing environment for the Twilio Voice Agent implementation.

## Setup

1. Clone the repository
2. Create a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: .\venv\Scripts\activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Copy `.env.example` to `.env` and fill in your Twilio credentials

## Running Tests

Run all tests:
```bash
pytest
```

Run tests with coverage:
```bash
pytest --cov=voice_agent
```

## Local Development

1. Start the Flask application:
   ```bash
   python -m voice_agent.app
   ```

2. Use ngrok to create a public URL:
   ```bash
   ngrok http 5000
   ```

3. Update your Twilio webhook URL with the ngrok URL

## Making Test Calls

Use curl to test the make_call endpoint:
```bash
curl -X POST http://localhost:5000/make_call \
  -H "Content-Type: application/json" \
  -d '{"to_number": "+1234567890", "message": "Test message"}'
```