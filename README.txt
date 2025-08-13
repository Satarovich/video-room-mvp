
You Can — Video Room MVP (под ключ)
==================================

Файлы:
- backend/  — сервер, генерирует room codes и auth tokens через 100ms API
- frontend/ — React приложение (Create React App) с автоподключением по токену

ВАЖНО: не коммить .env с реальными токенами.

Локальный запуск
----------------
1) Backend:
   cd backend
   cp .env.example .env
   # Открой backend/.env и вставь MANAGEMENT_TOKEN и ROOM_ID (и CLIENT_URL если нужно)
   npm install
   node index.js

2) Frontend:
   cd frontend
   npm install
   npm start

Тесты:
- Открой http://localhost:4000/join?role=host
- Открой http://localhost:4000/join?role=guest

Деплой
------
- Backend: Render.com или Railway — укажи root directory = backend, env variables: MANAGEMENT_TOKEN, ROOM_ID, CLIENT_URL
- Frontend: Vercel/Netlify — укажи root directory = frontend, build: npm run build, output: build
- После получения URL фронтенда, обнови CLIENT_URL на бекенде и redeploy.

