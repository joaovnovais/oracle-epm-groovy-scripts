# Oracle EPM Cloud — Groovy Scripts

A collection of Groovy scripts developed for Oracle EPM Cloud Planning (PBCS), covering business rules, form validations, data push jobs, and compatibility fixes for the Groovy Engine introduced in version 26.05.

All scripts are based on real-world implementations across multiple client environments.

---

## 📁 Repository Structure

---

## 🧩 About Oracle EPM Cloud Planning

Oracle EPM Cloud Planning (also known as PBCS — Planning and Budgeting Cloud Service) is Oracle's cloud-based financial planning platform. It supports budgeting, forecasting, and reporting across business dimensions such as Actuals, Budget, and Forecast scenarios.

Groovy scripting in EPM Cloud allows developers to extend native calculation logic with custom Java-based scripts executed directly on the server, enabling dynamic validations, complex data manipulations, and cross-cube operations.

---

## ⚙️ Groovy Engine 26.05 — Migration Notes

Oracle EPM Cloud version 26.05 introduced a stricter Groovy engine with breaking changes that affect existing scripts. Key issues addressed in this repository:

- **`final` variable redeclaration errors** — the new engine enforces stricter scoping rules; variables declared as `final` cannot be reassigned in any block
- **RTP (Runtime Prompt) syntax corrections** — updated syntax for retrieving runtime prompt values
- **Static type casting** — stricter type enforcement requiring explicit casting in several contexts

All scripts in the `migration-26.05/` folder have been tested and validated against the new engine.

---

## 🗂️ Script Categories

### Business Rules (`/business-rules`)
Custom Groovy rules used within EPM Planning applications to implement calculation logic beyond native Essbase capabilities. Examples include cross-dimensional data reads, conditional aggregations, and multi-scenario processing.

### Form Validations (`/form-validations`)
Runtime Groovy scripts triggered when users interact with EPM web forms. Used to enforce business constraints, display dynamic warnings, and block invalid data entries before they reach the database.

### Data Push Jobs (`/data-push`)
Scripts designed to push data between Planning cubes (e.g., from a main cube to a Reporting cube), including cube-clearing logic to avoid residual data across scenarios (ACT, BUD, FOR).

### Migration 26.05 (`/migration-26.05`)
Refactored versions of existing scripts updated for compatibility with the stricter Groovy engine shipped in Oracle EPM Cloud version 26.05.

---

## 🔧 How to Use

1. Open your Oracle EPM Cloud Planning application
2. Navigate to **Rules** (Calculation Manager or EPM Automate)
3. Create a new Groovy rule and paste the desired script
4. Adjust dimension members, cube names, and scenario references to match your application's metadata
5. Validate and deploy the rule

> ⚠️ Always test scripts in a **development or test environment** before deploying to production.

---

## 📌 Requirements

- Oracle EPM Cloud Planning (PBCS / EPBCS)
- Groovy scripting enabled in your environment
- Appropriate admin or power user permissions to create and deploy rules

---

## 👤 Author

**João Novais**
Oracle ACE Apprentice | Data Engineer | Oracle EPM Cloud Specialist

[![LinkedIn](https://img.shields.io/badge/LinkedIn-joaovnovais-blue?logo=linkedin)](https://www.linkedin.com/in/joaovnovais)
[![GitHub](https://img.shields.io/badge/GitHub-joaovnovais-black?logo=github)](https://github.com/joaovnovais)

---

## 📄 License

This repository is licensed under the MIT License. Scripts may be freely used and adapted with proper attribution.
