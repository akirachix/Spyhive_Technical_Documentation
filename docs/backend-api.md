# Backend API

## 1. Overview

The Bloom backend provides the API used by the mobile application and administrative dashboard.

It is built with FastAPI and handles requests from the client applications, application logic, database operations, authentication and other backend functionality.

The backend connects to PostgreSQL for persistent data storage.

---

## 2. Backend Structure

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
    |   |
    |   |-- config.py
    |   \-- limiter.py
    |
    |-- models/
    |   |
    |   |-- user.py
    |   |-- location.py
    |   |-- maternal_profile.py
    |   |-- symptom.py
    |   |-- symptom_log_item.py
    |   |-- care_schedule.py
    |   \-- maternal_tip.py
    |
    |-- schemas/
    |
    |-- routers/
    |   |
    |   |-- user.py
    |   |-- location.py
    |   |-- maternal_profile.py
    |   |-- symptom.py
    |   |-- symptom_log_item.py
    |   |-- care_schedule.py
    |   |-- maternal_tip.py
    |   \-- analytics.py
    |
    |-- repositories/
    |
    \-- services/
        |
        |-- user_service.py
        |-- location_service.py
        |-- maternal_profile_service.py
        |-- symptom_service.py
        |-- symptom_log_item_service.py
        |-- care_schedule_service.py
        |-- maternal_tip_service.py
        \-- analytics_service.py
```

The main areas inside the `bloom` package are:

- `core` — contains shared backend configuration and rate-limiting functionality.
- `models` — contains the database models used by the application.
- `schemas` — contains the schemas used for API data.
- `routers` — contains the API route definitions.
- `repositories` — contains database access functionality.
- `services` — contains the application logic for the different Bloom features.

---

## 3. Root-Level Backend Files

Several files are located directly inside the backend directory and provide functionality used by the application.

### `main.py`

`main.py` is the main entry point for the FastAPI application.

It is responsible for setting up the backend application and registering the API functionality.

### `database.py`

`database.py` contains the database functionality used by the backend to communicate with PostgreSQL.

### `dependency.py`

`dependency.py` contains dependencies used by the FastAPI application.

These dependencies can be used by API routes when shared resources or functionality are required.

### `email.py`

`email.py` contains the functionality used for email-related operations within the backend.

### `distance.py`

`distance.py` contains functionality used for distance calculations.

This is used by functionality that requires location-based distance calculations.

### `security.py`

`security.py` contains security-related functionality used by the backend.

It supports the security and authentication requirements of the API.

### `requirements.txt`

`requirements.txt` contains the Python packages required by the Bloom backend.

The dependencies can be installed using:

```bash
pip install -r requirements.txt
```

### `.env.example`

`.env.example` provides an example of the environment variables required by the backend.

Environment-specific configuration values are provided through environment variables rather than being stored directly in the source code.

---

## 4. Core

The `bloom/core/` directory contains shared backend functionality.

```text
core/
|
|-- config.py
\-- limiter.py
```

### `config.py`

`config.py` contains configuration used by the backend application.

### `limiter.py`

`limiter.py` contains the rate-limiting functionality used by the backend.

---

## 5. Models

The `bloom/models/` directory contains the database models used by Bloom.

```text
models/
|
|-- user.py
|-- location.py
|-- maternal_profile.py
|-- symptom.py
|-- symptom_log_item.py
|-- care_schedule.py
\-- maternal_tip.py
```

The models represent the main types of information stored and managed by the backend.

### `user.py`

Contains the model used for user information.

### `location.py`

Contains the model used for location-related information.

### `maternal_profile.py`

Contains the model used for maternal profile information.

### `symptom.py`

Contains the model used for symptom information.

### `symptom_log_item.py`

Contains the model used for individual symptom log entries.

### `care_schedule.py`

Contains the model used for care schedule information.

### `maternal_tip.py`

Contains the model used for maternal health tip information.

---

## 6. Schemas

The `bloom/schemas/` directory contains the schemas used by the API.

Schemas define the structure of data exchanged through API requests and responses.

They are used to ensure that data sent to and returned from the API follows the expected structure.

---

## 7. Routers

The `bloom/routers/` directory contains the API route definitions.

```text
routers/
|
|-- user.py
|-- location.py
|-- maternal_profile.py
|-- symptom.py
|-- symptom_log_item.py
|-- care_schedule.py
|-- maternal_tip.py
\-- analytics.py
```

The routers group API endpoints according to the functionality they provide.

### `user.py`

Contains API routes related to users.

### `location.py`

Contains API routes related to location functionality.

### `maternal_profile.py`

Contains API routes related to maternal profiles.

### `symptom.py`

Contains API routes related to symptoms.

### `symptom_log_item.py`

Contains API routes related to symptom log entries.

### `care_schedule.py`

Contains API routes related to care schedules.

### `maternal_tip.py`

Contains API routes related to maternal health tips.

### `analytics.py`

Contains API routes related to analytics functionality.

---

## 8. Repositories

The `bloom/repositories/` directory contains the repository layer used for database access.

The repository layer separates database-related operations from the API routes and application services.

This allows database operations to be kept separate from the rest of the application logic.

---

## 9. Services

The `bloom/services/` directory contains the application service layer.

```text
services/
|
|-- user_service.py
|-- security_service.py
|-- location_service.py
|-- maternal_profile_service.py
|-- symptom_service.py
|-- symptom_log_item_service.py
|-- care_schedule_service.py
|-- maternal_tip_service.py
\-- analytics_service.py
```

The services contain the application logic for the different areas of Bloom.

### `user_service.py`

Handles application logic related to users.

### `user_service.py`
Handles security-related functionality, including authentication, password protection, token handling and access control.

### `location_service.py`

Handles application logic related to location functionality.

### `maternal_profile_service.py`

Handles application logic related to maternal profiles.

### `symptom_service.py`

Handles application logic related to symptoms.

### `symptom_log_item_service.py`

Handles application logic related to symptom log entries.

### `care_schedule_service.py`

Handles application logic related to care schedules.

### `maternal_tip_service.py`

Handles application logic related to maternal health tips.

### `analytics_service.py`

Handles application logic related to analytics.

---

## 10. Backend Request Flow

A typical request to the Bloom backend moves through the API and application layers before reaching the database.

```text
Client Application
       |
       | HTTP Request
       |
     Router
       |
       |
    Service
       |
       |
   Repository
       |
       |
   PostgreSQL
```

The result is then returned through the backend to the client application.

This separation keeps API routing, application logic, and database access organized into their respective areas.

---

## 11. Mobile and Dashboard Communication

The Bloom backend serves both the mobile application and the administrative dashboard.

The mobile application uses the API for functionality such as:

- Authentication
- User information
- Maternal profiles
- Symptom logging
- Care schedules
- Maternal health tips
- Location-related functionality
- Alerts and relevant maternal information

The administrative dashboard uses the API for functionality such as:

- Administrator authentication
- User management
- Content management
- Growth and engagement metrics
- Safety and alerts
- Account settings

Both client applications communicate with the backend through the API rather than connecting directly to PostgreSQL.

---

## 12. Backend and Database

The backend is responsible for communicating with PostgreSQL.

The general relationship between the backend and database is:

```text
Bloom Backend
       |
       | Database operations
       |
   PostgreSQL
```

The backend handles the operations required to store and retrieve application data.

The database structure is documented separately in [Database](database.md).

---

## 13. Running the Backend

Before running the backend locally, install the required Python dependencies:

```bash
pip install -r requirements.txt
```

Create a local environment configuration based on `.env.example` and provide the required values.

The FastAPI application can then be started using the project's configured application entry point.

The exact environment configuration may differ between local development and deployed environments.

---

## 14. Related Documentation

- [Getting Started](getting-started.md)
- [System Architecture](architecture.md)
- [Database](database.md)
- [Mobile Application](mobile.md)
- [Administrative Dashboard](frontend-web.md)
- [Security](security.md)
- [Integrations](integrations.md)
- [Deployment](deployment.md)