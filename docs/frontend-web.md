# Administrative Dashboard

## 1. Overview

The Bloom administrative dashboard is the web interface used by Bloom administrators.

It provides administrators with access to platform management, user management, content management, account settings, and platform metrics.

The dashboard communicates with the Bloom backend through the API and does not connect directly to the PostgreSQL database.

```text
Administrator
       |
       |
Admin Dashboard
       |
       | API requests
       |
   Bloom Backend
       |
       | Database operations
       |
   PostgreSQL
```

---

## 2. Dashboard Structure

The dashboard is organized under the `admin` area of the frontend application.

```text
admin/
|
|-- account-settings/
|
|-- auth/
|   \-- login/
|
|-- content-management/
|
|-- metrics/
|   |
|   |-- growth-and-engagement/
|   \-- safety-and-alerts/
|
\-- users-management/
```

Each section provides a different area of functionality for administrators.

---

## 3. Authentication

Administrator authentication is located under:

```text
admin/
|
\-- auth/
    |
    \-- login/
```

The login area provides the entry point for administrators to authenticate before accessing the dashboard.

Authentication is handled through the application's backend API.

```text
Administrator
       |
       |
    Login
       |
       | Authentication request
       |
   Bloom Backend
       |
       |
 Authentication
```

Once authenticated, the administrator can access the available dashboard functionality.

---

## 4. Account Settings

Account settings are located under:

```text
admin/
|
\-- account-settings/
```

This section provides functionality related to administrator account settings.

Account-related requests are handled through the dashboard and its connection to the Bloom backend.

---

## 5. User Management

User management is located under:

```text
admin/
|
\-- users-management/
```

This section provides administrators with functionality for managing users within the Bloom platform.

User management communicates with the backend API to access the information and operations required by the dashboard.

```text
Administrator
       |
       |
Users Management
       |
       | API request
       |
   Bloom Backend
       |
       |
   User Data
```

---

## 6. Content Management

Content management is located under:

```text
admin/
|
\-- content-management/
```

This section provides administrators with functionality for managing platform content.

Content-related operations are performed through the dashboard and communicate with the Bloom backend.

---

## 7. Metrics

The dashboard contains a metrics section with two main areas:

```text
admin/
|
\-- metrics/
    |
    |-- growth-and-engagement/
    \-- safety-and-alerts/
```

These sections provide administrators with information used to monitor different aspects of the Bloom platform.

---

### 7.1 Growth and Engagement

The growth and engagement section is located at:

```text
admin/
|
\-- metrics/
    |
    \-- growth-and-engagement/
```

This area provides metrics related to platform growth and user engagement.

The dashboard retrieves the required information through the Bloom backend API.

```text
Administrator
       |
       |
Growth and Engagement
       |
       | API request
       |
   Bloom Backend
       |
       |
    Analytics
```

---

### 7.2 Safety and Alerts

The safety and alerts section is located at:

```text
admin/
|
\-- metrics/
    |
    \-- safety-and-alerts/
```

This area provides administrators with safety-related information and alerts available through the platform.

The dashboard communicates with the backend API to retrieve the relevant information.

```text
Administrator
       |
       |
 Safety and Alerts
       |
       | API request
       |
   Bloom Backend
       |
       |
Relevant Data
```

---

## 8. Dashboard and Backend Communication

The dashboard communicates with the Bloom backend through API requests.

The general communication flow is:

```text
Administrative Dashboard
       |
       | API request
       |
   Bloom Backend
       |
       | Application processing
       |
   Database / Services
       |
       |
   API Response
       |
       |
Administrative Dashboard
```

The backend handles the application logic and database operations required by the dashboard.

---

## 9. Dashboard Areas and Backend Functionality

The main relationship between the dashboard sections and backend functionality can be summarized as follows:

| Dashboard Area | Related Functionality |
|---|---|
| Authentication | Administrator authentication |
| Account Settings | Administrator account functionality |
| User Management | User-related operations |
| Content Management | Platform content operations |
| Growth and Engagement | Analytics and engagement information |
| Safety and Alerts | Safety-related information and alerts |

The dashboard acts as the administrative interface, while the backend provides the API and application services behind these features.

---

## 10. Frontend Application Structure

The administrative dashboard is part of the Bloom frontend application.

The main dashboard area is organized as:

```text
frontend/
|
\-- app/
    |
    \-- admin/
        |
        |-- account-settings/
        |
        |-- auth/
        |   \-- login/
        |
        |-- content-management/
        |
        |-- metrics/
        |   |
        |   |-- growth-and-engagement/
        |   \-- safety-and-alerts/
        |
        \-- users-management/
```

Other frontend files and components support the dashboard application.

The dashboard-specific pages are grouped under the `admin` area to keep the administrative functionality organized separately from other frontend resources.

---

## 11. Database Access

The administrative dashboard does not communicate directly with PostgreSQL.

Database operations are handled by the Bloom backend.

```text
Admin Dashboard
       |
       |
   Bloom API
       |
       |
   Bloom Backend
       |
       |
   PostgreSQL
```

This allows the backend to control how administrative data is retrieved and modified.

---

## 12. Related Documentation

- [Getting Started](getting-started.md)
- [Platform Overview](overview.md)
- [System Architecture](architecture.md)
- [Backend API](backend-api.md)
- [Database](database.md)
- [Mobile Application](mobile.md)
- [Security](security.md)
- [Integrations](integrations.md)
- [Deployment](deployment.md)