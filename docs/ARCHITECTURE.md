# Architecture

## Overview

This repository is intentionally small, but structured around the same separation used in larger backend services.

```text
Client
  |
  v
FastAPI routes
  |
  v
Pydantic validation
  |
  v
SQLAlchemy session
  |
  v
Database
```

## Application layers

### API layer
`app/main.py` exposes HTTP endpoints, validates request/response shapes, maps database errors to HTTP responses, and keeps transport concerns close to FastAPI.

### Schema layer
`app/schemas.py` defines request and response contracts with Pydantic. API consumers receive stable shapes instead of raw ORM objects.

### Persistence layer
`app/models.py` contains SQLAlchemy models while `app/database.py` owns engine/session creation and dependency injection.

### Configuration
Environment variables control runtime configuration. Secrets are intentionally excluded from Git and only placeholders are committed through `.env.example`.

## Production evolution

For a larger service I would split route modules, add a service/repository layer where business rules justify it, use Alembic migrations rather than startup table creation, add structured logging and metrics, and place authentication/authorization behind reusable dependencies.

The goal here is not complexity for its own sake; it is to demonstrate a clean base that can grow without rewriting the whole application.
