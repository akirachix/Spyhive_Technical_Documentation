# Code Standards

## 1. Overview

Bloom is developed across the mobile application, backend API, and administrative dashboard.

Each part of the project should follow the existing structure and conventions of that codebase.

---

## 2. General Guidelines

When contributing to Bloom:

- Keep changes focused on the feature or issue being worked on.
- Follow the existing folder and file organization.
- Use clear and descriptive names for files, functions, classes, and variables.
- Avoid unnecessary duplication.
- Keep sensitive configuration out of the repository.
- Test changes before creating a pull request.
- Update the relevant documentation when a change affects how the system works.

---

## 3. Backend

The backend is written in Python using FastAPI.

Backend code is organized into areas such as:

```text
bloom/
|
|-- core/
|-- models/
|-- schemas/
|-- routers/
|-- repositories/
\-- services/
```

Keep API routing, application logic, and data-related functionality in their appropriate areas.

Follow the naming style already used by the existing backend files.

---

## 4. Mobile

The mobile application is built with Flutter.

The main application code is organized under:

```text
lib/
|
|-- models/
|-- services/
|-- screens/
|-- widgets/
|-- providers/
|-- constants/
\-- utils/
```

Keep role-specific screens in their existing directories:

```text
screens/
|
|-- auth_screens/
|-- mothers_screens/
|-- caregiver_screens/
\-- chp_screens/
```

Reusable interface components should be placed in `widgets` rather than duplicated across screens.

---

## 5. Dashboard

The administrative dashboard follows the existing `app/admin` structure.

```text
app/
|
\-- admin/
    |
    |-- account-settings/
    |-- auth/
    |   \-- login/
    |-- content-management/
    |-- metrics/
    |   |-- growth-and-engagement/
    |   \-- safety-and-alerts/
    \-- users-management/
```

New dashboard functionality should be placed in the appropriate existing section.

---

## 6. Naming

Use names that clearly describe what the code does.

Examples from the backend include:

```text
user_service.py
maternal_profile_service.py
symptom_service.py
care_schedule_service.py
```

Use the same naming style when adding related files.

---

## 7. Pull Requests

Before submitting a pull request:

1. Test the changes locally.
2. Check that unrelated files have not been changed.
3. Make sure the code follows the existing project structure.
4. Describe what was changed and why.
5. Mention any relevant testing performed.

Keep pull requests focused so that changes are easier for the team to review.

---

## 8. Documentation

Documentation is maintained under:

```text
docs/
```

If a change affects the architecture, API, database, mobile application, dashboard, deployment, or development setup, update the relevant documentation.

---