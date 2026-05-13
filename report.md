# Petchem Project Report — VMS & CMS

**Author:** Abhay Maheshwari
**Role:** Software Development Intern
**Team/Department:** Petchem IT
**Manager/Mentor:** Mrs. Madhurika Tiwari
**Organization:** Reliance Industries Limited (RIL)

**Projects:** Petchem Visitor Management System (VMS) · Petchem Content Management System (CMS)
**Technology Stack:** Angular 19 (Frontend) · Spring Boot / Java (Backend) · MySQL (Database) · Redis (Caching) · AWS S3 (Media Storage) · Kubernetes (Deployment) · Istio (Service Mesh)
**Reporting Period:** 11 January 2026 – 7 May 2026
**Duration:** ~17 Weeks
**Total Tasks Completed:** 160+ (VMS) · 55+ (CMS)

---

## Executive Summary

Over the course of approximately **17 weeks**, two major enterprise projects were developed and delivered under Petchem IT at Reliance Industries Limited:

1. **Petchem Visitor Management System (VMS)** — A full-stack enterprise visitor management application covering **160+ tasks** including UI/UX overhaul, feature development, backend engineering, security hardening, vulnerability remediation, infrastructure fixes, data encryption, and accessibility/responsive design compliance.
2. **Petchem Content Management System (CMS)** — A dynamic content management platform for the R|Elan™ brand website covering **55+ tasks** including CMS-driven dynamic content, admin panel development, image optimization, section reordering, media management via AWS S3, QA/Dev environment hardening, Strapi v4 evaluation, and UI migration from legacy designs.

The internship began with a foundational **Customer Management System (CMS CRUD)** project to master the core technology stack before transitioning into the VMS development. From late April 2026, work expanded to include the **Petchem CMS** project in parallel.

### Key Highlights

| Area | Achievements |
|------|-------------|
| **UI/UX** | Complete visual overhaul with glassmorphism design, responsive layouts, keyboard shortcuts, premium form inputs, real-time input masking, and modal dialogs |
| **Features** | Visitor history, column sorting, internal/external visitor filters, multi-zone allocation, draggable zone maps, dashboard stats, keyboard shortcuts cheatsheet, auto-fetch employee details via AD, internal employee lookup, time duration tracking, reminder checkout notifications |
| **Security** | JWT authentication, clickjacking defense (multi-layered), HP Fortify remediation, Kubernetes secrets migration, CSRF protection, frame-busting scripts, AES-256 encryption for PII data, OTP dual-mode (SMS + email) |
| **Backend** | Role-based access control (RBAC) harmonization, DTO validation with referential integrity, performance caching, SCSS migration, IAM token refresh, bootstrap.yml migration |
| **Infrastructure** | Kubernetes ConfigMap fixes, VirtualService routing, QA/Dev environment configuration, database connection troubleshooting, CORS configuration, Swagger API documentation updates |
| **Code Quality** | SonarQube code smell remediation, WCAG 2-A accessibility compliance, BlackDuck vulnerability analysis, npm dependency security audit |
| **CMS** | Dynamic content rendering, admin panel page editor, section reordering with persistence, CMS-driven media (images & YouTube), image compression & lazy loading, S3 bucket migration, legacy UI migration, Trendbook/EarthTee/Circular Design Challenge CMS integration |

---

## Category-wise Task Breakdown

### VMS Categories

| Category | Count | Description |
|----------|-------|-------------|
| UI/UX | 30 | Visual design, responsive layouts, form styling, dialog migrations, input masking |
| Feature | 35 | New functional capabilities and enhancements |
| Security | 25 | Authentication, authorization, vulnerability remediation, encryption |
| Backend | 27 | API fixes, performance, validation, role-based logic, AD integration |
| Infrastructure | 15 | Kubernetes, ConfigMap, VirtualService, deployment, CORS, Swagger |
| Other | 14 | Debugging, diagnostics, configuration |
| Security/Vulnerability | 3 | Dedicated vulnerability assessments and audits |
| Documentation | 6 | Reports, screenshots, project overview, handoff materials |

### CMS Categories

| Category | Count | Description |
|----------|-------|-------------|
| CMS / Admin Panel | 12 | Page editor configuration, block alias mapping, admin content registration, media manager |
| UI/UX Migration | 10 | Legacy design migration, Trendbook, Article, Timeline, EarthTee, home page parity redesigns |
| Media & Performance | 10 | Image compression, lazy loading, S3 bucket migration, chunked downloads, blob loading UX, quality tuning |
| Feature | 8 | Section reordering, collapsible navigation, dynamic section templates, newsletter additions, testimonials |
| Infrastructure | 8 | QA/Dev config hardening, runtime URL normalization, CORS fixes, Docker dependency triage, upload limits |
| Security | 3 | Social embed security (iframe → embed migration), CORS server-side fix, endpoint alignment |
| Documentation | 4 | CMS architecture explanation, CloudFront evaluation, technical guides, extreme-detail work report |

---

## Week-wise Detailed Task Report

---

### Week 0: 11–17 January 2026 — *Orientation: Customer Management System (CMS CRUD)*

Foundational internship project — building a complete 3-tier CRUD application to master the core technology stack (Spring Boot & Angular).

| # | Task | Category | Summary |
|---|------|----------|---------|
| — | CMS Backend Setup | Backend | Formulated Customer Entity, JPA Repository, and Service layer for core CRUD business logic |
| — | CMS REST API Implementation | Backend | Built REST controllers for POST/GET/PUT/DELETE operations with JSON responses |
| — | CMS Angular Service | Feature | Created Angular service with RxJS, error handling, retry logic, and cache-busting headers |
| — | CMS UI Component Development | UI/UX | Built responsive components for Customer List (GetAll), Creation (Post), and Modification (Update) |
| — | CMS Routing & Navigation | Feature | Implemented application routing with guards and a centralized layout with navigation bar |
| — | CMS Project Documentation | Documentation | Drafted a comprehensive 3-tier architecture explanation for the CMS project |

#### Orientation Project Deep-Dive: Customer Management System

**Architecture Overview:**
The project implements a **3-tier architecture** with a Spring Boot backend and an Angular frontend.
- **Backend (Spring Boot):** Handles data operations via JPA/MySQL and provides REST API endpoints.
- **Frontend (Angular):** Provides a user interface for managing customers, communicating via HTTP.

**Key Backend Components:**
- **Customer Entity:** Mapped to MySQL using JPA annotations; utilizes Lombok for boilerplate reduction.
- **CustomerRepository:** Extends `JpaRepository` for instant CRUD capability.
- **Service Layer:** Houses the business logic for `post`, `get`, `put`, and `delete` operations.
- **Controller Layer:** Exposes JSON endpoints with proper status codes and cache-control headers.

**Key Frontend Components:**
- **CustomerService:** Centralized HTTP handler with error handling, timeout protection (10s), and exponential backoff retry logic.
- **Components:** Modular UI for viewing (GetAll), adding (Post), and editing (Update) records with two-way data binding and form validation.

**Technologies Mastered:** Spring Boot 4.0.1, Spring Data JPA, MySQL, Lombok, Java 17, Angular 21, TypeScript, RxJS, Angular Forms & Router.

---

### Week 1: 18–24 January 2026 — *Project Onboarding & Repository Migration*

| # | Task | Category | Summary |
|---|------|----------|---------|
| — | Project Onboarding | Other | Understanding the VMS project architecture, codebase walkthrough, and development environment setup |
| — | Frontend Repo Migration | Infrastructure | Migrated the entire Angular frontend codebase from `Test_PC_AJ_VMS_UI` to the official `PC_AJ_VMS_UI` repository (commit `f59cf5c1`, Jan 20) |
| — | Backend Repo Migration | Infrastructure | Migrated the Spring Boot microservice codebase from `Test_PC_SB_VMS_Microservice` to the official `PC_SB_VMS_Microservice` repository (commit `c65ce79b`, Jan 20) |
| — | Admin Panel — Initial Build | Feature | Built and committed the initial Admin Panel for VMS on both frontend and backend repositories (commit `105ef535` / `310acdba`, Jan 23) |

---

### Week 2: 25–31 January 2026 — *Backend Architecture & JWT Design*

| # | Task | Category | Summary |
|---|------|----------|---------|
| — | Admin Panel Route Creation | Backend | Created the `/admin/` route and page structure for the VMS Admin Panel |
| — | JWT Token Enhancement | Security | Enhanced JWT payload to include `roleCode`, `roleId`, and `warehouseName` — eliminates repeated DB lookups on every action |
| — | Database Schema Design (Joins) | Backend | Designed cross-table joins across `vms_users`, `vms_roles`, `vms_warehouse`, and `zones` |
| — | Fail-safe Left Joins | Backend | Implemented Left Join pattern with `"unknown"` fallback when DB returns null — prevents crashes on missing data |
| — | RBAC System Design | Security | Designed Role-Based Access Control system; locked `/admin/**` routes to admin roles only |
| — | JwtAuthFilter & Security Config | Security | Created `JwtAuthFilter` with security config for admin route access control |
| — | AuthService — Login Restriction | Security | Restricted login to only registered `vms_users`; non-registered users are blocked |
| — | VmsUserRepo with Left Join | Backend | Created `VmsUserRepo` with Left Join queries for enriched user data retrieval |
| — | General Update & Codebase Refinement | Other | Pushed general codebase updates and refinements across frontend and backend (commit `1b697f23` / `4e11852b`, Jan 27) |
| — | Zonal Coordinator Role | Feature | Added Zonal Coordinator role with full role mapping and access control (commit `acfd2991` / `ac2ffc65`, Jan 29) |
| — | Multiple Features & Filters | Feature | Fixed and implemented multiple features including visitor request filters across frontend and backend (commit `be25fc53` / `2fd87952`, Jan 30) |

---

### Week 3: 1–7 February 2026 — *Services, DTOs & Warehouse Layering*

| # | Task | Category | Summary |
|---|------|----------|---------|
| — | External OTP Service Integration | Security | Enhanced External OTP Service to generate JWT tokens and create VMS-specific tokens; updated `JwtUtil.java` |
| — | AdminUserServices Creation | Backend | Built `adminUserServices` for user & role management with RBAC enforcement |
| — | AdminController REST API | Backend | Created `adminController.java` with REST endpoints for all Admin operations |
| — | DTO Layer Design | Backend | Created `AdminUserDTO`, `ReportDTO`, `ReportFilterDTO`, and `WarehouseDTO` for clean data transfer |
| — | Warehouse Three-Layer Architecture | Backend | Implemented full warehouse layering — Entity (actual DB), Repository (DB access), DTO (filtered display) |
| — | Error Handler — OTP Rate Limiting | Security | Added error handler for excessive OTP requests — shows meaningful error instead of generic 400 Bad Request |
| — | Toaster Notification System Design | UI/UX | Designed comprehensive toaster notification system covering OTP, Admin, and Visitor events |
| — | Mail Notification System | Feature | Implemented email notifications for check-in, checkout, and visitor request creation events |
| — | Review Fixes — Mobile OTP, Mails, Disabled Buttons | Other | Addressed code review suggestions: fixed mobile OTP flow, mail notifications, and disabled button behavior (commit `0dd943d4`, Feb 2) |
| — | Fixed Toasters & Multi-Company Support | Feature | Fixed toaster notifications and implemented multi-company support for users (commit `0d4559a1`, Feb 3) |
| — | JWT, Zonal Admin & Multi-Company Schema Fix | Backend | Fixed JWT implementation, updated database schema for zonal administration and multi-company allocation (commit `da0dee79`, Feb 4) |
| — | Visitor Request Filters Fix | UI/UX | Fixed CSS and logic for visitor request filters (commits `350a9258`, `54851dfc`, Feb 4) |
| — | ConfigSetup Repository Creation | Infrastructure | Created `PC_AJ_ConfigSetup` repository with `README.md`, `PC_AJ_ConfigSetup.properties`, and environment JSONs (`dev.json`, `qa.json`, `prod.json`) (Feb 4–5) |
| — | CI/CD Pipeline Setup | Infrastructure | Set up CI/CD pipeline with Azure Pipelines for automated builds; configured environment replication for prod and QA (Feb 5) |
| — | Production Build Fixes | Infrastructure | Attempted and iterated on production build fixes across the frontend (commits `921cd07d`, `64ade6ab`, Feb 6) |
| — | ConfigMap Repository Creation | Infrastructure | Created `PC_SB_VMS_ConfigMap` repository with initial push including dev/qa configuration (commit `b9782e7c`, Feb 6) |

---

### Week 4: 8–11 February 2026 — *Admin Features & Security Logic*

| # | Task | Category | Summary |
|---|------|----------|---------|
| — | Super Admin Company Management | Feature | Enabled Super Admins to add/edit companies through the admin panel |
| — | Warehouse Auto-Index | Feature | Implemented auto-increment for Warehouse ID (`w-id`) when adding new warehouses — removed manual ID input |
| — | Visitor ID Generation | Feature | Implemented visitor ID generation based on company association |
| — | Role Allocation Logic | Security | Enforced senior-to-junior role allocation rule — prevents lower roles from assigning higher roles |
| — | Security Portal — Warehouse Check-ins | Feature | Built security officer check-in flow scoped to their assigned warehouse |
| — | Sidebar Data Fetching via JWT | Feature | Implemented sidebar data population (Company/Role/Warehouse mapping) through JWT claims instead of separate DB calls |
| — | OTP Response Handling | Security | Implemented OTP response manipulation and 3+ fail attempt lockout logic |
| — | User Management Search & Filters | Feature | Added search functionality and role-based filtering to User Management; added zonal and company filtering to Warehouse Management |
| — | Disable vs. Error Pattern | UI/UX | Replaced "Not Allowed" error toasters with disabled buttons for unauthorized actions |
| — | Port & Artifact DevOps Configuration | Infrastructure | Configured port mappings and `artifacts.devops` structure for microservice deployment (commit `e2fb128b`, Feb 9) |
| — | ConfigSetup Pipeline & Property Fixes | Infrastructure | Fixed `PC_AJ_ConfigSetup.properties`, deleted incorrect Azure pipeline file, iterated on `dev.json` (Feb 9–10) |
| — | HTTP to HTTPS Migration | Security | Migrated all API endpoints from HTTP to HTTPS across configuration files (commit `8f417065`, Feb 11) |

---

### Week 5: 12–16 February 2026 — *Foundation & Core UI Overhaul*

#### Day 1 — Wednesday, 12 February 2026 (11 Tasks)

| # | Task | Category | Summary |
|---|------|----------|---------|
| 1 | Improve Table Layout and UI | UI/UX | Comprehensive visual refinements — compact date formatting, text truncation, improved badge contrast, glassmorphic unified header, standardized `border-radius` (12px) and heights (44px) |
| 2 | Revert Visitor List Layout | UI/UX | Separated visitor name and secondary info into distinct columns; made entire table rows clickable with hover feedback |
| 3 | Merge Header and Filters UI | UI/UX | Merged the separate header and filter bar into a single cohesive "Unified Header" section with perfect alignment |
| 4 | Polishing the User Management UI | UI/UX | Enhanced User Management with unified glassmorphic header, modern role/status badges, refined form layout, filtered-out raw IDs |
| 5 | Reuse PFP View Style in Personal Profile | UI/UX | Investigated profile picture (PFP) styling to reuse across admin and personal profile views |
| 6 | Updating the Theme Color to Blue | UI/UX | Migrated all purple theme references to a cohesive blue theme across visitor-requests, header, admin-reports, and visitor type dialog |
| 7 | Replace Native Popups with Custom UI | Feature | Replaced all native browser `confirm()` dialogs with a custom `ConfirmationDialogComponent` supporting severity levels |
| 8 | Initializing Reports with Default Data | Feature | Modified Reports page to auto-load data on initialization with a 1-year default date range |
| 9 | Fix Data Visibility Issue | Backend | Fixed backend role-based filtering so all roles see correct data; ensured `companyId`, `warehouseId`, and `zoneId` are auto-resolved |
| 10 | Zone Page Revamp — Compass Map Visuals | UI/UX | Completely revamped Zone Management page with a spatial compass-map layout, search/sort functionality, and color-coded utilization bars |
| 11 | Allow Super Admins to CRUD Other Super Admins | Feature | Updated both frontend and backend to allow Super Admins to manage other Super Admin accounts |

#### Day 2 — Thursday, 13 February 2026 (4 Tasks)

| # | Task | Category | Summary |
|---|------|----------|---------|
| 12 | Implement Link Fixes | Infrastructure | Fixed VirtualService redirects in `qa.yml` and `dev.yml`; added asset routing for Angular bundles |
| 13 | Resolve PC_SB_VMS_Microservice Build Failure | Infrastructure | Analyzed build failure logs related to missing test scripts in `artifacts.devops/tests` |
| 14 | Enable Multiple Zone Allocation | Feature | Updated zone selection to support multiple zones for Zonal Coordinators; added role mapping and route guards |
| 15 | Warehouse Mapping Fix | Backend | Fixed warehouse lookup to prioritize `warehouseId` over name-based lookup; fixed Zonal Coordinator visibility with role ID string handling |

#### Day 3 — Monday, 16 February 2026 (4 Tasks)

| # | Task | Category | Summary |
|---|------|----------|---------|
| 16 | Visitor History Implementation | Feature | Full-stack implementation — backend `/api/visitor/history` endpoint, `VisitorHistoryDialogComponent`, history buttons in Security Dashboard and Visitor Requests |
| 17 | Dummy Visitor Requests | Other | Created extensive SQL seed script for 39+ dummy visitor requests across all warehouses with varied statuses |
| 18 | Add Filter for Internal and External Entries | Feature | End-to-end visitor type filter — added `createdType` to backend DTO/repository/service; frontend dropdown with cumulative filtering |
| 19 | Debugging and Fixing QA Site Availability | Infrastructure | Fixed HTTPS redirect scheme in VirtualService, created `qa.json`, modified Angular build configuration to flatten output for QA |

---

### Week 6: 17–23 February 2026 — *Feature Polish & Security*

#### Day 1 — Tuesday, 17 February 2026 (3 Tasks)

| # | Task | Category | Summary |
|---|------|----------|---------|
| 20 | Revamp Button Design & Layout | UI/UX | Unified action bar at the bottom of Visitor Details; premium gradient for Check In/Out; glassmorphic style for History button |
| 21 | Diagnose Login Connection Issue | Other | Investigated API URL configuration across `environment.ts`, `environment.prod.ts`, and `proxy.conf.json` |
| 22 | Disable Check-In Button for Invalid Requests | Feature | Added `isCheckInDisabled` logic with tooltip; compacted Visitor Details dialog to eliminate scrollbar |

---

### Week 7: 2–8 March 2026 — *Auth, Performance & Admin Enhancements*

#### Day 1 — Monday, 2 March 2026 (1 Task)

| # | Task | Category | Summary |
|---|------|----------|---------|
| 23 | Local Auth Bypass Removal | Security | Removed dev-login bypass, restored standard SSO flow, implemented fallback for IAM returning `'na'` user, enriched user data from DB |

#### Day 2 — Wednesday, 4 March 2026 (10 Tasks)

| # | Task | Category | Summary |
|---|------|----------|---------|
| 24 | Debugging 503 Service Unavailable | Other | Investigated 503 error on `/auth/login` — checked port mappings, liveness/readiness probes, gateway configuration |
| 25 | Performance Troubleshooting | Backend | Implemented Spring `@Cacheable` for Company/Warehouse/Zone repositories; added `@EnableCaching`; replacing N+1 query pattern |
| 26 | Updating Manual Testing Guide | Documentation | Updated manual testing guide with roles and test data |
| 27 | Implementing Column Sorting | Feature | Full-stack column sorting — backend DTO/Service support for dynamic sorting; frontend `MatSort` integration with sort indicators |
| 28 | Resolve Backend Connection Issue | Other | Switched frontend to dev backend server (`petchemvmsdev.ril.com`); updated `environment.ts` and `environment.json` |
| 29 | Make User Profile Responsive | UI/UX | Dynamic sidebar widths (`min(400px, 90vw)`), media queries for heights below 800px/650px, auto-scaling avatars and fonts |
| 30 | Update Profile Styling | UI/UX | Restyled "My Profile" panel to match admin "User Details" layout — restructured into Account Information and Access Management sections |
| 31 | Fix Warehouse Update Toaster Message | Backend | Fixed incorrect "added" message on warehouse update; corrected primary key field from `id` to `warehouseId` |
| 32 | Allow Super Admins to Add Zones | Backend | Added `@GeneratedValue(strategy = GenerationType.IDENTITY)` to Zone entity for auto-ID generation |
| 33 | Improve Warehouse Management Visuals | UI/UX | Premium glassmorphic form card, gradient icon containers, iconographic enhancements, micro-animations |

#### Day 3 — Thursday, 5 March 2026 (4 Tasks)

| # | Task | Category | Summary |
|---|------|----------|---------|
| 34 | Troubleshooting Database Connection Error | Other | Investigated database configuration issues in `dev.yml` and `application.yml` |
| 35 | Premium Input Form Implementation | UI/UX | Global form overhaul — external static labels, `backdrop-filter: blur` effects, synchronized input/select heights, refined shadows |
| 36 | Allow Visitor Details for Past Visitors | Feature | Planned logic to allow opening visitor details for non-today visitors while disabling check-in |
| 37 | Delete Pending Visitor Requests | Feature | Added UI and backend API to change visitor request status to "deleted" when request is "pending" |

#### Day 4 — Friday, 6 March 2026 (8 Tasks)

| # | Task | Category | Summary |
|---|------|----------|---------|
| 38 | Fix User Warehouse Assignment Bug | Backend | Implemented `filterWarehousesByCompany` helper to auto-purge warehouses when a company is removed from user profile |
| 39 | Admin Users Table UX Enhancements | UI/UX | Merged Warehouse+Zone into "Access Scope" column, +N tooltip popovers, role-based row tints, scope indicator icons, frozen first columns |
| 40 | Add Sorting & Filtering to Warehouse Management | Feature | Added `MatTableDataSource`, `MatSort`, search filters, and clear-filter functionality to warehouse table |
| 41 | Fix Multi-Warehouse Visitor Request Creation | Backend | Fixed frontend auto-selection for multi-warehouse managers; fixed backend eager fallback preventing database mismatch corruption |
| 42 | Fixing Hibernate SQL Logging | Other | Configured Hibernate SQL logging in terminal for debugging |
| 43 | Fix Dashboard Requests Count Discrepancy | Backend | Added RBAC-scoped `COUNT` queries to `VisitorRequestRepository`; added "Scheduled" view mode to Security Landing |
| 44 | Keyboard Shortcuts Implementation | Feature | Planned comprehensive keyboard shortcut system (implemented in Task 46) |
| 45 | Migrate Inline Forms to Popups | UI/UX | Migrated Company, Warehouse, and User forms from inline to modal dialogs with unified `_dialog-styles.scss` |

#### Day 5 — Saturday, 7 March 2026 (1 Task)

| # | Task | Category | Summary |
|---|------|----------|---------|
| 46 | Implement Keyboard Shortcuts | Feature | Full keyboard shortcut system — `Alt+Q` cheatsheet, `Alt+V/I/S/L/P` navigation, `Ctrl+Enter` submit, `Escape` cancel/blur, contextual search focusing |

---

### Week 8: 9–15 March 2026 — *Security Hardening & Code Quality*

#### Day 1 — Sunday, 9 March 2026 (6 Tasks)

| # | Task | Category | Summary |
|---|------|----------|---------|
| 47 | Cache Synchronization Planning | Backend | Identified stale cache mechanism in `AdminService`; proposed RxJS `shareReplay` invalidation strategies |
| 48 | Admin Visibility Fix | Backend | Fixed `WarehouseService` role string verification bug causing dashboard/table count mismatch for Admin users |
| 49 | Cache Synchronization Implementation | Backend | Implemented cache invalidation — clear `warehousesCache$`, `zonesCache$`, `companiesCache$` on any CRUD mutation |
| 50 | Fix `<th>` Accessibility Issues | UI/UX | Added `scope="col"` and `aria-label` to all tables; fixed code smells in SCSS files; removed commented code |
| 51 | Debug Configuration Loading Issue | Infrastructure | Fixed `qa.json` URL synchronization, `AppInitService` fallbacks, VirtualService match blocks, and double-slash rewrite issue |
| 52 | Comprehensive Sonar Fixes (Batch) | Security | Fixed 50+ SonarQube code smells — unused DTOs, broad catch blocks, nested ternaries, duplicate code extraction, dedicated exceptions creation |

#### Day 2 — Monday, 10 March 2026 (2 Tasks)

| # | Task | Category | Summary |
|---|------|----------|---------|
| 53 | Vulnerability Assessment | Security/Vulnerability | Full 9-point security audit — authentication/authorization, hardcoded secrets, security headers, CORS, CSRF, file upload, OTP flooding, XSS, outdated libraries |
| 54 | Project Responsiveness | UI/UX | Comprehensive mobile-responsive design across ALL pages — 25+ component files updated with media queries, flex-wrap, 1-column layouts, horizontal scroll tables |

#### Day 3 — Tuesday, 11 March 2026 (4 Tasks)

| # | Task | Category | Summary |
|---|------|----------|---------|
| 55 | Security Hardening (HP Fortify) | Security | Multi-phase hardening — replaced `java.util.Random` with `SecureRandom`, refactored error handling, sanitized logs, externalized secrets, renamed password references, CSRF interceptor |
| 56 | Fixing K8S Deployment Database Connection | Infrastructure | Fixed `spring.application.name` mismatch, added `spring.config.import`, aligned ConfigMap keys across dev/qa environments |
| 57 | Analyzing BlackDuck Risk Report | Security/Vulnerability | Extracted and analyzed `PC_AJ_VMS_UI_1_0_BlackDuck_RiskReport.pdf` for open-source vulnerability assessment |
| 58 | Resolve 503 Error for /auth/login | Other | Fixed database connection failure caused by password not loading from Kubernetes ConfigMap; verified property prefix mapping |

#### Day 4 — Wednesday, 12 March 2026 (6 Tasks)

| # | Task | Category | Summary |
|---|------|----------|---------|
| 59 | Fixing the Login Request | Other | Configured local runtime with correct MySQL password; fixed `/auth/login` 400 error |
| 60 | Fix 403 Forbidden for list_warehouses | Security | Fixed Spring Security configuration allowing warehouse listing endpoint |
| 61 | SCSS Migration | UI/UX | Migrated entire project from deprecated `@import` to modern `@use`/`@forward` Sass syntax; standardized namespaces |
| 62 | Add Visit Date and Expected Time to RIL Employee Form | Feature | Added date picker and time slot selector to internal employee visitor form |
| 63 | Remediation of tar Vulnerability | Security/Vulnerability | Fixed CVE-2026-29786 by forcing `tar@7.5.11` via npm overrides |
| 64 | Remediation of Vulnerabilities (Batch 2) | Security | Remediated `serialize-javascript`, `debug`, `minipass`, `micromatch`, `cross-spawn`, `ajv-formats` — 0 audit issues |

#### Day 5 — Thursday, 13 March 2026 (3 Tasks)

| # | Task | Category | Summary |
|---|------|----------|---------|
| 65 | Project Overview | Documentation | Researched and drafted comprehensive project overview including technologies, modules, objectives, and end users |
| 66 | Fixing Build Failure | Other | Investigated `package.json` dependency conflicts causing build failure |
| 67 | Resolve Dependency Conflict | Backend | Downgraded `ngx-cookie-service` from `^21.1.0` to `^19.1.2` for Angular 19 compatibility — verified with clean `npm install` |

---

### Week 9: 17–20 March 2026 — *Infrastructure, Validation & Final Fixes*

| # | Task | Category | Summary |
|---|------|----------|---------|
| 68 | Backend Validation Fix — Complete Plan | Security | Added Jakarta validation annotations (`@Pattern`, `@NotBlank`, `@NotNull`, `@Positive`, `@Email`) across all DTOs; implemented service-layer referential integrity checks for all foreign keys |
| 69 | Migrate to Kubernetes Secrets & Fix Connectivity | Infrastructure | Replaced hardcoded credentials with `${petchemvms_db_username}` etc. across all environment files; fixed port mismatch (8080→8081) |
| 70 | Diagnose and Fix 'Add User' 400 Bad Request | Backend | Fixed unauthorized role selection, property mismatches between frontend/backend, `biometric_enabled` DB mismatch, VirtualService routing rules |
| 71 | Synchronize Warehouse Access with Company Removal | Feature | Auto-purge warehouse assignments when company is removed; restrict Zonal Coordinator access to Zone∩Company warehouses |
| 72 | Implementing Draggable Zones | Feature | Added `posX`/`posY` to Zone entity; implemented CDK drag with radial auto-symmetric layout; fixed Side Panel and permissions |
| 73 | Switch Local Backend to QA Database | Other | Configured local backend to connect to QA database for testing |
| 74 | Add JWT Authentication to All API Requests | Security | Analyzed Spring Security and JWT configuration; identified endpoints bypassing authentication |
| 75 | Clickjacking Testing | Security | Created clickjacking PoC HTML file; audited project for `X-Frame-Options` and `Content-Security-Policy` |
| 76 | Avoid Clickjacking | Security | Multi-layered clickjacking defense — backend `Content-Security-Policy: frame-ancestors 'self'`, frontend SSR headers, frame-busting JavaScript in `index.html` |
| 77 | Token Storage in Local Storage | Feature | Persisted OAuth2 access token in both `sessionStorage` and `localStorage` with fallback retrieval |
| 78 | Fixing the Report Tab | Backend | Fixed `ReportService` missing Super Admin (`roleId: 0`) check causing restricted data display |
| 79 | Fix Security Portal Dashboard Stats | UI/UX | Fixed real-time stats mapping; refined "Deleted" and "Expired" status tags with subtle `rgba(..., 0.08)` fills |
| 80 | VMS Infrastructure and UI Fixes | Other | Fixed Security Portal refresh, removed map coordinates from ZM, fixed visitor status counts, harmonized RBAC role checks in `JwtUserContext` |
| 81 | Adding Photos to VMS Documentation | Documentation | Embedded 13 UI screenshots into VMS project overview documentation for IRM Testing Team |

---

### Week 10: 23–29 March 2026 — *Token Management, Dashboard & Date Filters*

| # | Task | Category | Summary |
|---|------|----------|---------|
| 82 | Token Management & Expiry Handling | Security | Implemented JWT token lifecycle — expiration tracking, expired/deleted visitor request API endpoints, and Flutter pagination support |
| 83 | IAM-side Refresh Token Generation | Security | Built IAM-side refresh token generation flow to maintain persistent sessions without re-authentication |
| 84 | Revert & Fix Token Generation | Backend | Reverted token management changes due to issues and applied corrected IAM-side refresh token logic |
| 85 | Delete/Expired Count Fix | Backend | Fixed backend count queries for deleted and expired visitor request status tracking |
| 86 | Apply Date Filters on Every Listing Page | Feature | Applied date-range filtering across all visitor listing pages; reorganized dashboard tiles based on role hierarchy; renamed "Total Pending" → "Pending Check-out" |

---

### Week 11: 30 March–5 April 2026 — *Employee Lookup, Time Duration & Internal Visitors*

| # | Task | Category | Summary |
|---|------|----------|---------|
| 87 | Auto-Fetch Employee Details via AD | Feature | Integrated Active Directory search (`commonutilsqa.ril.com/empinfo`) to auto-populate employee details when creating internal visitor requests |
| 88 | Internal Employee Lookup | Feature | Built full-stack internal employee lookup — backend service for AD integration, frontend auto-complete, and Employee ID validation |
| 89 | Time Duration Tracking | Feature | Added expected check-in/check-out time tracking with computed visit duration display across visitor request views |
| 90 | Time Duration CSS Fix | UI/UX | Fixed styling issues in the time duration display to ensure proper alignment and responsiveness |
| 91 | Display Name Instead of Domain ID | UI/UX | Updated visitor request listings and details to show human-readable names instead of raw domain IDs |
| 92 | Phone Number Sanitization | Feature | Implemented `sanitizePhoneNumber()` utility — strips country codes (91-prefix), non-digit characters, and normalizes to 10-digit format |
| 93 | Reminder Checkout Notifications | Feature | Implemented automated email reminder notifications for visitors who haven't checked out, with backend scheduled task and email service integration |
| 94 | Swagger Documentation Update | Documentation | Updated `PC_SB_VMS_Microservice_DEV.swagger` and `_QA.swagger` with all new API endpoints |
| 95 | User Details Import Error Handling | Backend | Added comprehensive exception handling for user details import — graceful fallbacks when AD lookups fail or return partial data |
| 96 | Fetch by Employee ID | Backend | Switched user/visitor lookup from domain-based to Employee ID-based retrieval for more reliable identification |
| 97 | AD Search URL Externalization | Infrastructure | Externalized `AD_SEARCH_URL` to environment configuration (`application.yml`) instead of hardcoding — supports per-environment AD endpoints |

---

### Week 12: 6–12 April 2026 — *Bootstrap Migration & Configuration*

| # | Task | Category | Summary |
|---|------|----------|---------|
| 98 | Bootstrap.yml Migration | Infrastructure | Renamed `application.yml` to `bootstrap.yml` for proper Spring Cloud config loading order — ensures ConfigMap values are injected before application context initializes |
| 99 | ConfigMap Property Alignment | Infrastructure | Aligned all ConfigMap property keys across dev/qa environments; fixed `spring.config.import` references |
| 100 | Application-QA.yml Creation | Infrastructure | Created dedicated `application-qa.yml` profile with QA-specific database URLs, AD endpoints, and CORS origins |
| 101 | Bootstrap.yml Iterative Fixes | Infrastructure | Multiple iterations on `bootstrap.yml` to fix property loading precedence issues across Kubernetes deployments |
| 102 | Common Utils Integration | Backend | Integrated `commonutils` library for shared utility functions across microservice components |

---

### Week 13: 13–19 April 2026 — *Encryption, OTP Enhancements & Input Validation*

| # | Task | Category | Summary |
|---|------|----------|---------|
| 103 | OTP Dual-Mode (SMS + Email) | Feature | Enhanced OTP service to support both SMS and email delivery channels; user can choose preferred OTP receiving method |
| 104 | Input Validation & Real-time Masking | UI/UX | Implemented strict client-side validation with real-time input masking for PAN (5L+4D+1L), Passport (1L+7D), Aadhaar (last 4 digits), Employee ID (1L+8D), and Driver's License |
| 105 | AES-256 Encryption for Confidential Data | Security | Implemented AES-256-CBC encryption for visitor PII (mobile, email, ID proof) — 32-byte key, 16-byte IV, externalized via `ENCRYPTION_KEY`/`ENCRYPTION_IV` environment variables |
| 106 | Username Regex Fix | Security | Fixed username validation regex to properly accept corporate domain formats and special characters |
| 107 | Encrypted Email Communication | Security | Implemented decryption pipeline for encrypted PII when sending email notifications — ensures emails contain readable visitor data while storage remains encrypted |
| 108 | Search Button in Reports Page | UI/UX | Added explicit search/apply button to Reports page for triggering filtered report generation |
| 109 | Redundant Test Files Cleanup | Other | Removed redundant test files from `artifacts.devops/tests` to fix build pipeline issues |

---

### Week 14: 20–24 April 2026 — *VMS Final Polish & CMS Onboarding*

*This week marked the final production hardening of VMS alongside the beginning of dedicated CMS development work.*

---

#### 🔷 VMS — Visitor Management System

##### Day 1 — Tuesday, 22 April 2026 (2 Tasks)

| # | Task | Category | Summary |
|---|------|----------|---------|
| 110 | CORS Configuration Update | Security | Added `http://*.ril.com` to CORS allowed origins for cross-environment API accessibility |
| 111 | VMS Backend Debugging & Port Fixes | Other | Killed zombie processes on port 8081; restarted backend with QA database connection; resolved startup failures in `run_qa.ps1` |

##### Day 2 — Wednesday, 23 April 2026 (3 Tasks)

| # | Task | Category | Summary |
|---|------|----------|---------|
| 112 | OTP Dual-Mode Transaction ID Fix | Security | Fixed critical bug where "both" OTP mode (SMS + email) generated two separate transaction IDs resulting in duplicate OTPs; unified to single `transactionId` across both channels |
| 113 | HTTPS ↔ HTTP Protocol Fixes | Infrastructure | Resolved HTTPS/HTTP mismatch issues across dev/QA environments to prevent mixed-content errors |
| 114 | Dev Environment Update | Other | Applied accumulated dev environment configuration synchronization |

##### Day 3 — Thursday, 24 April 2026 (6 Tasks)

| # | Task | Category | Summary |
|---|------|----------|---------|
| 115 | Report Date Selector Dialog | Feature | Built `ReportDateSelectorDialog` component — prompts user to set start/end date on Reports page open; scoped download to only fetched (filtered) data |
| 116 | PII Masking Fix After Check-In | Security | Fixed visitor information dialog where PII data (phone, email, ID proof) became masked after check-in action; ensured unmasked data persists through check-in flow |
| 117 | Responsiveness & Email Feature Fix | UI/UX | Fixed responsive layout issues across admin reports, dashboard, and other pages; resolved email notification feature bugs |
| 118 | VMS Demo Scripting & Role-based Walkthrough | Other | Developed concise 2-minute role-based walkthrough plan; prepared shot sequences for Super Admin, Admin, and Zonal roles |
| 119 | Dummy Data Seeding (Diverse Scenarios) | Other | Generated large test datasets covering checked-in, checked-out, expired, and repeat visitors to ensure dashboard visual parity |
| 120 | Tester-Oriented Handoff Documentation | Documentation | Authored comprehensive technical documentation for IRM/Testing team covering QR replay security, token lifecycles, and error mapping |

---

#### 🟢 CMS — Content Management System (t2 Workspace)

> CMS development begins in parallel from Week 14 alongside final VMS polish.

##### Day 2 — Wednesday, 23 April 2026 (3 Tasks)

| # | Task | Category | Summary |
|---|------|----------|---------|
| C1 | Image Compression & Lazy Loading | Media & Performance | Implemented `ImageCompressionService` for client-side compression with on-the-fly downscaling and WebP conversion via Canvas API; integrated `LazyBlobSrcDirective` for browser-level lazy loading |
| C2 | R-Story Timeline Content Update | UI/UX Migration | Added 2023/2024/2025 milestones (75+ brands, 100+ brands, global expansion); reordered timeline to descending chronological order; fixed text rendering issues |
| C3 | CMS Admin Panel Overview & Demo Prep | Documentation | Researched and prepared comprehensive admin panel architecture overview for internal demo covering `ContentService`, `MediaResolverService`, page editor configuration, and CMS data flow |

---

#### 🟢 CMS — t2 Workspace Deep-Dive Tasks (VMS Feature Work)

| # | Task | Category | Summary |
|---|------|----------|---------|
| t2-1 | Visitor Seed Data Generation | Backend | Created SQL seeding script with 50+ visitor entries including encrypted PII; added checked-out, expired, deleted lifecycle states; implemented AES + Base64(IV+ciphertext) compatibility pattern |
| t2-2 | OTP Channel Expansion — Both Mode | Feature | Added "Both" (SMS + Email) OTP option to frontend and backend; full-width pill-style UI control; updated backend `mode="both"` handling in auth controller and service layer |
| t2-3 | OTP 401 Incident Troubleshooting | Security | Hardened OTP headers (Basic auth + session/access/id tokens); patched `ExternalOtpService` origin binding and sanitize fallback; patched global exception handler for empty 401 upstream bodies; identified QA token vs DEV OTP endpoint mismatch |
| t2-4 | Reports Page Search/Filter | Feature | Implemented client-side search over report dataset; added search input with filtered-vs-total count UX; updated exports to honor filtered rows; updated SCSS for layout |
| t2-5 | Internal Visitor Auto-fill Integration | Feature | Integrated internal server fetch for employee data during internal visitor creation flow (AD/domain-ID style lookup adaptation) |
| t2-6 | VMS Comprehensive Documentation | Documentation | Built comprehensive project document for IRM/testing audience — expected error behavior and status codes, JWT/token lifetime and expiry interplay, test URLs/credentials/modes, QR security/replay/expiry, scheduled expiry mechanics |
| t2-7 | Demo Narrative & Shot Planning | Documentation | Built complete 2-minute demo flow covering multiple roles and visitor types (internal/external/returning); planned role-wise shot sequences |

---

### Strapi PoC Phase — Late April 2026 (t4 Workspace)

*Parallel evaluation of Strapi v4 (headless CMS) in the `desktop/t4` workspace to assess viability for admin-driven content editing before committing to the custom Spring Boot CMS backend.*

| # | Task | Category | Summary |
|---|------|----------|---------|
| S1 | Strapi Headless CMS Evaluation & Local Setup | CMS / Admin Panel | Evaluated Strapi v4 as a potential headless CMS; configured local instance on port 1337 with PostgreSQL; provisioned Azure App Service deployment plan; documented 8-part integration architecture (Strapi → Angular REST API → dynamic content) |
| S2 | Strapi Content Type Design | CMS / Admin Panel | Designed 6 content type schemas: `GlobalSEO` (Single Type), `PageMeta`, `HeroSection`, `TextBlock`, `MediaBlock` (Collection Types), `NavigationItem`; all indexed by `pageSlug` for route-based content lookup |
| S3 | Angular CMS Service Prototype | Feature | Built `CmsService` at `src/app/core/services/cms.service.ts` using `HttpClient` with `shareReplay(1)` caching, typed interfaces (`HeroContent`, `PageMeta`), graceful fallback for CMS-unreachable states, and environment externalization |
| S4 | CMS Data Seeding Scripts | Other | Created `seed-cms-data.js` and `seed-demo-text.js` scripts to populate Strapi with test page content (home + about pages), hero sections, text blocks, and page meta — with auto-publish and duplicate-detection logic |
| S5 | "No-Change" Debugging Loop | Other | Iteratively debugged persistent "No Change Visible" issue — identified mapping mismatches between Strapi v4 JSON shape (`data[].attributes...`) and frontend renderer expectations; diagnosed slug mismatch and cache/state invalidation gaps |
| S6 | Strapi Role & Token Configuration | Security | Configured Strapi roles (Admin: full CRUD + publish, Editor: edit + draft only); set up read-only public API token with `find`/`findOne` permissions only; disabled unauthenticated public API access |
| S7 | Strapi SSR Migration Planning | Feature | Architecture recommendation for SSR/prerender-centric approach for SEO + perceived performance; planned Strapi-backed CMS integration with deployment separation and data aggregation / caching / TransferState tactics |
| S8 | Strapi Home Text Integration Debug | CMS / Admin Panel | Full-stack scan of Angular home component TS/HTML/SCSS, CMS service layer, SSR/server entry and proxy configs, Strapi schemas; diagnosed and patched response-shape incompatibility (flattened vs. `data[].attributes`) |

---

#### 🟢 CMS — Early Development (23–24 April 2026, t3 Workspace)

##### Day 3 — Thursday, 24 April 2026 (4 Tasks)

| # | Task | Category | Summary |
|---|------|----------|---------|
| C4 | Header Navigation Rename | UI/UX | Changed "R-Commitment to Green" menu label to "R-Commitment" across header navigation and dynamic content rendering logic |
| C5 | Collapsible Navigation Menus | Feature | Implemented collapsible/expandable behavior for nested navigation sections in the CMS header component |
| C6 | Image Gallery Masonry Layout | UI/UX | Fixed variable-size image card layout — implemented balanced-height masonry layout with gap equalization so left/right column cards align at top and bottom |
| C7 | R-Story Timeline UI Redesign | UI/UX Migration | Redesigned the R-Story timeline section to match legacy reference design (`t5` files); applied new SCSS styling via `_timeline.scss` |

---

### Week 15: 4 May 2026 — *CMS Section Reordering & Infrastructure*

*(No VMS work this week — full focus on CMS)*

#### 🟢 CMS — Day 1 — Sunday, 4 May 2026 (10 Tasks)

| # | Task | Category | Summary |
|---|------|----------|---------|
| C8 | Section Reordering with Persistence | Feature | Implemented drag-and-drop section reordering across all CMS pages using CDK Drag; added backend persistence so reorder changes survive page refresh; debugged ordering issues where "Top Stories" and "R Experience" sections reset to incorrect positions |
| C9 | CMS Section Templates — Image+Text & YouTube Video | Feature | Added three new section templates: (1) Image + Text side-by-side, (2) YouTube Video with text below, (3) YouTube Video + Text side-by-side; implemented media resolution and sanitization for YouTube embeds in `HomeComponent` |
| C10 | S3 Bucket Migration | Infrastructure | Migrated CMS media storage from default S3 bucket to `FLMBLOB_fed`; updated `environment.json`, `dev.json`, and all `ConfigMap` references across frontend and backend |
| C11 | CloudFront Architecture Review | Documentation | Evaluated CloudFront + OAC (Origin Access Control) architecture for public media serving — rated plan 9/10; documented implementation plan for eliminating pre-signed URLs on reads while keeping write path unchanged |
| C12 | Image Quality Investigation | Media & Performance | Investigated and diagnosed image quality degradation in CMS pages; identified compression pipeline as root cause; adjusted `LazyBlobSrcDirective` parameters to preserve original quality |
| C13a | QA Image Retrieval Failure Diagnosis | Infrastructure | Investigated QA-specific image failures via `/api/get-files`; identified malformed APIM context path patterns; introduced runtime URL repair logic in frontend init flow to normalize malformed APIM paths |
| C13b | QA vs Dev Config Audit | Infrastructure | Performed comprehensive cross-repo environment diff analysis across `PC_OT_CMS_ConfigSetUp`, `PC_SB_CMS_ConfigMap`, `PC_AJ_CMS_ConfigSetup`, and frontend/backend code repos — identified bucket mismatches, missing fields, URL inconsistencies, and auth endpoint gaps |
| C13c | CORS Diagnosis (Server-Side) | Security | Initiated root-cause analysis for "Invalid CORS request" errors in QA environment; prepared server-side CORS configuration fix for the CMS microservice |
| C13d | QA/Prod Config Normalization | Infrastructure | Normalized QA and production configuration files — fixed missing fields, URL consistency, and auth endpoint alignment across all config layers |
| C13e | Bucket Source Consistency Fix | Infrastructure | Forced intended bucket (`FLMBLOB_fed`) across all environments; fixed bucket mismatch that caused images to load from wrong S3 source in QA |

---

### Week 16: 5 May 2026 — *CMS Admin Panel & Component Fixes*

*(No VMS work this week — full focus on CMS)*

#### 🟢 CMS — Day 1 — Monday, 5 May 2026 (12 Tasks)

| # | Task | Category | Summary |
|---|------|----------|---------|
| C14 | Directive Compilation Fixes | Infrastructure | Resolved Angular compilation errors related to `ChunkedDownloadService` dependency injection using `@Inject`; fixed module import issues across multiple CMS components to stabilize the build |
| C15 | CMS Architecture Explanation | Documentation | Prepared detailed CMS admin panel architecture documentation covering `ContentService` data flow, `MediaResolverService` pipeline, `blockAliases` configuration, page editor component structure, and dynamic section rendering lifecycle — for knowledge transfer to team |
| C16 | R-Commitment Navigation Rename | UI/UX | Updated "R-Commitment to Green" label to "R-Commitment" in CMS header navigation (`header.component.html`) for consistency |
| C17 | Component Rendering Fix | Backend | Fixed rendering issues in multiple CMS components (R-Story, EcoGold, FeelFresh, GreenGold-Ecocean) — resolved broken section templates and padding inconsistencies across Innovation Station pages |
| C18 | Trendbook Association CMS Mapping Fix | CMS / Admin Panel | Fixed the "Associations" section on the Trendbook page — updated `blockAliases` and HTML template to properly map CMS fields; enabled content editing; redesigned UI to side-by-side Image + Text layout with "Find Out More" button |
| C19 | LFW Image Loading UX Improvement | Media & Performance | Improved Lakme Fashion Week image loading behavior — added loading-state visuals, lazy-load refinements, adjusted compression strategy to quality-priority defaults, set viewport images to eager/sync for perceived quality |
| C20 | Frontend Media Endpoint Correction | Infrastructure | Corrected frontend media endpoint to align with backend route conventions (`/api/get-files` alignment); fixed empty/invalid gallery source fallback to avoid carousel "no slides" state |
| C21 | Chunked/Parallel Blob Download | Media & Performance | Implemented parallel/chunked blob download strategy for large media files; introduced bounded-concurrency pipeline with in-flight request deduplication to reduce long-tail wait times |
| C22 | Upload Size Limit Increase | Infrastructure | Diagnosed upload max-size issues from backend and multipart config layers; raised limits toward 50 MB across Spring Boot, Nginx proxy buffers, and Kubernetes ingress annotations to support high-resolution CMS media uploads |
| C23 | CMS-to-Home Base Path Migration | Infrastructure | Progressed `/cms` to `/home` base path migration — aligned build/runtime path behaviors and downstream QA image loading expectations |
| C24 | R-Story Timeline Admin Additions | Feature | Enabled timeline item addition via CMS admin panel; refined ordering/sorting behavior for R-Story timeline entries |
| C25 | LFW Top Stories & Card Import | Feature | Enabled "Top Stories" section additions via CMS admin; implemented card data import support with ordering refinements |

---

### Week 17: 6 May 2026 — *CMS UI Migration & Media Editing*

*(No VMS work this week — full focus on CMS)*

#### 🟢 CMS — Day 1 — Tuesday, 6 May 2026 (10 Tasks)

| # | Task | Category | Summary |
|---|------|----------|---------|
| C26 | Trendbook Associations UI Redesign | UI/UX Migration | Redesigned "Our Latest Associations" section using reference `t5` design files — implemented side-by-side image-text layout, applied specific typography (font family, weight, size, letter spacing), color adjustments, and ensured full responsiveness with CMS compliance |
| C27 | Article Page UI Refactoring | UI/UX Migration | Aligned Trendbook Article page UI with legacy `t5` design — restructured "Featured Trends" section to use images with integrated overlay titles; maintained full CMS functionality for all dynamic content blocks |
| C28 | Circular Design Challenge — CMS Media Editing | CMS / Admin Panel | Enabled CMS-based content management for the "In the Media" section of Circular Design Challenge page — updated ViewModel to map `media_1`, `media_2` CMS fields; updated HTML template to iterate over dynamic media items |
| C29 | EarthTee Admin Content Registration | CMS / Admin Panel | Completed EarthTee page migration to fully dynamic CMS architecture — registered all new content blocks (highlights 7.0–3.0, video, journey steps) in `page-editor.component.ts`; ran data population script to inject legacy content into CMS database |
| C30 | Blob Fetch Latency Optimization | Media & Performance | Extended performance improvements — text-first rendering pathways, media request caching/dedup, controlled concurrency for media resolution; produced architecture planning for future scale behavior |
| C31 | Newsletter CMS Expansion | Feature | Expanded Newsletter section: add-new support, featured-image workflow adjustments, descending sort behavior fix; enabled admin-panel-driven newsletter management |
| C32 | Testimonials Section Fix | Feature | Fixed per-item testimonial behavior — resolved shared values/wrong section creation bugs; each testimonial entry now correctly maps to its own CMS block |
| C33 | Media Manager Enhancements | CMS / Admin Panel | Improved blob media upload usability in admin workflows — upload and library visibility improvements; discussed "view broader bucket inventory" capability for content administrators |
| C34 | Multi-Page Migration Sweep | UI/UX Migration | Large migration sweep across multiple R|Elan pages and sub-pages — extended dynamic editability to additional Innovation Station sections and content blocks |
| C35 | Footer & Editability Coverage Checks | CMS / Admin Panel | Validated footer content editability and verified migration coverage across all CMS-managed pages; fixed identified gaps in block alias mapping |

---

### Week 18: 7 May 2026 — *CMS Dynamic Images & Green Ambitions*

*(No VMS work this week — full focus on CMS)*

#### 🟢 CMS — Day 1 — Wednesday, 7 May 2026 (8 Tasks)

| # | Task | Category | Summary |
|---|------|----------|---------|
| C36 | CMS Editable Images — Green Ambitions Sliders | CMS / Admin Panel | Migrated "Our Green Ambitions" image slider sections to fully dynamic CMS-driven architecture — registered all six slider slots in Admin Panel; removed hardcoded fallback images; standardized absolute asset paths; suppressed 404 console errors for unresolved CMS references; integrated CSS loading spinner |
| C37 | Global Image Loader Rollout | Media & Performance | Rolled out centralized image-loader directive/class strategy for all image instances — addressed loader-too-brief, broken fallback flashes, and placeholder dimension mismatches (layout shift prevention) |
| C38 | Home Page Production Parity | UI/UX Migration | Aligned home page against production references — adjusted spacing/gaps, typography sizes/weights, section-level visual hierarchy; implemented selective editability restrictions for specific fields |
| C39 | LFW Video/Embed Work | Feature | Implemented photo-to-video embed for Lakme Fashion Week section; adjusted placement after user clarification; validated admin field exposure for `video_url` under correct LFW section |
| C40 | Social Feed Security — iframe to Embed | Security | Replaced social feed iframe strategy with safer embed approach — iterated from links-only fallback to proper embedded-post presentation for improved security posture |
| C41 | Docker Dependency Triage | Infrastructure | Analyzed Docker install failures from build logs; investigated `better-sqlite3` usage and completed removal of unused dependency; documented Node engine warning (`EBADENGINE`) with upgrade recommendation |
| C42 | Admin UI Polish & Presentation | UI/UX Migration | Continued admin usability polish and presentation adjustments — refined editing controls, field visibility, and section management workflows for upcoming demo |
| C43 | Extreme-Detail Work Report Generation | Documentation | Generated comprehensive day-wise work report with correction audit, cross-workspace coverage (t2/t3/t4), unified task inventory, and pending items checklist — `WORK_REPORT_ALL_CHATS_EXTREME_DETAIL.md` |

---

## Pending & Open Items

### High Priority

- Rebuild/redeploy latest UI + backend fixes to QA and verify deployed config parity with repo values
- Confirm cluster-side APIM context and bucket config are exactly aligned with corrected source values
- OTP external 401 full closure in QA environment — confirm with end-to-end logs
- Run deterministic Strapi edit → publish → frontend reflect checklist under stable Node/toolchain

### Medium Priority

- Finalize "Top Stories ↔ Newsletters" functional connection intent (expected behavior to be locked)
- Add/verify `.dockerignore` optimization to reduce build context size and speed CI builds
- Align runtime Node version with dependency engine requirements in Docker base image
- Internal-server autofill completion verification (t2 workspace — internal employee lookup confirmation)

### Low Priority

- Explore backend response optimization for media endpoint (lighter payload strategy)
- Optional: stronger date attribution for undated sessions via git/terminal chronology
- Explore broader bucket inventory visibility for content administrators in media manager

---

## Files & Repositories Modified

### VMS Repositories

| Repository | Description | Primary Files Modified |
|-----------|-------------|----------------------|
| `PC_AJ_VMS_UI` | Angular 19 Frontend | Component HTML/TS/SCSS files, `styles.scss`, `angular.json`, `package.json`, `environment.ts`, `app-config.conf` |
| `PC_SB_VMS_Microservice` | Spring Boot Backend | Controllers, Services, DTOs, Entities, Repositories, `SecurityConfig.java`, `application.yml` |
| `PC_SB_VMS_ConfigMap` | Kubernetes Configuration | `dev.yml`, `qa.yml`, `application-qa.yml` |
| `PC_OT_CONFIGSETUP-1` | DevOps Configuration | `VirtualService/qa.yml`, `ConfigSetup.properties` |
| `PC_AJ_ConfigSetup` | VMS Frontend Config | `qa.json` |

### CMS Repositories

| Repository | Description | Primary Files Modified |
|-----------|-------------|----------------------|
| `PC_AJ_CMS_UI` | Angular CMS Frontend | Component HTML/TS/SCSS files across `views/`, `service/`, `directives/`, `admin/page-editor`, `environments/` |
| `PC_SB_CMS_Microservice` | Spring Boot CMS Backend | Controllers, Services, `bootstrap.yml`, `JwtInterceptor.java` |
| `PC_SB_CMS_ConfigMap` | CMS Kubernetes Configuration | `dev.yml`, `qa.yml` |
| `PC_AJ_CMS_ConfigSetup` | CMS Frontend Config | `dev.json`, `environment.json` |

### Reference & Design Repositories

| Repository | Description | Usage |
|-----------|-------------|-------|
| `desktop/t5/PC_AJ_CMS_UI` | Legacy Reference Repo | Used as the UI Design Baseline for porting typography, layout gaps, and spacing parity to the new CMS architecture |
| `desktop/t1/Test_VMS_UI` | Initial Test Repo | Served as the migration source for the VMS frontend during Week 1 |

---

## Key Technical Decisions

### VMS

1. **Glassmorphism Design System** — Adopted as the core visual language across all modules for a premium, modern aesthetic
2. **External Static Labels** — Migrated from Material floating labels to static external labels for uniform visual consistency across all form states
3. **npm Overrides for Security** — Used `overrides` in `package.json` to force safe versions of transitive dependencies without waiting for upstream fixes
4. **Spring `@Cacheable`** — Adopted for Company/Warehouse/Zone repositories to eliminate N+1 query performance issues
5. **Multi-layered Clickjacking Defense** — Combined `X-Frame-Options`, `Content-Security-Policy: frame-ancestors`, and JavaScript frame-busting for defense-in-depth
6. **RBAC Harmonization** — Standardized role checks across all backend services to handle both numeric IDs (`"0"`, `"1"`, `"2"`) and string roles (`"super_admin"`, `"admin"`, `"zonal_coordinator"`)
7. **Kubernetes Secrets Migration** — Replaced all hardcoded credentials with environment variable references for secure deployment
8. **AES-256-CBC Encryption for PII** — Encrypted sensitive visitor fields (mobile, email, ID proof) at rest using externalized keys, with transparent decryption for email notifications
9. **Bootstrap.yml Migration** — Moved Spring configuration to `bootstrap.yml` to ensure ConfigMap values are injected before application context initialization in Kubernetes
10. **Active Directory Integration** — Integrated corporate AD search for auto-populating employee details during internal visitor request creation, reducing manual data entry and errors

### CMS

11. **CMS Block Alias Architecture** — Used `blockAliases` pattern in each component to map CMS backend field keys to frontend view model properties, enabling admin panel editability for all dynamic content
12. **Client-side Image Compression** — Implemented `ImageCompressionService` with Canvas API for on-the-fly downscaling and WebP conversion, eliminating need for backend image processing
13. **Lazy Blob Source Directive** — Created `LazyBlobSrcDirective` for efficient browser-level lazy loading with blob URL management and intersection observer integration
14. **S3 Bucket Strategy** — Migrated to `FLMBLOB_fed` bucket with CloudFront OAC architecture evaluation for optimized public media delivery
15. **Section Reordering Persistence** — Implemented CDK Drag-based section reordering with backend persistence to maintain admin-configured page layouts across sessions

---

## Challenges Faced

### VMS

- **RBAC Harmonization:** Reconciling inconsistent role representations (numeric vs. string) across the frontend, backend, and security contexts to ensure reliable authorization.
- **Infrastructure & Deployment Complexity:** Diagnosing 503 Service Unavailable errors in the Kubernetes environment caused by application name mismatches and missing ConfigMap references.
- **Legacy Security Debt:** Remediating a large volume of HP Fortify and SonarQube vulnerabilities, including insecure randomness and broad exception handling, while maintaining system stability.
- **Transitive Dependency Vulnerabilities:** Managing critical security risks (like the `tar` vulnerability) embedded deep within the dependency tree using advanced package management techniques like `npm overrides`.
- **UI Responsiveness & Consistency:** Porting a massive UI codebase to a modern, responsive glassmorphism design while ensuring consistent behavior across diverse screen sizes and input methods.
- **PII Encryption Pipeline:** Implementing end-to-end AES-256 encryption for sensitive visitor data while ensuring email notifications and search functionality remain operational through transparent decryption layers.
- **Bootstrap.yml Configuration Ordering:** Resolving Spring Boot configuration loading precedence issues when migrating from `application.yml` to `bootstrap.yml` for proper Kubernetes ConfigMap injection.
- **AD Integration Reliability:** Handling intermittent Active Directory lookup failures with graceful fallbacks, ensuring the visitor request creation flow remains functional even when the corporate directory is unavailable.
- **OTP Dual-Mode Transaction Sync:** Fixing the "both" OTP mode where SMS and email channels generated separate transaction IDs, causing verification failures when users entered OTP from one channel while the system validated against the other.

### CMS

- **Legacy Design Migration:** Porting content and styling from legacy `t5` codebase to the active CMS architecture while maintaining CMS editability and dynamic content rendering.
- **Block Alias Mapping Complexity:** Correctly mapping hierarchical CMS content blocks to component view models, especially for deeply nested sections like EarthTee highlights and Trendbook associations.
- **Image Quality vs. Performance Trade-off:** Balancing client-side image compression for faster load times against maintaining acceptable visual quality — required iterative tuning of compression parameters.
- **Section Reordering Persistence:** Ensuring drag-and-drop section reorder changes persist across page refreshes — debugging issues where specific sections (Top Stories, R Experience) reset to incorrect positions due to initialization order conflicts.
- **Angular Dependency Injection in Directives:** Resolving compilation errors caused by improper DI configuration in the `LazyBlobSrcDirective` when the `ChunkedDownloadService` was introduced.
- **QA vs Dev Environment Divergence:** Diagnosing production-only failures where images loaded in Dev but failed in QA due to APIM context path malformations, bucket mismatches, and config value inconsistencies across 4+ configuration repositories.
- **Strapi PoC "No-Change" Loop:** Resolving persistent visibility gaps in the Strapi prototype where admin edits were not reflecting in the frontend — caused by JSON shape mismatches, slug mapping inconsistencies, and cache invalidation gaps.
- **Docker Dependency Failures:** Triaging Docker build failures caused by `better-sqlite3` native compilation requirements; resolving Node engine version mismatches (`EBADENGINE` warnings) in CI/CD pipeline.
- **Upload Size Limitations:** Diagnosing and resolving multi-layer upload limits (Spring Boot multipart config, Nginx proxy buffers, Kubernetes ingress annotations) to support high-resolution media uploads.

---

## Key Learnings

### VMS

- **Enterprise Security Standards:** Mastery of multi-layered defense strategies, including CSP, JWT, clickjacking protection, and AES-256 data-at-rest encryption.
- **DevOps & Cloud Native Architecture:** Gained practical experience with Kubernetes ConfigMaps, Istio VirtualServices, GitOps workflows, and Spring Cloud bootstrap configuration.
- **Modern UI/UX Patterns:** Implementing high-fidelity designs using Angular 19, Sass `@use` syntax, advanced CSS techniques, and real-time input masking.
- **Code Sustainability:** Learning how to systematically reduce cognitive complexity and technical debt through SonarQube-driven refactoring.
- **Database Performance:** Experience with Spring Data JPA caching strategies and Redis integration to optimize application performance for high-volume data retrieval.
- **Enterprise Integration:** Practical experience integrating with corporate Active Directory, IAM token services, and multi-channel OTP delivery systems.

### CMS

- **CMS Architecture Patterns:** Understanding the full lifecycle of dynamic CMS content — from backend `ContentService` data fetching through `MediaResolverService` pipeline to frontend component rendering via `blockAliases` mapping.
- **AWS Media Infrastructure:** Hands-on experience with S3 bucket management, CloudFront CDN evaluation, and Origin Access Control (OAC) architecture for secure public media delivery.
- **Client-side Image Optimization:** Building production-grade image compression and lazy loading pipelines using Canvas API, WebP conversion, and Intersection Observer without backend dependencies.
- **Legacy Code Migration:** Developing systematic approaches to migrate existing designs and content from legacy codebases while preserving functionality and introducing CMS editability.
- **Admin Panel Engineering:** Building extensible page editor configurations with section templates, block registrations, and data population scripts for non-technical content management.
- **Headless CMS Evaluation:** Practical experience evaluating Strapi v4 as a headless CMS alternative, including content type design, REST API integration patterns, role-based access configuration, and deployment architecture planning on Azure.
- **Cross-Environment Debugging:** Developing rigorous diff-analysis and config reconciliation practices across 4+ repositories to diagnose QA-only failures that worked perfectly in Dev.
- **Blob Download Performance Engineering:** Designing bounded-concurrency download pipelines with request deduplication and text-first rendering strategies to optimize perceived load times for media-heavy pages.

---