# -Monta-Thik-Ache-
Hackathon project 
Author:Team_Timeout
# Monta Thik Ache?

Full-stack web app with mental health check-in, community health features, anonymous help, seasonal tips, symptom guide, events+volunteers, export, and a voice-first assistant.

## Stack
- Backend: Node.js + Express, JSON file storage
- Frontend: React (Vite), simple PWA service worker

## Run locally

In two terminals from the workspace root:

1) Backend (Node) — optional legacy
```
cd backend
npm install
npm run start
```
Backend runs on http://localhost:4000

2) Backend (Django + MySQL)
```
cd backend_django
python -m venv .venv && .venv/Scripts/activate
pip install -r requirements.txt

# Configure MySQL (create DB `mta` and user or edit env)
set DJANGO_SECRET_KEY=dev
set DJANGO_DEBUG=1
set MYSQL_DATABASE=mta
set MYSQL_USER=root
set MYSQL_PASSWORD=
set MYSQL_HOST=127.0.0.1
set MYSQL_PORT=3306

python manage.py migrate
python manage.py runserver 8000
```
API docs: http://localhost:8000/api/docs/

3) Frontend
```
cd frontend
npm install
npm run dev
```
Frontend runs on http://localhost:5173 and proxies /api to Django at 8000.

## Features mapping
- Mission 1: Mood tracker with voice-to-text, suggestions, notifications
- Mission 2: Community map with network reliability fallback, share/call/WhatsApp, nearest GP suggestion
- Mission 3: Anonymous help request with offline queue via IndexedDB and auto-upload when online
- Mission 4: Seasonal preventive tips by month + current temperature (Open-Meteo), emergency hotline
- Mission 6: Symptom awareness guide, guidance actions
- Missions 7+8: Community health events + volunteer directory
- Mission 9: Export mission-8 data (JSON/CSV) + simple correction detection
- Mission 10: Voice-first assistant (speech recognition + TTS) and appointment request

## Notes
- Push notifications are implemented using the Web Notifications API (permission required). Browser push services are not configured.
- Location map uses a static map image for reliability rather than live tiles.
- Data is stored in `backend/data/store.json`.


https://app.eraser.io/workspace/7AGRjXrdDge4Cod8XO3h?origin=share
