# Bloom Deployment

This folder contains documentation and resources related to deploying the Bloom platform.

The Bloom project includes several parts that may be deployed separately, including the backend, mobile application, administrative dashboard, and informational website.

## Deployment Areas

The main deployment areas are:

```text
deployment/
|
|-- backend
|-- mobile
|-- dashboard
\-- website
```

The exact deployment process depends on the component being deployed.

## Backend

The Bloom backend provides the API used by the mobile application and administrative dashboard.

Before deploying the backend, the required environment variables and database configuration need to be set.

## Mobile Application

The mobile application communicates with the deployed Bloom backend through the API.

The application must be configured to use the correct backend API address before release.

## Administrative Dashboard

The administrative dashboard communicates with the Bloom backend through the API.

Its deployment is separate from the backend and mobile application.

## Informational Website

The informational website is publicly accessible and is separate from the authenticated applications.

## Related Documentation

- [Getting Started](../docs/getting-started.md)
- [Backend API](../docs/backend-api.md)
- [Mobile Application](../docs/mobile.md)
- [Administrative Dashboard](../docs/frontend-web.md)