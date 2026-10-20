# Backend (Express + MongoDB)

1. Make sure MongoDB is running on your computer (default: `mongodb://127.0.0.1:27017`).
2. `cd backend`
3. `npm install`
4. Check `backend/.env` (see `.env.example`).
5. `npm run dev` (starts on http://localhost:5000)

## API
- `POST /api/auth/register`  body: name, email, password
- `POST /api/auth/login`     body: email, password -> returns token and user
- `GET  /api/auth/me`        needs header `Authorization: Bearer <token>`

### Tasks (all need `Authorization: Bearer <token>`; each user only sees their own tasks)
- `GET    /api/tasks`      list my tasks
- `POST   /api/tasks`      body: title
- `PUT    /api/tasks/:id`  body: title and/or completed
- `DELETE /api/tasks/:id`  delete a task
