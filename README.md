# Team Task Manager API

REST API for managing development team tasks, built with **FastAPI**, **PostgreSQL** and **SQLAlchemy**.
Includes user registration with password hashing.

## Setup

```bash
pip install -r requirements.txt
alembic upgrade head
uvicorn main:app --reload
```

Set the PostgreSQL connection string in `database.py` before running.
Swagger UI: http://127.0.0.1:8000/docs

## Endpoints

| Resource | Endpoints |
|----------|-----------|
| Auth     | `POST /register` |
| Users    | `POST /users`, `GET /users`, `GET /users/{id}`, `DELETE /users/{id}` |
| Projects | `POST /projects`, `GET /projects`, `GET /projects/{id}` |
| Tasks    | `POST /tasks`, `GET /tasks`, `GET /tasks/{id}`, `PUT /tasks/{id}`, `DELETE /tasks/{id}` |

## Data Model

- **users**: id, name, email, password (hashed), created_at
- **projects**: id, name, description, created_at
- **tasks**: id, title, description, status (todo / in_progress / done), priority (low / medium / high), user_id, project_id, created_at
