# GitHub Webhook Listener (Flask + MongoDB)

This project is a backend application that listens to GitHub webhook events,
processes them, and stores the event data in MongoDB.
It uses ngrok to expose the local Flask server to GitHub.

--------------------------------------------------

FEATURES

- Receives GitHub Push events
- Processes webhook payloads
- Stores data in MongoDB
- REST API to fetch stored events
- Auto-refresh frontend (every 15 seconds)
- ngrok integration for webhook testing

--------------------------------------------------

TECH STACK

- Python
- Flask
- MongoDB
- ngrok
- GitHub Webhooks

--------------------------------------------------

PROJECT STRUCTURE

webhook-repo/
|
|-- app.py
|-- templates/
|   |-- index.html
|-- requirements.txt
|-- README.md

--------------------------------------------------

SETUP INSTRUCTIONS

1. Clone the repository

git clone https://github.com/Venkat3250/<repo-name>.git
cd <repo-name>

--------------------------------------------------

2. Install dependencies

pip install -r requirements.txt

--------------------------------------------------

3. Start MongoDB

mongod --dbpath C:\data\db

MongoDB runs on:
localhost:27017

--------------------------------------------------

4. Run the Flask application

python app.py

Flask server runs on:
http://127.0.0.1:5000

--------------------------------------------------

5. Start ngrok

ngrok http 5000

You will get a public URL like:
https://xxxx.ngrok-free.dev

--------------------------------------------------

GITHUB WEBHOOK CONFIGURATION

Go to:
GitHub Repository → Settings → Webhooks → Add Webhook

Payload URL:
https://<ngrok-url>/webhook

Content type:
application/json

Events:
Just the push event

Active:
Enabled

--------------------------------------------------

WEBHOOK ENDPOINT

POST /webhook

The application extracts and stores:
- request_id
- repo
- author
- action
- from_branch
- to_branch
- timestamp

--------------------------------------------------

API ENDPOINT

GET /events

Returns the latest 20 webhook events stored in MongoDB.

--------------------------------------------------

FRONTEND

- URL: GET /
- Displays webhook events
- Auto-refreshes every 15 seconds

--------------------------------------------------

VERIFICATION CHECKLIST

- GitHub push triggers webhook
- ngrok receives POST request
- Flask processes payload
- Data stored in MongoDB
- Events visible via API and UI

--------------------------------------------------

WHAT THIS PROJECT SHOWS

- Real-time webhook handling
- Backend API development
- GitHub integration
- MongoDB data storage
- End-to-end request flow debugging

--------------------------------------------------

NOTES

- ngrok URL changes on restart (Free plan)
- Flask development server is used
- Suitable for demo and assignment purposes

--------------------------------------------------

AUTHOR

G Venkata Mohan Krishna
GitHub: https://github.com/Venkat3250
