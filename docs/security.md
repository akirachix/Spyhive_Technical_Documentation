# Security

## 1. Overview

Security in Bloom is handled primarily through the backend API.

The mobile application and administrative dashboard communicate with the backend rather than accessing the database directly.

```text
Mobile Application
       |
       | API request
       |
Bloom Backend
       |
       | Database access
       |
PostgreSQL
```

The same approach is used for the administrative dashboard.

---

## 2. Authentication and Authorization

Bloom uses authentication to control access to the platform.

The backend is responsible for handling authentication and authorization for requests coming from the client applications.

```text
User
 |
 |
Client Application
 |
 | Authentication request
 |
Bloom Backend
 |
 | Authentication / Authorization
 |
Access to requested resource
```

Different users have different roles within Bloom, including:

- Mothers
- Caregivers
- Community Health Promoters (CHPs)
- Administrators

Access to platform functionality is based on the user's role.

---

## 3. API Security

The backend provides the main security layer for API requests.

Security-related functionality is handled through the backend, including:

- Authentication
- Authorization
- Request handling
- Input validation
- Rate limiting
- Access control

The backend contains a dedicated security module:

```text
backend/
|
\-- security.py
```

Rate limiting is also configured within the backend:

```text
backend/
|
\-- bloom/
    |
    \-- core/
        |
        \-- limiter.py
```

---

## 4. Database Access

The mobile application and administrative dashboard do not connect directly to PostgreSQL.

All database operations go through the backend.

```text
Mobile / Dashboard
       |
       | API
       |
Backend
       |
       | Database access
       |
PostgreSQL
```

This keeps database access within the backend rather than exposing the database directly to client applications.

---

## 5. Environment Variables

Environment-specific configuration is kept outside the source code.

The backend contains an example environment file:

```text
backend/
|
\-- .env.example
```

The mobile application and dashboard also contain their own `.env.example` files.

Actual environment files should not be committed to the repository when they contain private credentials or configuration values.

---

## 6. Sensitive Data

Bloom handles application data such as:

- User information
- Maternal profiles
- Symptoms and symptom logs
- Care schedules
- Location information

Access to this information is handled through the backend API and the application's authentication and authorization mechanisms.

Only the functionality available to an authenticated and authorized user should expose the corresponding data.

---

## 7. Security Responsibilities

Security is shared across the different parts of the platform:

| Component | Main responsibility |
|---|---|
| Mobile | User authentication and secure API communication |
| Dashboard | Administrator authentication and access control |
| Backend | Authentication, authorization, validation and API security |
| Database | Persistent storage of application data |

The backend acts as the main security boundary between the client applications and stored data.

---

## 8. Security Practices

When contributing to Bloom:

- Do not commit `.env` files containing secrets.
- Keep API credentials and private configuration out of source code.
- Use the backend API when accessing application data.
- Do not expose database credentials to client applications.
- Follow the project's authentication and authorization patterns when adding new functionality.

---

## 9. Related Documentation

- [Getting Started](getting-started.md)
- [System Architecture](architecture.md)
- [Backend API](backend-api.md)
- [Database](database.md)
- [Mobile Application](mobile.md)
- [Administrative Dashboard](frontend-web.md)