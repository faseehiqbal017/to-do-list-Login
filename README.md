# test-react

React (Vite) frontend with an Express + MongoDB backend. Features: sign up, login, and a protected home page.

## How to run
1. Start MongoDB locally (default port 27017). Data is saved in a database named `test-react`.
2. Backend (terminal 1):
   ```
   cd backend
   npm install
   npm run dev
   ```
3. Frontend (terminal 2):
   ```
   cd frontend
   npm install
   npm run dev
   ```
4. Open http://localhost:5173

## Environment files
- `backend/.env`: PORT, MONGO_URI, JWT_SECRET, CLIENT_URL
- `frontend/.env`: VITE_API_URL (backend address used by the frontend)

## How it works
- Sign up: password is hashed with bcrypt and the user is saved in MongoDB.
- Login: the server checks the password and sends back a JWT token.
- The frontend keeps the token in localStorage and sends it with every request.
- `/home` is a protected page; without a token you are sent back to `/login`.
- The dashboard has a to-do list (create, read, update, delete). Tasks are stored per user: the API checks the token and only returns or changes tasks owned by the logged-in user.
