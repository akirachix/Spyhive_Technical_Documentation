# Bloom Backend

The Bloom backend provides the API used by the mobile application and administrative dashboard.

It is built with **FastAPI** and communicates with the PostgreSQL database.

---

## Backend Structure

The backend is organized into root-level files and the `bloom` package.

```text
backend/
|
|-- main.py
|-- database.py
|-- dependency.py
|-- email.py
|-- distance.py
|-- security.py
|
|-- requirements.txt
|-- .env.example
|
\-- bloom/
    |
    |-- core/
    |-- models/
    |-- schemas/
    |-- routers/
    |-- repositories/
    \-- services/
```

### Root Files

The root-level Python files provide shared backend functionality, including application setup, database access, dependencies, email functionality, distance calculations, and security.

`requirements.txt` contains the Python dependencies required by the backend.

`.env.example` provides an example of the environment variables needed to configure the backend.

### `bloom/`

The `bloom` package contains the main application components.

| Folder | Purpose |
|---|---|
| `core/` | Configuration and rate limiting |
| `models/` | Database models |
| `schemas/` | API data schemas |
| `routers/` | API routes |
| `repositories/` | Data access |
| `services/` | Application logic |

---

## API

The backend provides API endpoints used by both the Bloom mobile application and administrative dashboard.

For the detailed API documentation, see [Backend API](../docs/backend-api.md).

## Setup

For backend installation, environment configuration, and running the application locally, see [Getting Started](../docs/getting-started.md).