# Phase 1 — Project Analysis, Architecture, Authentication, and Authorisation

Transform the current application into **“Nuvolaris HR”**, a professional human resources management platform.

Do not create a new application. Do not stop at a scaffold, prototype, or mocked implementation.

The user interface must be in Italian.

## Initial project analysis

Before making changes, fully analyse the existing project and reuse its current:

- architecture;
- directory structure;
- components;
- design system;
- coding conventions;
- backend patterns;
- integrations;
- official bindings;
- deployment workflow.

Do not replace working parts unnecessarily.

Maintain an updated checklist throughout the work. It must include at least:

- architecture and data model;
- authentication;
- employee backend;
- file and CV management;
- turnover;
- frontend;
- user administration;
- tests and browser verification.

## Authentication and authorisation

Implement complete authentication with:

- initial setup of the first administrator;
- login and logout;
- persistent sessions with correctly managed expiration;
- redirect to the dashboard after login;
- redirect to the login page when an unauthenticated user visits a protected page;
- backend API protection, not only frontend route protection;
- passwords stored exclusively using secure password hashing;
- no credentials or secrets exposed in the frontend, logs, or API responses.

Implement two roles:

- **Administrator**: full access, including user management;
- **HR Manager**: access to employee, CV, and turnover management, but no access to administrator management.

The administrator panel must allow administrators to:

- create users;
- change user roles;
- deactivate accounts;
- reactivate accounts.

A deactivated user must immediately lose access and must not be able to create new authenticated sessions.

Use Redis for application sessions.

Use PostgreSQL as the authoritative data source for users and authorisation-related data.

Protect every relevant backend endpoint with authentication and role-based authorisation.

Do not expose credentials, connection strings, tokens, session identifiers, or storage secrets in:

- frontend code;
- browser responses;
- browser storage beyond what is strictly required for secure session handling;
- logs;
- error messages;
- API payloads.

After completing this phase, deploy the required backend changes and verify:

- first-administrator setup;
- login;
- logout;
- session persistence;
- session expiration;
- protected-page redirects;
- protected API behaviour;
- administrator and HR Manager permissions;
- deactivated-account access denial.

---

# Phase 2 — Employee Management, Files, and CVs

## Employee management

Implement a complete employee CRUD using real persisted data.

Each employee must support:

- first name and surname;
- email address;
- telephone number;
- unique employee ID;
- department;
- company role;
- manager;
- hire date;
- contract type;
- status: active, leaving, or terminated;
- departure date;
- departure reason;
- notes;
- photograph;
- CV.

Use PostgreSQL as the authoritative source for:

- employees;
- departments;
- managers and reporting relationships;
- employment status;
- employment events.

The employee list must support:

- search;
- filters by department, role, and status;
- sorting;
- pagination;
- empty states;
- loading states;
- error states;
- access to the complete employee profile.

The employee profile must show:

- personal details;
- photograph;
- current employment situation;
- employment event history;
- CV information.

## Photographs and CV files

Allow users to upload, replace, view, and delete:

- one employee photograph;
- one or more CV files in PDF format.

Maintain a simple version history for CV files.

Validate file type and file size on both the frontend and backend.

Use S3 for photographs and PDF files.

The browser must not connect directly to the storage service and must never receive storage credentials.

All file operations must go through protected backend endpoints.

## Structured CV profiles

For every CV, store an editable structured profile containing:

- professional summary;
- skills;
- work experience;
- education;
- languages;
- date of the latest update.

Use MongoDB for:

- structured CV profiles;
- CV version history and related metadata.

Do not implement AI-based CV parsing. In this version, structured CV information must be entered and maintained manually.

Ensure that file metadata, version history, and structured CV data remain correctly associated with the corresponding employee.

Handle partial failures safely. For example, a failed storage or MongoDB operation must not leave inconsistent PostgreSQL records or make the entire interface crash.

After every coherent group of backend changes, perform the required deployment.

Before completing this phase, verify with real test data:

- employee creation;
- employee editing;
- employee search and filtering;
- access to the complete employee profile;
- photograph upload, display, replacement, and deletion;
- PDF CV upload, display, versioning, replacement, and deletion;
- structured CV profile creation and editing;
- validation of unsupported or oversized files;
- authorisation of every employee and file endpoint.

---

# Phase 3 — Turnover, Dashboard, User Administration, and UX

## Turnover and employment events

Create a reliable employment-event history containing at least:

- hiring;
- transfer;
- termination.

Turnover must be calculated from real data and actual employment events.

Do not use hardcoded, random, or simulated figures.

Implement an HR dashboard with:

- total number of employees;
- active employees;
- new hires during the selected period;
- departures during the selected period;
- turnover percentage;
- employee distribution by department;
- monthly hiring and departure trends;
- latest personnel events.

Allow the user to:

- select the analysis period;
- filter dashboard data by department.

Use Redis to cache dashboard statistics.

Employee and employment-event changes must correctly invalidate all affected cache entries.

Use PostgreSQL as the authoritative source for dashboard and turnover calculations.

## User administration

Create an administrator-only user-management section that supports:

- user creation;
- role changes;
- account deactivation;
- account reactivation;
- clear account-status visibility;
- validation and understandable error messages.

HR Managers must not be able to open or use administrator-management pages or APIs.

## Professional user experience

Create a professional, consistent, responsive, and accessible interface.

Include:

- side navigation;
- dashboard;
- employees section;
- turnover section;
- user administration section;
- profile menu;
- logout action;
- forms with validation;
- confirmation prompts for destructive operations;
- clear notifications;
- skeletons or loading indicators;
- safe error handling without blank pages;
- understandable messages without stack traces or sensitive information.

The interface must be in Italian.

A malformed API response or the failure of a single service must not crash the entire interface.

Implement defensive response handling and appropriate error boundaries or equivalent safeguards.

The application must work:

- in the current development environment;
- after deployment;
- without hardcoded domains, hosts, or URLs.

Use all available components for their intended responsibilities:

- PostgreSQL for users, employees, departments, and employment events;
- MongoDB for structured CV profiles and CV version history;
- S3 for photographs and PDF files;
- Redis for application sessions and dashboard-statistics caching.

Use only the official integrations and bindings already available in the project.

Do not invent:

- hostnames;
- URLs;
- credentials;
- secrets;
- environment variables;
- unsupported service bindings.

Do not connect the frontend directly to infrastructure services.

After every coherent group of backend changes, perform the required deployment.

Run the frontend typecheck and build before the final verification phase.

---

# Phase 4 — Testing, Deployment, and Final Browser Verification

Proceed autonomously until the application is complete.

When an error occurs:

- identify and fix the actual root cause;
- redeploy when required;
- continue the work;
- do not ask the user to execute technical commands.

Do not consider mocked responses, static placeholders, or frontend-only behaviour to be a valid implementation.

Use recognisable test data. Remove it at the end when removal does not prevent the user from inspecting the completed application.

Before declaring the work complete, verify the real deployed application in the browser.

The final browser verification must include:

1. initial administrator setup;
2. login and redirect to the dashboard;
3. denied access to protected pages without authentication;
4. creation of an employee;
5. editing and searching for the employee;
6. uploading and viewing the employee photograph and CV;
7. updating the structured CV profile;
8. recording an employee departure;
9. automatic update of turnover statistics;
10. creation and management of an HR Manager account;
11. verification that the HR Manager cannot access administrator management;
12. account deactivation and verification that the deactivated user can no longer log in;
13. logout and session invalidation;
14. verification of filtering, sorting, pagination, loading, empty, and error states;
15. verification that unsupported or oversized files are rejected safely;
16. verification that dashboard caching is invalidated after relevant employee or employment-event changes;
17. verification that the interface remains usable when an individual backend service returns an unexpected response;
18. confirmation that there are no errors in the browser console;
19. confirmation that no credentials, secrets, tokens, stack traces, internal URLs, or sensitive connection details appear in browser responses, logs, or console output;
20. confirmation that the deployed application uses real PostgreSQL, MongoDB, S3, and Redis integrations.

Do not declare the work complete until all of the following work together in the actually deployed application:

- authentication;
- authorisation;
- employee CRUD;
- photographs;
- CV files and version history;
- structured CV profiles;
- employment events;
- turnover calculations;
- dashboard;
- user administration;
- responsive navigation;
- error handling;
- session invalidation;
- backend API protection.

At the end, provide a concise completion report containing:

- the implemented architecture;
- the data model used in each service;
- the completed checklist;
- deployments performed;
- tests, typechecks, and builds executed;
- browser scenarios verified;
- any remaining known limitation, if one genuinely exists.
