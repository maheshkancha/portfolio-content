# Portfolio Data Repository

This repository `portfolio-content` contains structured static content for a personal portfolio application.
All portfolio information is stored as JSON and served directly from GitHub so that the frontend application can fetch and render it dynamically.

This approach keeps the portfolio:
* Fully static
* Version controlled
* Easily maintainable
* Decoupled from frontend code
* Validated using JSON Schema

---

## 📌 Purpose

The goal of this repository is to act as a single source of truth for portfolio content, including:

* Personal profile information
* Skills and technologies
* Work experience
* Projects
* Domain expertise
* Education
* Social links
* Media assets

The frontend application fetches this data using GitHub raw content endpoints and renders it.

No backend server is required.

---

## 🧭 System Flow

```
Author updates portfolio.json
        ↓
Schema validation runs (local or CI)
        ↓
Changes committed to GitHub
        ↓
GitHub hosts JSON as static content
        ↓
Svelte portfolio app fetches JSON via HTTP
        ↓
UI renders portfolio dynamically
```

---

## 📂 Repository Structure

```
portfolio-data/
│
├── portfolio.json
│   Main portfolio content
│
├── portfolio.schema.json
│   JSON Schema for validation
│
├── images/
│   Profile images, project screenshots, media
│
└── README.md
    Documentation
```

---

## 📄 Data File Description
`portfolio.json`
Contains all portfolio content in structured format.
This file is consumed by the frontend application.

---

`portfolio.schema.json`
Defines the validation rules for portfolio.json.

Ensures:
* Required fields exist
* Data types are correct
* URLs are valid
* Dates are formatted properly
* Structure remains consistent

---
Ini
## ✅ Schema Validation Plan

Schema validation ensures data integrity and prevents runtime errors in the frontend.

Validation can be performed at multiple stages:

1️⃣ Local Development Validation

Developers validate JSON before committing.

Tools:
* AJV CLI
* VS Code JSON Schema support
* Custom validation scripts

---

2️⃣ Continuous Integration Validation (Recommended)

A CI workflow automatically validates JSON on every push or pull request.

Process:

```
Commit changes
   ↓
CI pipeline runs schema validation
   ↓
If invalid → build fails
If valid → merge allowed
```

This guarantees only valid portfolio data is deployed.

---

3️⃣ Runtime Validation (Optional)

The frontend app can validate fetched JSON before rendering.

Benefits:

* Extra safety
* Protects against corrupted data
* Helpful for public APIs

---

## 🌐 Data Access (Frontend Usage)

The frontend application retrieves portfolio data directly from GitHub raw file URLs.

Example:

```
https://raw.githubusercontent.com/<username>/<repo>/<branch>/portfolio.json
```

This endpoint returns the latest validated portfolio data.

OR

The contents have been **published as GitHub pages**. So, contents can now be accessed as:

```
https://<username>.github.io/<repo>/<file_name.ext>
```

---

## ✏️ How to Update Portfolio Content

* Edit portfolio.json
* Validate against schema
* Commit and push changes
* Frontend automatically reflects updates
* No frontend deployment required if content only changes.

---

## 🧩 Design Principles

* Static-first architecture
* Content separated from UI
* Strong schema enforcement
* Git-based versioning
* Serverless data delivery
* Scalable structure

---

## 🚀 Future Enhancements

* GitHub Actions auto validation
* JSON versioning strategy
* Localization support
* CMS-style editing interface
* Media optimization pipeline

---

### 👤 Maintainer
Mahesh Bahadur
(Senior Staff Engineer)