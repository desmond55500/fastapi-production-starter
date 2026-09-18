# FastAPI Production Starter

A clean, public-safe backend portfolio project demonstrating how I structure a small production-minded API with **FastAPI, PostgreSQL-ready configuration, SQLAlchemy, validation, testing, and Docker**.

This project was built independently as a portfolio demonstration and contains no company source code or proprietary business logic.

## Highlights

- FastAPI application structure
- Environment-based configuration
- SQLAlchemy database setup
- Health-check endpoint
- Simple user resource with validation
- Docker and Docker Compose configuration
- Pytest API tests
- Safe `.env.example` configuration
- Clear separation between application, database, and schemas

## Stack

- Python 3.12
- FastAPI
- SQLAlchemy
- Pydantic
- PostgreSQL
- Uvicorn
- Pytest
- Docker

## Project structure

```text
app/
  __init__.py
  main.py
  database.py
  models.py
  schemas.py
tests/
  test_api.py
.env.example
.gitignore
Dockerfile
docker-compose.yml
requirements.txt
```

## Run locally

```bash
python -m venv .venv
source .venv/bin/activate       # macOS/Linux
# .venv\Scripts\activate      # Windows

pip install -r requirements.txt
cp .env.example .env
uvicorn app.main:app --reload
```

Open:

- API: http://127.0.0.1:8000
- Swagger docs: http://127.0.0.1:8000/docs
- Health: http://127.0.0.1:8000/health

## Run with Docker

```bash
docker compose up --build
```

## Example endpoints

| Method | Endpoint | Purpose |
| --- | --- | --- |
| GET | `/` | API metadata |
| GET | `/health` | Health check |
| GET | `/users` | List users |
| POST | `/users` | Create a user |

## Why this project exists

Most of my production application work is private. This repository demonstrates the same engineering fundamentals in a completely independent project that can safely be reviewed publicly.

## Next improvements

- JWT authentication
- Alembic migrations
- Async database sessions
- CI with GitHub Actions
- Role-based authorization
- Pagination and filtering
