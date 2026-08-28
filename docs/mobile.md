# Mobile Application

## 1. Overview

The Bloom mobile application is the main client application for mothers, caregivers, and Community Health Promoters (CHPs).

The application is built with Flutter and provides role-specific functionality depending on the type of user accessing the application.

The mobile application communicates with the Bloom backend through APIs. It does not connect directly to the PostgreSQL database.

```text
Mother / Caregiver / CHP
       |
       |
   Bloom Mobile
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

## 2. User Roles

The mobile application supports three main user roles:

```text
Bloom Mobile
|
|-- Mother
|
|-- Caregiver
|
\-- Community Health Promoter (CHP)
```

Each role has functionality relevant to its responsibilities within the Bloom platform.

---

## 3. Mobile Prototypes

The Bloom mobile prototypes show the main screens and user flows for the supported user roles.

- [Figma Prototypes](https://www.figma.com/proto/2rfI9KDVXSv7dH8pbdwkKy/SpyHive-Designs?node-id=559-1167&t=jhKiC1Y2LamimTym-1&scaling=scale-down&content-scaling=fixed&page-id=1%3A2&starting-point-node-id=551%3A397&show-proto-sidebar=1)


---

## 4. Mobile Application Structure

The Flutter application is organized under the `mobile` directory.

The main application code is located in `lib`.

```text
mobile/
|
|-- lib/
|   |
|   |-- main.dart
|   |
|   |-- models/
|   |
|   |-- services/
|   |   |
|   |   |-- api/
|   |   |
|   |   |-- authentication/
|   |   |
|   |   \-- notifications/
|   |
|   |-- screens/
|   |   |
|   |   |-- auth_screens/
|   |   |
|   |   |-- mothers_screens/
|   |   |
|   |   |-- caregiver_screens/
|   |   |
|   |   \-- chp_screens/
|   |
|   |-- widgets/
|   |
|   |-- providers/
|   |
|   |-- constants/
|   |
|   \-- utils/
|   |
|-- assets/
|   |
|   |-- images/
|   |-- icons/
|   \-- fonts/
|
|-- test/
|   |
|   |-- unit/
|   |-- widget/
|   \-- integration/
|
|-- android/
|-- ios/
|
|-- pubspec.yaml
\-- .env.example
```

The application separates screens, services, models, reusable widgets, providers, constants, and utility functionality.

---

## 5. Main Application Entry Point

The main application entry point is:

```text
lib/
|
\-- main.dart
```

`main.dart` starts the Flutter application and provides the entry point from which the application is initialized.

---

## 6. Models

The `models` directory contains the data models used by the mobile application.

```text
lib/
|
\-- models/
```

Models provide a representation of the data used by the application when communicating with the backend and displaying information within the mobile interface.

---

## 7. Services

The `services` directory contains functionality used by the application to communicate with external services and handle shared application operations.

```text
services/
|
|-- api/
|
|-- authentication/
|
\-- notifications/
```

### API Services

The `api` directory contains the services used for communication between the Flutter application and the Bloom backend.

The mobile application uses these services when sending requests to or retrieving information from the Bloom API.

```text
Bloom Mobile
       |
       | API request
       |
   API Services
       |
       |
   Bloom Backend
```

API communication is used for functionality such as:

- Authentication
- User information
- Maternal profile information
- Symptom logging
- Care schedules
- Maternal health tips
- Location-related functionality
- Other information provided through the Bloom API

---

### Authentication Services

Authentication-related functionality is organized under:

```text
services/
|
\-- authentication/
```

These services support authentication within the mobile application.

The authentication process communicates with the Bloom backend rather than handling authentication only within the local application.

```text
User
 |
 |
Mobile Application
 |
 | Authentication request
 |
Bloom Backend
 |
 |
Authentication
```

---

### Notification Services

Notification-related functionality is organized under:

```text
services/
|
\-- notifications/
```

These services support notification functionality within the mobile application.

Notifications are part of the application's wider reminder and alert functionality.

---

## 8. Screens

The mobile screens are organized according to the user roles and authentication functionality.

```text
screens/
|
|-- auth_screens/
|
|-- mothers_screens/
|
|-- caregiver_screens/
|
\-- chp_screens/
```

This organization keeps the interfaces for the different user roles separate.

---

### 8.1 Authentication Screens

Authentication screens are located under:

```text
screens/
|
\-- auth_screens/
```

These screens provide the user-facing authentication flow for the mobile application.

---

### 8.2 Mother Screens

Mother-specific screens are located under:

```text
screens/
|
\-- mothers_screens/
```

The mother experience includes functionality such as:

- Maternal profile management
- Daily symptom logging
- Maternal health recommendations
- Care scheduling
- Reminders
- Delivery date tracking
- Location functionality
- Maternal health tips
- Alerts and notifications

Information entered or generated through these features is handled through the mobile application's API integration with the Bloom backend.

---

### 8.3 Caregiver Screens

Caregiver-specific screens are located under:

```text
screens/
|
\-- caregiver_screens/
```

These screens provide functionality intended for caregivers.

The caregiver experience allows relevant maternal information to be accessed through the functionality provided by the Bloom platform.

Access to information is handled through the application's backend API.

---

### 8.4 CHP Screens

Community Health Promoter functionality is organized under:

```text
screens/
|
\-- chp_screens/
```

These screens provide functionality intended for Community Health Promoters.

The CHP experience includes functionality related to interaction with mothers and location-related information available through the Bloom platform.

---

## 9. Widgets

Reusable Flutter widgets are organized under:

```text
lib/
|
\-- widgets/
```

Widgets are used to provide reusable interface components across the application.

Keeping reusable components in a separate directory makes it easier to use common interface elements across different screens.

---

## 10. Providers

Application providers are located under:

```text
lib/
|
\-- providers/
```

Providers are used by the mobile application to manage and provide application state to the relevant parts of the interface.

---

## 11. Constants

Application constants are organized under:

```text
lib/
|
\-- constants/
```

This directory contains values that are shared across different parts of the mobile application.

Keeping shared constants in one location avoids repeatedly defining the same values throughout the application.

---

## 12. Utilities

Utility functionality is organized under:

```text
lib/
|
\-- utils/
```

This directory contains reusable supporting functionality used by the mobile application.

---

## 13. Assets

The mobile application contains assets under the `assets` directory.

```text
assets/
|
|-- images/
|-- icons/
\-- fonts/
```

### `images/`

Contains image assets used by the mobile application.

### `icons/`

Contains icon assets used by the application.

### `fonts/`

Contains font resources used by the application.

---

## 14. Testing

Mobile tests are organized under the `test` directory.

```text
test/
|
|-- unit/
|-- widget/
\-- integration/
```

### Unit Tests

The `unit` directory contains tests for individual pieces of application logic.

### Widget Tests

The `widget` directory contains tests for Flutter widgets and interface components.

### Integration Tests

The `integration` directory contains tests that verify functionality across multiple parts of the application.

---

## 15. API Integration

The mobile application communicates with the Bloom backend through the API services.

The general flow is:

```text
Mobile Screen
       |
       | User action
       |
API Service
       |
       | HTTP request
       |
Bloom Backend
       |
       | Application processing
       |
PostgreSQL
       |
       | Response
       |
Bloom Backend
       |
       |
API Service
       |
       |
Mobile Screen
```

This allows information entered through the mobile application to be sent to the backend and stored in the database where required.

---

## 16. Mobile Functionality

The mobile application provides functionality across the supported user roles.

The main areas include:

- User authentication
- Maternal profile management
- Daily symptom logging
- Maternal health recommendations
- Care scheduling
- Reminders
- Delivery date tracking
- Location functionality
- Caregiver functionality
- CHP functionality
- Maternal health tips
- Alerts and notifications

The functionality is connected to the backend API so that application data can be exchanged between the mobile application and the Bloom platform.

---

## 17. Environment Configuration

The mobile project contains an `.env.example` file.

```text
mobile/
|
\-- .env.example
```

The example file provides the expected environment configuration for the application.

Environment-specific values should be configured locally rather than committing sensitive values to the repository.

---

## 18. Flutter Dependencies

Flutter dependencies are defined in:

```text
mobile/
|
\-- pubspec.yaml
```

The `pubspec.yaml` file contains the packages and other project configuration required by the Flutter application.

Dependencies can be installed through Flutter's normal package management process.

From the mobile project directory:

```bash
flutter pub get
```

---

## 19. Running the Mobile Application

To work with the mobile application locally, make sure Flutter is installed and configured on the development machine.

From the `mobile` directory, install the project dependencies:

```bash
flutter pub get
```

The application can then be launched on a configured emulator, simulator, or physical device using the normal Flutter development workflow.

For example:

```bash
flutter run
```

The required environment configuration should be available before running features that depend on the Bloom backend API.

---

## 20. Related Documentation

- [Getting Started](getting-started.md)
- [Platform Overview](overview.md)
- [System Architecture](architecture.md)
- [Backend API](backend-api.md)
- [Database](database.md)
- [Administrative Dashboard](frontend-web.md)
- [Security](security.md)
- [Integrations](integrations.md)
- [Deployment](deployment.md)
- [Testing](testing.md)