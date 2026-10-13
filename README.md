# Hope Foundation – NGO Website (React + Express + MongoDB)

## Setup
Requirements: Node.js 18+, MongoDB (local, or a free MongoDB Atlas URI).

1. Backend
   cd server && npm install
   cp .env.example .env     # edit JWT_SECRET, ADMIN_EMAIL, ADMIN_PASSWORD, MONGO_URI
   npm run seed             # optional: 40 DEMO records (npm run seed -- --clear removes them)
   npm run dev              # API on http://localhost:5000
2. Frontend (new terminal)
   cd client && npm install && npm run dev   # http://localhost:5173
3. Staff login: open /dashboard and sign in with ADMIN_EMAIL / ADMIN_PASSWORD from server/.env.

## Security
bcrypt-checked admin login, JWT (8h), helmet, rate limiting, field whitelisting, validation on client and server,
and all personal-record endpoints require the admin token. The public API only returns aggregate counts.
For production: use HTTPS, a strong JWT_SECRET, and restrict CLIENT_URL.
