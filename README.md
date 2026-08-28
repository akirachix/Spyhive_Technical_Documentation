# Bloom Platform Technical Documentation

This directory contains the central technical documentation for the Bloom maternal health platform. It provides a system overview designed to help developers understand the architecture, configure local environments, and safely contribute code.

The documentation outlines the business rules, security models, and code standards applied across the backend API, mobile application, and administrative web workflows.

---

## Documentation Map

The system guides are split into separate modules for clean organization:

* Getting Started: Software requirements, repository cloning, and environment verification.
* System Architecture: System interaction flow charts, data routing, and infrastructure maps.
* Backend API: Core logic configurations, routing mechanisms, and data schemas.
* Database Design: Object-relational mapping models, table schemas, and data constraints.
* Frontend Web: Layout maps and permission rules for administrative interfaces.
* Mobile Client: App configurations, lifecycle synchronization, and localized user flows.
* Platform Security: Session telemetry constraints, rate-limiting guards, and access tiers.
* Code Standards: Branch naming conventions, commit formats, and validation procedures.

---

## Repository Structure

The documentation folder sits at the root of the main platform workspace:

```text
docs/
├── README.md
├── getting-started.md
├── overview.md
├── architecture.md
├── backend-api.md
├── database.md
├── frontend-web.md
├── mobile.md
├── security.md
├── deployment.md
├── integrations.md
├── code-standards.md
├── testing.md
└── glossary.md
```

---

## Managing Documentation in VS Code

Our team maintains and edits all platform documentation as Markdown files directly inside Visual Studio Code. Follow these workspace steps when making updates:

* **Markdown Preview:** Press `Ctrl + Shift + V` (Windows/Linux) or `Cmd + Shift + V` (macOS) to check formatting before saving files.
* **Integrated Terminal:** Use the built-in terminal window to run document checks and commit your updates cleanly.

---

## Core Maintenance Guidelines

### 1. Document Integrity
* Code Sync: Update the documentation file immediately when changing data models or route structures.
* No Fake Assets: Do not include placeholder links for structures that do not exist within the active code branches.

### 2. Formatting Standards
* Language Rule: Write all technical explanations in clean, direct, and simple English.
* Visual Diagrams: Keep drawings like ERDs updated within the design files directory instead of duplicating them in text files.

---

## Testing Documentation Changes

Before pushing modifications to the repository, ensure your document updates do not break standard layouts:

```bash
# Run your configured documentation link verification tool here
```
**Make sure your updates follow these rules:**
* All markdown cross-links between documentation files must resolve correctly without broken links.
* Document section codes must match active structural rules outlined in the core style guides.
* Code syntax highlighting identifiers in blocks must correctly match their designated implementation languages.
