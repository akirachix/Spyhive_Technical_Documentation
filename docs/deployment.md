# Deployment

## 1. Overview

Bloom is made up of separate applications that work together through the backend API.

The main deployed components are:

- Bloom Mobile Application
- Bloom Administrative Dashboard
- Bloom Backend API
- PostgreSQL Database
- Bloom Informational Website

The mobile application and dashboard communicate with the backend through APIs.

---

## 2. Deployment Structure

The general deployment relationship is:

```text
Bloom Mobile
|
|-- API
|
|-- Bloom Backend
|
|-- Database
|
\-- PostgreSQL

Bloom Dashboard
|
|-- API
|
\-- Bloom Backend

Bloom Informational Website
```

The informational website operates separately from the authenticated mobile and dashboard applications.

---

## 3. Backend Deployment

The backend is built with FastAPI.

The backend requires its environment configuration and Python dependencies before it can be run.

The main dependency files are:

```text
backend/
|
|-- requirements.txt
\-- .env.example
```

Dependencies can be installed with:

```bash
pip install -r requirements.txt
```

The backend uses the FastAPI application entry point:

```text
backend/
|
\-- main.py
```

The exact deployment environment and hosting configuration should be kept consistent with the environment used by the team.

---

## 4. Mobile Deployment

The Bloom mobile application is built with Flutter.

The project contains platform-specific directories for:

```text
mobile/
|
|-- android/
|-- ios/
\-- pubspec.yaml
```

Before building or running the application, install the Flutter dependencies:

```bash
flutter pub get
```

The application can be run locally with:

```bash
flutter run
```

Production builds should use the appropriate Flutter build process for the target platform.

---

## 5. Dashboard Deployment

The administrative dashboard is a web application.

Its main application structure is under:

```text
frontend/
|
\-- app/
    |
    \-- admin/
```

The dashboard has its own dependencies and environment configuration.

```text
frontend/
|
|-- package.json
\-- .env.example
```

Dependencies can be installed using the package manager configured for the project.

---

## 6. Informational Website

The Bloom informational website is publicly available at:

[Visit the Bloom Informational Website →](https://bloom-rho-sand.vercel.app/)

The informational website is separate from the administrative dashboard and mobile application.

---

## 7. Environment Configuration

Each application uses environment-specific configuration where required.

Example configuration files are provided as:

```text
backend/
|
\-- .env.example

mobile/
|
\-- .env.example

frontend/
|
\-- .env.example
```

Actual environment files should not be committed when they contain private credentials or other sensitive values.

---

## 8. Deployment Considerations

Before deploying a new version:

- Confirm the required environment variables are configured.
- Install the required dependencies.
- Verify the application builds successfully.
- Test the API and relevant client functionality.
- Check that the deployed application can communicate with the backend.

---

## 9. Related Documentation

- [Getting Started](getting-started.md)
- [System Architecture](architecture.md)
- [Backend API](backend-api.md)
- [Database](database.md)
- [Mobile Application](mobile.md)
- [Administrative Dashboard](frontend-web.md)
- [Integrations](integrations.md)
- [Testing](testing.md)