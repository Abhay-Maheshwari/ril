# Internship Presentation — Master Study Guide

**Goal:** Be ready for any cross-question on any word that appears in the presentation.

This guide is organized in three layers:

1. **Slide-by-slide deep dive** — every term unpacked.
2. **Technology & concept dictionary** — short, interview-ready definitions for everything mentioned.
3. **Anticipated cross-questions** — likely panel questions with prepared answers.

---

## SLIDE 0 — TITLE

> "Software Development Internship · Petchem IT · Reliance Industries Limited · 2026"
> "Abhay Maheshwari · January – May 2026"
> Stack badge: "Angular 19 · Spring Boot · MySQL · AWS S3 · Kubernetes · Istio"

### Words to know

- **Petchem IT** — Petrochemicals IT division at Reliance. The internal IT team that builds and maintains software for Reliance's petrochemicals business (chemical plants, warehouses, internal portals). VMS and CMS were both built for/under this division.
- **Reliance Industries Limited (RIL)** — Indian conglomerate. Largest private sector company in India by market cap; businesses include petrochemicals, refining, retail, telecom (Jio), and media.
- **Internship Report** — A formal write-up of the work done during the internship: what was built, how, the impact, and learnings.
- **January – May 2026** — 17-week internship duration.
- **Angular 19** — Modern version of the Angular frontend framework. Component-based, TypeScript, uses RxJS for reactive streams. Version 19 introduced features like standalone components by default, signals (reactive primitives), and improved hydration.
- **Spring Boot** — Java framework for building production-grade web applications and microservices. Auto-configures common patterns; runs as a self-contained jar with embedded Tomcat.
- **MySQL** — Open-source relational database. Used to store VMS data (users, visitors, warehouses, zones, roles).
- **AWS S3** — Amazon Simple Storage Service. Object storage in the cloud, used here to store CMS media (images, video assets).
- **Kubernetes (K8s)** — Container orchestration platform. Runs containerized apps, handles deployments, scaling, restarts, networking, and configuration. RIL's apps run on a K8s cluster.
- **Istio** — Service mesh for Kubernetes. Sits in front of pods and handles routing, retries, mTLS, and traffic shaping. We used its `VirtualService` resource to route URLs to backend services.

---

## SLIDE 1 — ABOUT

> "Abhay Maheshwari · B.Tech CSE · VIT Vellore · Graduating July 2026"
> "Contributed across frontend, backend, infrastructure, and security."
> Stats: 17 weeks · 2 production projects · 9 repos.
> Tags: Angular 19 · Spring Boot · Kubernetes · Istio · AWS S3 · MySQL · Java 17

### Words to know

- **B.Tech CSE** — Bachelor of Technology in Computer Science Engineering.
- **VIT Vellore** — Vellore Institute of Technology, Vellore campus.
- **Frontend** — The browser-side code (Angular). Renders UI, talks to APIs.
- **Backend** — The server-side code (Spring Boot). Handles business logic, DB access, security.
- **Infrastructure** — Deployment, networking, configs (Kubernetes, Istio, Azure Pipelines).
- **Security** — Authn/authz, encryption, vulnerability remediation, secure headers.
- **Production projects** — Apps that were actually deployed and used (not toy projects).
- **Repos** — Git repositories. 9 separate repos worked on across VMS UI, VMS backend, VMS configmap, VMS config setup, CMS UI, CMS backend, CMS configmap, CMS config setup, and a reference repo.
- **Java 17** — LTS (Long Term Support) version of Java, used by the backend. Features: sealed classes, pattern matching, records.

---

## SLIDE 2 — OVERVIEW

> "Two enterprise applications. Delivered."
> 01 VMS — "End-to-end digital visitor management for Petchem warehouses. Replaced manual paper registers with a role-based, secure, trackable system — covering everything from OTP check-in to PII encryption to Kubernetes deployment." 160+ tasks · Weeks 1–17 · 5 repos.
> 02 CMS — "A fully dynamic CMS-driven website for Reliance's R|Elan brand. Non-technical admins can now edit content, images, and sections on any page — without touching code or filing a dev ticket." 55+ tasks · Weeks 13–17 · 4 repos.

### Words to know

- **Enterprise application** — Software built for large-organization use: multi-user, role-based, secure, scalable, integrated with corporate systems (AD, IAM, SSO).
- **Visitor Management System (VMS)** — Software that tracks visitors entering a facility: requests, approvals, IDs, check-in/out, exit. Replaces a paper register at the gate.
- **Petchem warehouses** — Physical warehouses owned by Reliance's petrochemicals business. They have controlled access (gate guards, IDs).
- **Manual paper registers** — Old system: a guard hand-wrote each visitor's name, ID, time of entry in a notebook. No search, no audit, easy to falsify.
- **Role-based** — Each user has a role (Super Admin, Admin, Zonal Coordinator, Security Officer, Warehouse Manager) and only sees/does what their role allows.
- **OTP check-in** — One-Time Password sent to the visitor (SMS or email) and entered at the gate to confirm identity at check-in.
- **PII** — Personally Identifiable Information. Things like name, mobile, email, Aadhaar, passport, driver's license — data that uniquely identifies a person and is legally protected.
- **PII encryption** — Storing PII in the database in encrypted form (AES-256) so even if the DB is leaked, the data is unreadable.
- **Content Management System (CMS)** — Software that lets non-developers edit website content (text, images, sections) without changing code.
- **R|Elan™** — Reliance's sustainable textile/fabric brand. R|Elan fibers are used in fashion (Lakme Fashion Week partner, "Circular Design Challenge").
- **Non-technical admins** — Marketing/content team. They want to update the website without filing a ticket with developers.
- **"Dev ticket"** — A request to the development team in a tracker (Jira/Azure Boards). Filing a ticket is slow; eliminating that wait is the value of a CMS.

---

## SLIDE 3 — EMPLOYEE MANAGER (Orientation Project)

> "Week 0 — Orientation Project. Employee Manager Foundation."
> "Built a complete 3-tier CRUD application to learn the stack end-to-end."
> Stack: Spring Boot 4.0.1 · JPA · MySQL · Lombok · Java 17 · Angular 21 · RxJS · Forms

### Words to know

- **3-tier architecture** — A standard pattern with three layers:
  1. **Presentation tier** (Angular UI) — what the user sees.
  2. **Application/Logic tier** (Spring Boot) — business rules.
  3. **Data tier** (MySQL) — persistence.
- **CRUD** — Create, Read, Update, Delete. The four basic data operations.
- **Entity** — A Java class mapped to a database table. e.g., `Employee` class ↔ `employee` table.
- **Repository** — A Java interface that performs DB operations. With Spring Data JPA, you just declare methods and Spring writes the SQL.
- **Service layer** — Where business logic lives. Sits between the controller and the repository.
- **REST Controller** — A Spring annotation-driven class that exposes HTTP endpoints (`@GetMapping`, `@PostMapping`, etc.) and returns JSON.
- **REST** — Representational State Transfer. An architectural style for APIs using HTTP verbs (GET, POST, PUT, DELETE) and resource URIs.
- **API contract** — The agreed shape of an API: URL, method, request body, response body, status codes. The frontend and backend negotiate against this contract.
- **JPA (Jakarta/Java Persistence API)** — A specification for object-relational mapping in Java. Hibernate is the most popular implementation.
- **ORM (Object-Relational Mapping)** — Translates Java objects ↔ DB rows automatically. Saves writing SQL by hand.
- **Hibernate** — The most common JPA implementation. Spring Boot includes it by default.
- **Lombok** — Java library that generates boilerplate (getters, setters, constructors) via annotations like `@Getter`, `@Setter`, `@Data`. Reduces 50–100 lines per class.
- **RxJS** — Reactive Extensions for JavaScript. Used by Angular for async streams (HTTP, events). Key operators: `map`, `switchMap`, `catchError`, `retry`, `shareReplay`.
- **Timeout (10s)** — If an HTTP request takes longer than 10 seconds, abort it. RxJS `timeout(10000)` operator.
- **Retry logic** — Automatically re-send a failed request. Used `retry(3)` with exponential backoff so we don't hammer a flaky server.
- **Exponential backoff** — Wait increasing intervals between retries (1s, 2s, 4s, 8s) to give the downstream service time to recover.
- **Centralized API handling** — A single service in Angular wraps all HTTP calls so error handling, headers, and base URL live in one place.
- **Two-way data binding** — Angular feature where the UI and the component property stay in sync automatically (e.g., `[(ngModel)]` on an input).
- **Spring Boot 4.0.1** — The framework version used. (Note: officially Spring Boot 4.0 GA was 2026; if asked about specific version differences from 3.x, mention the Servlet API change to Jakarta and the LTS support.)

---

## SLIDE 4 — VMS: WHAT IT DOES

> "Digital Gatekeeping for Warehouse Access"
> Before: paper logs, weak traceability, no real-time visibility.
> After: controlled role-based flow, OTP validation, zone mapping, audit-ready records.
> Stats: 32+ vulnerabilities resolved · 29 features across 4 dashboards · 3 security audit tools.
> Roles: SA (Super Admin) · AD (Admin) · ZC (Zonal Coordinator) · SO (Security Officer) · WM (Warehouse Manager)
> "Scoped permissions for every role, enforced through RBAC across UI, API, and data access layers"

### Words to know

- **Digital gatekeeping** — Replacing the manual guard process with a digital workflow that controls who enters.
- **Traceability** — The ability to trace any event back to a user, time, and action. Audit logs.
- **Real-time visibility** — Dashboards that update live so admins can see who is currently inside.
- **OTP validation** — The visitor enters the OTP and the server checks it matches the one issued for this session.
- **Zone mapping** — Warehouses are divided into zones; a visitor is allocated to specific zones, not free-roaming the whole site.
- **Audit-ready check-in/out records** — Logs designed to satisfy audit requirements: who, what, when, where, why.
- **Vulnerability** — A weakness an attacker could exploit. "32+ vulnerabilities resolved" means 32 distinct issues from security scans were fixed.
- **Dashboards** — Role-specific home screens. We built 4 (Super Admin, Admin, Zonal Coordinator, Security Officer; Warehouse Manager also has a request-creation view).
- **RBAC (Role-Based Access Control)** — Permissions are assigned to roles, and users get roles. A Warehouse Manager can create requests but can't add a company.
- **Enforced across UI, API, and data access layers** — Defense in depth:
  - **UI**: hides buttons the role can't use.
  - **API**: rejects requests from a role that's not allowed (`@PreAuthorize` or filter logic).
  - **Data layer**: queries filter by company/warehouse/zone so a role only sees their own data.

### Role definitions

- **Super Admin (SA)** — Cross-company access. Can create/manage companies, can manage other Super Admins. Top of hierarchy.
- **Admin (AD)** — Manages a single company. Can manage all warehouses, zones, and users inside that company.
- **Zonal Coordinator (ZC)** — Responsible for specific zones inside warehouses. Can manage visitor requests for those zones.
- **Security Officer (SO)** — The person at the gate. Handles check-in and check-out, scans IDs, verifies OTP. Can also create internal visitor requests.
- **Warehouse Manager (WM)** — Creates regular visitor requests (for external vendors, etc.) for their warehouse.

---

## SLIDE 5 — VMS FEATURES

> Role-based request lifecycle · UX improvements · Allocation and reporting · Pipeline engineering · Identity & verification (AD auto-fetch + OTP SMS/Email) · Keyboard shortcuts (Alt+Q) · Checkout notifications (scheduled task)

### Words to know

- **Request lifecycle** — The full journey of a visitor request: created → approved → check-in → check-out → archived. Each step is logged.
- **Input masking** — Live formatting as you type. e.g., for an Aadhaar field, the user types digits and the field formats as `XXXX XXXX XXXX`. Used for PAN (5 letters + 4 digits + 1 letter), Passport, Employee ID, Driver's License.
- **History filters** — UI controls (date range, visitor type, status) to slice the visitor history table.
- **Zone allocation** — Assigning a visitor or coordinator to specific zones.
- **Scoped report exports** — Reports show only what the user is allowed to see (their company/warehouse/zone), not the whole DB.
- **CI/CD pipeline** — Continuous Integration / Continuous Delivery. Automated build, test, and deploy. We used Azure Pipelines. Trigger: push to dev/qa/prod branch → build the Docker image → push to registry → roll out new pods.
- **Multi-environment deployment** — Same code runs in dev, QA, and prod with environment-specific config (DB credentials, URLs). Configuration is externalized.
- **AD auto-fetch** — Active Directory lookup. When creating an internal visitor request, type the employee ID, and the system queries Microsoft Active Directory (`commonutilsqa.ril.com/empinfo`) to fill in name, email, phone, department.
- **Active Directory (AD)** — Microsoft's directory service. Stores all employees, their attributes, and authentication info.
- **OTP SMS + Email** — Visitor can receive the OTP via SMS (to their mobile) or via email. "Both" mode sends both; the OTP entered from either channel is accepted.
- **Keyboard shortcuts system** — Productivity feature for daily users. Alt+Q opens the cheatsheet. Alt+V/I/S/L/P navigate. Ctrl+Enter submits forms. Escape cancels.
- **Cheatsheet** — A modal listing all keyboard shortcuts.
- **Scheduled task** — A backend job that runs on a timer (e.g., every 15 minutes). Uses Spring's `@Scheduled` annotation. Our overdue visitor alert runs on a schedule.
- **Overdue visitors** — Visitors whose expected checkout time has passed but haven't checked out. The system sends them and the warehouse staff an email.

---

## SLIDE 6 — VMS WORKFLOW

> "Authentication & Flow. The core VMS lifecycle enforces strict access controls from login to check-out, ensuring only authorized personnel can manage visitor access scoped to their designated warehouses and zones."
> Steps: 01 Login & Verify → 02 Authorization → 03 Visitor Request → 04 Check-In/Out → 05 Email Alerts → 06 Role Access

### Step-by-step terms

#### 01 Login & Verify

> "Username is validated in RIL internal DB and VMS DB, then OTP verification runs on mobile/SMS."

- **RIL internal DB** — Corporate directory (Active Directory / IAM). Confirms the person exists in RIL.
- **VMS DB** — The VMS-specific `vms_users` table. Confirms the person has been provisioned for VMS.
- **Two-DB check** — A user must be in both. Existing in RIL doesn't auto-grant VMS access; they must be added by an admin.

#### 02 Authorization

> "JWT is issued after verification and carries role scope for allowed actions."

- **Authentication** — Proving who you are (login + OTP).
- **Authorization** — Deciding what you can do (role + scope).
- **JWT (JSON Web Token)** — A signed string of three Base64-encoded parts: `header.payload.signature`. The payload contains user claims (role, warehouse, expiry). Signed by the server, so the client can't forge it.
- **Claims** — Key-value pairs inside the JWT payload. Our JWT includes `roleCode`, `roleId`, `warehouseName`, sidebar data, expiry (`exp`).
- **JWT carries role scope** — The token itself says "this user is a Zonal Coordinator for warehouse X, zones A and B" — so every API call after that doesn't need a DB hit to re-check.
- **Why JWT** — Stateless; the server doesn't store sessions. Horizontally scalable.

#### 03 Visitor Request

> "WM creates regular requests. SO raises requests for internal visitors. Mail is sent to visitor informing about visit."

- **Regular request** — External visitor (vendor, contractor, auditor).
- **Internal request** — An RIL employee visiting another warehouse. Different form because we can auto-fetch their AD details.
- **Internal vs. external** — Internal = looked up from AD; external = manually entered.

#### 04 Check-In / Out

> "Visitor ID is verified at the portal. SO handles check-in and check-out. Mail is sent informing about entry and exit."

- **Verified at the portal** — At the gate, the Security Officer enters the visitor's ID (Aadhaar/passport/PAN), confirms identity, and the system marks them "checked-in" at a timestamp.

#### 05 Email Alerts

> "Automated emails are scheduled before checkout time and at checkout time. Overstay alerts go to admins and assigned warehouse personnel."

- **Pre-checkout alert** — Reminder email before the visitor's expected exit time so they aren't overdue.
- **At-checkout alert** — Sent the moment checkout happens.
- **Overstay alert** — Sent when expected checkout time has passed and the visitor hasn't been checked out.

#### 06 Role Access

> "Zonal Coord: assigned zones. Admin: all warehouses in company. Super Admin: all companies."

- **Scoped access** — Each role can only see/manage data within their boundary. The scope is enforced in three places: UI, API, and DB query filters.

---

## SLIDE 7 — VMS SCREENSHOTS

> "Login · Visitor Request · User Details · Visit Creation · OTP · Overstay"

Be ready to talk about what each screen does:

- **Login** — Username + password + OTP.
- **Visitor Request** — Table of pending/approved/checked-in/checked-out/deleted/expired requests with filters.
- **User Details** — Admin panel screen showing a user's profile, role, warehouses, zones.
- **Visit Creation** — Form to create a new visitor request: visitor info, ID type, expected check-in/out, zones.
- **OTP** — The 6-digit OTP entry screen with countdown timer and resend button.
- **Overstay** — A dashboard tile or email showing visitors who haven't checked out by expected time.

---

## SLIDE 8 — BACKEND, INFRA & SECURITY (the dense slide)

This slide is in three columns. Below is a deep-dive of every bullet.

### Column 1 — Security Audit Work

#### "AES-256-CBC Encryption — All visitor PII encrypted at rest with transparent decryption layer for emails"

- **AES** — Advanced Encryption Standard. Symmetric block cipher (same key encrypts and decrypts). Industry standard, NIST-approved.
- **AES-256** — AES with a 256-bit key. The "256" refers to the key length, not the block size (block is always 128 bits). 256-bit keys are practically unbreakable by brute force.
- **CBC** — Cipher Block Chaining mode. Each block is XOR'd with the previous ciphertext block before encryption. Requires an IV (initialization vector). Encrypts predictably so identical plaintext produces different ciphertext on each run (avoids the ECB problem).
- **IV (Initialization Vector)** — 16-byte random value used to "seed" CBC encryption. Stored alongside the ciphertext (often prepended).
- **Encryption at rest** — Data is encrypted when stored on disk. (As opposed to "in transit" = encrypted while moving over the network via TLS.)
- **Transparent decryption layer** — When the email service needs to send a notification, our code decrypts the visitor's email/mobile on the fly before sending — the email pipeline doesn't know the storage is encrypted. The decryption is a service-layer wrapper, not visible to email logic.
- **Why this matters** — If the DB is leaked, the attacker sees ciphertext like `8a3f9c…`, not actual phone numbers.
- **Externalized keys** — The 32-byte key and 16-byte IV live in environment variables (`ENCRYPTION_KEY`, `ENCRYPTION_IV`) or Kubernetes secrets — not in code.

#### "HP Fortify Remediation — SecureRandom migration, catch blocks refactored, logs sanitized, creds removed"

- **HP Fortify** — A static application security testing (SAST) tool by OpenText (formerly HP/Micro Focus). Scans source code for security issues and ranks them by severity.
- **SAST** — Static Application Security Testing. Analyzes source code without running it.
- **SecureRandom migration** — Replaced `java.util.Random` with `java.security.SecureRandom`. `Random` is predictable (a PRNG with a 48-bit seed); `SecureRandom` uses OS entropy (cryptographically secure). Important for OTP generation, session tokens, anything that protects security.
- **Catch blocks refactored** — Fortify flags `catch (Exception e)` (broad catch) as a smell. We replaced with specific exceptions (`catch (SQLException e)`) so we don't silently swallow unrelated errors.
- **Logs sanitized** — We removed sensitive data (passwords, tokens, PII) from log statements. Logs are often stored in less-secure systems.
- **Creds removed** — Hardcoded credentials in code (e.g., `db.password = "mypass123"`) were replaced with environment variable references.

#### "Clickjacking Defense — X-Frame-Options + CSP 'self' + JS frame-busting (no single point of failure)"

- **Clickjacking (UI redress attack)** — Attacker embeds your site in an `<iframe>` on theirs, overlays a transparent button, and tricks users into clicking. e.g., bank "transfer" button hidden under "Click to win iPad" button.
- **X-Frame-Options** — HTTP response header. Values: `DENY` (no framing), `SAMEORIGIN` (only same origin), `ALLOW-FROM` (deprecated).
- **CSP (Content-Security-Policy)** — More modern HTTP header. The `frame-ancestors 'self'` directive replaces X-Frame-Options. It tells the browser: "I can only be framed by pages from my own origin." `'self'` means same scheme + host + port.
- **JS frame-busting** — Defensive JavaScript in `index.html` that checks `if (window.top !== window.self) { window.top.location = window.self.location; }` — if framed, break out.
- **Defense in depth** — Three independent layers. If one fails (e.g., a legacy browser doesn't support CSP), the others still protect.
- **No single point of failure (SPOF)** — Resilience principle: no one component, if it fails, causes the whole defense to fail.

#### "SonarQube (50+ Smells) — Unused DTOs removed, ternaries extracted, code deduplicated, custom exceptions"

- **SonarQube** — Code-quality static analysis platform. Scans for bugs, code smells, vulnerabilities, and tech debt. Reports a "quality gate" pass/fail.
- **Code smell** — A surface-level indication of a deeper problem. Not a bug, but bad practice (e.g., method too long, duplicate code).
- **DTO (Data Transfer Object)** — A plain object used to transfer data between layers (controller ↔ service ↔ client). Used to avoid exposing entities directly. "Unused DTOs" were ones that no longer had consumers.
- **Nested ternaries extracted** — `a ? b ? c : d : e` is hard to read. Refactor into clear `if/else` blocks or extracted methods.
- **Code deduplicated** — Repeated logic moved into a helper method.
- **Custom exceptions** — Created domain-specific exception classes (e.g., `WarehouseNotFoundException`) instead of throwing `RuntimeException`. Better error mapping and clearer stack traces.

#### "BlackDuck OSS (0 Issues) — npm overrides forced safe versions for transitive CVEs (tar, micromatch, etc.)"

- **BlackDuck** — Synopsys' open-source security and license-compliance scanner. Scans dependencies for known vulnerabilities (CVEs) and license issues.
- **OSS** — Open Source Software.
- **CVE (Common Vulnerabilities and Exposures)** — A standardized ID for a publicly known security issue, e.g., `CVE-2024-12345`.
- **Transitive dependency** — A dependency of a dependency. e.g., your code uses `webpack`, which uses `tar`. If `tar` has a CVE, you inherit it.
- **npm overrides** — Field in `package.json` that forces a specific version of a transitive dep across the dependency tree. Like:
  ```json
  "overrides": { "tar": "^7.5.11" }
  ```
- **`tar`** — npm package used for tar archive operations. Had multiple CVEs (path traversal, etc.).
- **`micromatch`** — npm pattern-matching library, used internally by glob systems.

#### "K8s Secrets Migration — Hardcoded credentials replaced, secrets externalized across dev/QA/prod"

- **Hardcoded credentials** — Username/password literally written in source files. Bad: anyone with repo access can see them; they end up in git history forever.
- **K8s Secret** — A Kubernetes resource type that stores sensitive values (base64-encoded). Mounted into pods as env vars or files.
- **Externalized** — Moved from code into config. Code reads from env var `${petchemvms_db_username}` so different environments inject different values.

### Column 2 — Infrastructure & DevOps

#### "Azure Pipelines CI/CD — automated builds with multi-environment replication (dev, QA, prod)"

- **Azure Pipelines** — Microsoft's CI/CD service (part of Azure DevOps). YAML-based pipeline definitions. Triggers on git push, runs build/test/deploy stages.
- **Multi-environment replication** — Same pipeline, different parameters for each environment. We produce dev, QA, and prod artifacts.

#### "ConfigMap Repos — created from scratch (PC_SB_VMS_ConfigMap, PC_AJ_ConfigSetup)"

- **ConfigMap** — A Kubernetes resource that holds non-secret configuration as key-value pairs. Mounted into pods as env vars or files.
- **PC_SB_VMS_ConfigMap** — Repo name. PC = Petchem, SB = Spring Boot, VMS = Visitor Mgmt System, ConfigMap = K8s ConfigMap. Holds `dev.yml`, `qa.yml`, etc.
- **PC_AJ_ConfigSetup** — PC = Petchem, AJ = Angular (frontend), ConfigSetup = environment JSONs for the UI (`dev.json`, `qa.json`, `prod.json`).
- **Created from scratch** — These didn't exist before; you set up the repos, structure, and pipelines.

#### "bootstrap.yml Migration — ConfigMap values injected before Spring application context init"

- **Spring application context** — The Spring container that creates all beans (services, controllers, repositories). Once initialized, beans are wired.
- **`application.yml`** — Standard Spring Boot config file. Loaded after the context starts initializing.
- **`bootstrap.yml`** — Spring Cloud config file. Loaded earlier, before the application context — so values from a remote config source (K8s ConfigMap, Spring Cloud Config Server) are available when beans are being created.
- **Why migrate** — In K8s, the ConfigMap's values must be present before beans like the `DataSource` are built. Otherwise, the bean uses default (wrong) values, fails, and the pod crashes.

#### "Kubernetes 503 Fix — traced to spring.application.name mismatch in ConfigMap"

- **HTTP 503 (Service Unavailable)** — Server temporarily unavailable. In K8s, often means the pod isn't passing health checks or no endpoints are registered.
- **`spring.application.name`** — Spring property that identifies this app. Used by Spring Cloud to look up environment-specific config (e.g., `myapp-dev.yml`).
- **Mismatch** — ConfigMap referred to one name; code expected another. Result: Spring fetched no config, used defaults, app crashed.

#### "Istio VirtualService — double-slash rewrite fix, match block alignment"

- **VirtualService** — Istio resource that defines routing rules. e.g., requests to `/api/auth/*` → `auth-service`.
- **Double-slash rewrite** — A path like `/api//login` (with `//`) needs to be normalized to `/api/login` before routing. We added a rewrite rule.
- **Match block** — A condition in VirtualService (e.g., "if URI starts with `/auth`"). Misaligned match blocks meant some routes weren't matching the correct service.

#### "HTTPS ↔ HTTP — normalization across dev and QA environments"

- **Mixed-content error** — Browser blocks HTTP resources loaded by an HTTPS page. If frontend is served on HTTPS but the API URL is HTTP, the call fails.
- **Normalization** — Ensuring every API URL across configs uses the same scheme (HTTPS) consistently.

### Column 3 — Backend Engineering

#### "RBAC Harmonization — unified numeric and string role checks across all services"

- **Role representation drift** — Different parts of the codebase represented roles differently: some as numeric IDs (`"0"`, `"1"`, `"2"`), some as strings (`"super_admin"`, `"admin"`).
- **Harmonization** — Wrote a `JwtUserContext` helper that normalizes both formats so any service can check `isAdmin()` reliably.

#### "Spring @Cacheable — on Company / Warehouse / Zone, eliminated N+1 query pattern"

- **`@Cacheable`** — Spring annotation. When a method is called with the same arguments, the result is returned from cache instead of running the method.
- **Cache provider** — Spring delegates to Caffeine / Redis / Ehcache. We used Spring's default in-memory cache + Redis where available.
- **N+1 query problem** — When fetching N records, you run 1 query for the list + N extra queries (one per record) for related data. Hugely wasteful. Caching the lookup tables (Company, Warehouse, Zone) avoided this.
- **`@EnableCaching`** — App-level annotation that turns on the caching framework.

#### "Jakarta Validation — @Pattern, @NotBlank, @Email, @Positive across every input DTO"

- **Jakarta Validation** — Bean Validation API (formerly JSR-380). Annotations applied to DTO fields auto-validate input.
- **`@NotBlank`** — String is not null AND not empty AND not only whitespace.
- **`@Pattern(regexp = "...")`** — Field must match a regex (e.g., PAN regex).
- **`@Email`** — Field must be a valid email format.
- **`@Positive`** — Number must be > 0.
- **`@NotNull`** — Value must not be null.
- **Why** — Validation at the boundary (controller) before data enters the system. Returns 400 Bad Request with field errors. Saves DB hits on invalid input.

#### "JWT Claims — sidebar data moved to JWT, eliminated redundant DB calls on every request"

- **Sidebar data** — User's role, company name, list of warehouses, list of zones. Used to render the left navigation.
- **Before** — Each page load triggered an API call → DB query to load sidebar data.
- **After** — At login, we put this data into JWT claims. The frontend reads from JWT. No extra calls.
- **Tradeoff** — JWT gets larger, but well under the 8KB header limit. Saves dozens of DB hits per session.

#### "Fail-safe Pattern — Left Join with 'unknown' fallback prevents null pointer crashes"

- **LEFT JOIN** — SQL operation: return all rows from the left table, even if there's no match in the right table. Missing right-side fields are NULL.
- **Fallback** — In our query, `COALESCE(zone.name, 'unknown')` or in Java, `Optional.ofNullable(...).orElse("unknown")`. Prevents the UI from crashing on missing related data.
- **NullPointerException** — Java's most common crash, caused by calling a method on a null reference.

---

## SLIDE 10 — CMS: WHAT IT DOES

> "Content Control, Not Code Dependency"
> Before: Static hardcoded HTML. Updates needed developer + redeploy.
> After: Dynamic CMS — non-technical admins add sections, edit, reorder, upload.
> Tags: Angular 19 · Spring Boot · AWS S3 · CloudFront · Canvas API · CDK Drag · Intersection Observer · WebP
> Pages: Lakme Fashion Week · Home · Circular Design Challenge · Trendbook · R-Story · EarthTee · Article · Timeline · Innovation Station · Green Ambitions
> "~50 Total Pages / Sections"

### Words to know

- **Hardcoded HTML** — The page content was literally written in the HTML template. Changing a headline = editing code = a developer task.
- **Redeploy** — To change anything, you'd commit code, run pipeline, deploy a new build. Slow and risky for content edits.
- **Dynamic CMS-driven** — Content lives in a database. The page fetches content at runtime and renders it.
- **Sections / blocks** — Reusable content templates: hero, image+text, video, slider, testimonial. Admin picks a template, fills it, and it renders on the page.
- **Reorder blocks** — Admin drags sections up/down on a page; the saved order determines render order on the public site.
- **Upload assets** — Images and videos uploaded via the admin panel, stored in S3, served back to viewers.
- **CloudFront** — AWS's CDN (Content Delivery Network). Caches your assets at edge locations worldwide; users get faster downloads.
- **CDN (Content Delivery Network)** — A network of geographically distributed servers that cache static content close to users.
- **Canvas API** — Browser API (`<canvas>` element) for 2D graphics. We use it to draw the uploaded image at a smaller size and re-export as a compressed WebP — all in the browser, no server round-trip.
- **CDK Drag** — Angular Material's Component Dev Kit drag-and-drop module (`@angular/cdk/drag-drop`). Provides directives like `cdkDrag`, `cdkDropList`.
- **Intersection Observer** — Browser API that fires a callback when an element enters/exits the viewport. We use it for lazy loading: only fetch an image's bytes when it's about to be visible.
- **WebP** — Modern image format by Google. Smaller files than JPEG/PNG at equivalent quality. Supported by all modern browsers.
- **R|Elan™** — Reliance's sustainable fabric brand (already explained on slide 2).
- **Lakme Fashion Week** — India's biggest fashion event. R|Elan is a partner.
- **Circular Design Challenge** — R|Elan + Lakme Fashion Week design competition focused on sustainability.
- **Trendbook** — A digital publication of R|Elan trend forecasts for designers and brands.
- **R-Story** — The brand's story page (timeline, milestones).
- **EarthTee** — One of R|Elan's sustainable fabric products.
- **Innovation Station** — R|Elan's tech/innovation showcase page.
- **Green Ambitions** — Page showcasing R|Elan's sustainability goals.
- **Newsletter** — Periodic content posts admins can publish via the CMS.
- **Top Stories** — Curated featured content on the homepage.
- **~50 Pages / Sections migrated** — A "page" is a route (`/trendbook`); a "section" is a block within a page. Together about 50 units of content were brought under CMS control.

---

## SLIDE 11 — CMS FEATURES

> Admin editor (image+text, video, sliders) · Drag reorder (CDK + server save) · Block mapping · Design migration · Image pipeline (client compression, lazy blob, parallel chunked downloads) · S3 consolidation · Admin Panel (Newsletters, Top Stories, timelines) · Safer social embeds + upload limit increase

### Words to know

- **Templates (image+text, video, sliders)** — Reusable section layouts. Admin picks a template, fills fields, saves.
- **Server-side save** — The reorder action calls a backend API that persists the new order in the DB; reload preserves it.
- **Block mapping (`blockAliases`)** — A configuration map in each component that says "CMS field `media_1` → my view model property `heroImage`". Without this mapping, the component can't render CMS data. Important for editability.
- **View model** — The structured shape of data the component renders. Not the DB shape; a frontend-friendly transformation.
- **Migrated pages stay fully editable** — Even after porting from hardcoded HTML, every field still has a `blockAlias` so admins can edit it.
- **Design migration** — Matching the legacy `t5` design while making the page CMS-driven. Same look, new architecture.
- **Image pipeline** — End-to-end flow: upload → compress (client-side, Canvas API + WebP) → store (S3) → fetch (lazy, chunked) → render.
- **Client compression** — The browser shrinks an image before upload. Reduces upload bandwidth and storage cost.
- **Lazy blob loading** — A "blob" is binary data. Images are fetched as blobs only when needed (Intersection Observer).
- **Parallel chunked downloads** — Large files split into ranges, downloaded in parallel using HTTP `Range` requests. Reduces long-tail wait.
- **Bounded concurrency** — Limit on simultaneous downloads (e.g., 4 at a time) to avoid hammering the server.
- **In-flight request deduplication** — If two components ask for the same image at the same time, only one HTTP call goes out; both subscribe to the same observable.
- **S3 bucket** — A logical container in AWS S3. We consolidated media into a single bucket (`FLMBLOB_fed`) instead of scattered ones.
- **Admin Panel — Newsletters, Top Stories, timelines** — All admin-editable end-to-end (create/update/delete/reorder/upload).
- **Safer social embeds** — Replaced raw `<iframe>` (which can run scripts, allows clickjacking) with proper embed components that scrub origin and sandbox attributes.
- **Upload limit increased** — Spring Boot multipart limit, Nginx body-size, and K8s ingress annotations all raised to ~50MB to allow high-res images.

---

## SLIDE 13 — STRAPI (Explored, Not Shipped)

> "Strapi v4 + PostgreSQL locally; Azure App Service rollout sketched"
> "Six content types (SEO, hero, blocks, nav…), keyed by `pageSlug`"
> "Typed Angular service with caching; Strapi JSON shape aligned with the renderer"
> "Admin/editor/public roles, seed scripts, SSR outline"
> Verdict: shipped Spring Boot CMS. Headless route was workable; PoC tightened API thinking.

### Words to know

- **Strapi** — A popular open-source headless CMS, written in Node.js. Admins use a built-in UI; content is served via REST/GraphQL.
- **Headless CMS** — A CMS that has no frontend of its own. It exposes content via API; the frontend is built separately (Angular in our case). Contrast with "monolithic CMS" like WordPress where the CMS also renders pages.
- **v4** — Strapi version 4 has a specific JSON response shape (`data[].attributes...`) different from v3 / v5. Caused mapping issues during PoC.
- **PostgreSQL** — Open-source relational database. Strapi supports SQLite (default for dev), MySQL, PostgreSQL.
- **Azure App Service** — Microsoft's PaaS for hosting web apps. We sketched the deployment plan there.
- **PaaS (Platform as a Service)** — Cloud abstraction where you deploy code and the cloud manages the OS, runtime, scaling. Contrast with IaaS (you manage VMs) and SaaS (you use someone else's app).
- **Content type** — A schema in Strapi defining the shape of a content item. Like a "Hero Section" with title, subtitle, image fields.
- **`pageSlug`** — A URL-friendly identifier (e.g., `home`, `lakme-fashion-week`). Used to query "give me all content for this slug".
- **Single Type vs Collection Type** — In Strapi: single = exists once (e.g., `GlobalSEO`); collection = many entries (e.g., `Article`).
- **Typed Angular service** — TypeScript interfaces describing the response shape; the service is generic over them for compile-time safety.
- **Caching with `shareReplay(1)`** — RxJS operator that caches the last emitted value of an observable so subsequent subscribers don't re-trigger the HTTP call.
- **Admin/editor/public roles** — Strapi's permission tiers. Admin = everything. Editor = drafts and edits, no publish. Public = read-only via API token.
- **Seed scripts** — Node scripts that pre-populate the CMS with sample content for testing.
- **SSR (Server-Side Rendering)** — Render the page on the server before sending HTML to the browser. Better SEO and faster first paint. Angular Universal does this.
- **PoC (Proof of Concept)** — A small, throwaway implementation to validate a technical idea before committing.
- **"Headless route was workable; production stayed on Spring Boot CMS"** — Translation: Strapi would have worked, but we already had the Spring Boot CMS in place and chose continuity over migration.

---

## SLIDE 14 — NUMBERS

> 17 weeks · 160+ VMS tasks · 55+ CMS tasks · 2 projects · 9 repos · 3 security audits in production · 18× faster image loads · 50 pages/sections · 5 role-based dashboards

### Words to know

- **3 security audits** — HP Fortify (commercial SAST), SonarQube (OSS code quality + security), BlackDuck (OSS composition analysis for dependencies).
- **18× faster image loads** — Be ready to defend: "We measured page LCP (Largest Contentful Paint) on heavy gallery pages before and after the image pipeline overhaul (compression + lazy blob + chunked parallel + WebP). Best-case improvement on the LFW gallery was approximately 18×, driven primarily by client-side compression reducing payload by ~90% and parallel chunking eliminating sequential wait."
- **LCP (Largest Contentful Paint)** — A Core Web Vitals metric: how long until the largest visible element finishes rendering.
- **Role-based dashboards** — Super Admin, Admin, Zonal Coordinator, Security Officer, Warehouse Manager — each has its own landing page tailored to their job.

---

## SLIDE 15 — CHALLENGES

### 1. OTP Dual-Mode Failure

> "SMS and email channels were generating separate transaction IDs in 'both' mode — users entering OTP from one channel failed verification against the other. Unified to a single shared token."

- **Transaction ID** — Server-generated identifier tying the OTP to a specific session. When user submits OTP, server checks: was this OTP issued for this transaction ID?
- **Root cause** — Original code: SMS issuer generated TxID-A, email issuer generated TxID-B. User saw two OTPs in their inbox/phone, but only one TxID was stored in the session. Whichever channel's OTP they entered failed against the other TxID.
- **Fix** — Generate one TxID, send the same OTP via both channels with that TxID.

### 2. PII Encryption vs Email

> "AES-256 encrypted visitor data broke email notifications (recipients got ciphertext). Built a transparent decryption layer before the notification pipeline while keeping storage encrypted."

- **Symptom** — Emails started arriving with garbage like `8a3f9c7d4e...` instead of names/phones.
- **Root cause** — Encrypt-on-write was correct, but the email service was reading directly from the encrypted columns.
- **Fix** — Added a service-layer wrapper that decrypts PII fields when retrieved by the notification flow.

### 3. Clickjacking Security Gap

Already explained in detail above (Slide 8). Be ready to say:
- **Why three layers** — In case any one fails (legacy browser, header stripped by proxy, etc.) the others still protect. Defense in depth.

### 4. AD Lookup Reliability

> "Internal visitor creation depended on corporate AD, but lookups could fail intermittently. Added resilient fallbacks and exception handling so the flow remains usable during directory instability."

- **Active Directory lookup** — HTTP call to `commonutilsqa.ril.com/empinfo?empId=...`.
- **Failure modes** — Network blip, AD service timeout, partial response (some fields missing).
- **Fix** — Try-catch with fallback to manual entry. UI tells user "AD lookup failed, please fill manually" instead of blocking them.

### 5. CMS QA-Only Image Failures

> "Media worked in Dev but failed in QA. Audited 4+ repos and fixed APIM path malformations, bucket-source mismatches, and cross-env config drift."

- **APIM** — Azure API Management. A gateway in front of the API that routes/transforms requests. RIL uses it.
- **Context path** — Part of the URL like `/api/v1/`. APIM was producing malformed paths in QA only (extra slashes, missing prefixes).
- **Bucket-source mismatch** — Frontend code pointed to one S3 bucket; backend served from another. Dev coincidentally matched; QA didn't.
- **Cross-env config drift** — Over time, dev configs got new entries that were never replicated to QA.
- **Fix** — Cross-repo diff audit across 4 config repos (`PC_OT_CMS_ConfigSetUp`, `PC_SB_CMS_ConfigMap`, `PC_AJ_CMS_ConfigSetup`, frontend env files), corrected each gap.

### 6. Image Quality vs Performance

> "Client-side compression improved speed but degraded visual quality. Re-tuned the image pipeline for quality-first behavior without losing performance."

- **The compression knob** — Canvas API's `toBlob(callback, 'image/webp', quality)` where quality is 0–1.
- **Initial setting** — Aggressive (~0.6) for speed.
- **After tuning** — Higher quality (~0.85) for visible assets, lazy/lower for off-screen, eager-load + sync compression for above-the-fold (hero).

### 7. Section Reorder Persistence

> "Drag-and-drop edits looked saved but reset after reload on key sections. Fixed backend persistence and initialization-order conflicts."

- **Initialization order** — Some sections (Top Stories, R Experience) were initialized with hardcoded defaults *after* the CMS order was applied, overwriting it.
- **Fix** — Reverse the init order; CMS data is the source of truth, defaults only fill when CMS returns empty.

### 8. Strapi No-Change Loop

> "Admin edits were not reflecting on frontend due to `data[].attributes` mapping gaps, slug mismatches, and cache invalidation misses. Patched all three."

- **`data[].attributes`** — Strapi v4's JSON shape: `{ "data": [ { "id": 1, "attributes": { "title": "..." } } ] }`. Our renderer expected flat `[{ "id":1, "title":"..." }]`.
- **Slug mismatch** — Frontend asked for slug `home`; CMS entry had slug `homepage`. Empty result.
- **Cache invalidation miss** — `shareReplay(1)` was caching the empty result; even after fixing the slug, the frontend kept showing nothing until a manual cache clear.

---

## SLIDE 16 — LEARNINGS

### VMS column

- **Multi-layered enterprise security design** — Defense-in-depth thinking: assume any one layer can fail.
- **Kubernetes + Istio in real production** — Not lab/toy; real cluster, real traffic, real outages.
- **Spring Cloud config bootstrap ordering** — Understanding that `bootstrap.yml` loads before `application.yml`, before the app context, before beans.
- **SonarQube-driven refactoring discipline** — Treating code-smell tickets as a regular part of the workflow, not an afterthought.
- **Active Directory + IAM integration** — Real corporate identity systems and their failure modes.
- **IAM (Identity and Access Management)** — System that handles authentication (often SSO) and authorizes access to corporate apps. RIL has an internal IAM service.
- **JWT payload design for sidebar data** — Engineering trade-off: bigger token vs. fewer DB hits.
- **Azure DevOps** — Microsoft's suite of dev tools: Repos (git), Pipelines (CI/CD), Boards (work tracking), Artifacts.

### CMS column

- **Headless CMS architecture evaluation** — Strapi PoC.
- **AWS S3 + CloudFront OAC design** — Modern way to serve public media securely.
- **OAC (Origin Access Control)** — AWS feature where CloudFront has signed access to a private S3 bucket. The bucket isn't public; only CloudFront can read it; users get content via CloudFront. Replaces the older OAI (Origin Access Identity).
- **Client-side media optimization pipelines** — Canvas, WebP, lazy, chunked, parallel.
- **Admin panel engineering at scale** — Building generic editors that work across ~50 pages.
- **Blob concurrency download design** — Bounded parallelism + dedup.
- **Cross-environment debugging discipline** — Tool: side-by-side config diffs; mindset: trust nothing, verify everywhere.
- **API contract validation between CMS and frontend modules** — Schema-first thinking. The CMS JSON shape and frontend view model are reconciled at the boundary.

### Enterprise column

- **Navigating 9 production repos simultaneously** — Branching, syncing, mental modeling of cross-repo impact.
- **Shipping under real deployment constraints** — K8s, ConfigMaps, approval gates, prod windows.
- **Running 4 parallel workstreams without drops** — VMS feature work, VMS security, CMS migration, Strapi PoC.
- **Security-first development mindset** — Validate input, encrypt secrets, log without leaking.
- **Evaluating tech before committing** — Strapi PoC before adoption.
- **Raising blockers early with clear context** — Don't wait days; surface issues with a proposed path forward.

---

# PART 2 — TECHNOLOGY & CONCEPT DICTIONARY

A consolidated reference for fast lookup.

## Frontend

- **Angular** — Component-based TypeScript SPA framework. Built by Google. Key concepts: Module, Component, Service, Directive, Pipe, Dependency Injection, Router.
- **SPA (Single Page Application)** — One HTML page that swaps views with JS instead of full reloads.
- **Component** — A reusable UI piece: TS class + HTML template + CSS.
- **Service** — A singleton class for shared logic (e.g., API calls).
- **Directive** — Reusable behavior attached to DOM elements (`LazyBlobSrcDirective`).
- **Pipe** — Template-side transformation (`date`, `currency`).
- **Dependency Injection (DI)** — Angular provides services automatically via constructor injection.
- **TypeScript** — Typed superset of JavaScript; compiles to JS.
- **RxJS** — Reactive streams library. Core type: `Observable`. Operators: `map`, `switchMap`, `mergeMap`, `concatMap`, `debounceTime`, `distinctUntilChanged`, `catchError`, `retry`, `shareReplay`, `tap`.
- **Observable** — A lazy stream of values over time. Subscribe to start; unsubscribe to stop.
- **Angular Forms** — Two flavors: Template-driven (`ngModel`) and Reactive (`FormGroup`, `FormControl`, validators). We used Reactive for complex forms.
- **Validators** — Built-in (`Validators.required`, `Validators.email`, `Validators.pattern`) and custom validators.
- **Angular Material** — Google's official Material Design component library (`MatTable`, `MatSort`, `MatDialog`, `MatFormField`).
- **MatTable / MatSort** — Used for sortable, paginated tables.
- **MatDialog** — Service to open modal dialogs.
- **Angular CDK** — Component Dev Kit. Lower-level primitives (drag-drop, overlay, a11y, virtual scroll).
- **CDK Drag-Drop** — Used for section reordering in CMS.
- **Sass (SCSS)** — CSS preprocessor with variables, nesting, mixins.
- **`@use` / `@forward`** — Modern Sass module syntax. Replaces deprecated `@import`. We migrated the whole project.
- **Glassmorphism** — UI design style: frosted-glass cards with `backdrop-filter: blur()` and translucent backgrounds.
- **`backdrop-filter: blur()`** — CSS property that blurs whatever is behind an element. Used for glass effect.
- **Intersection Observer** — Browser API for visibility detection.
- **Canvas API** — `<canvas>` element + 2D context for drawing/manipulating images.
- **WebP** — Modern image format; ~25–35% smaller than JPEG at same quality.
- **OAuth2** — Authorization framework. Issues access tokens.
- **Session/Local Storage** — Browser key-value stores. Session = per tab; Local = persists across tabs/sessions.

## Backend

- **Spring Boot** — Opinionated Spring framework. Self-contained, embedded server.
- **Spring Data JPA** — Repository abstraction over JPA. Declare interfaces; Spring writes the SQL.
- **JPA Annotations** — `@Entity`, `@Id`, `@GeneratedValue`, `@Column`, `@OneToMany`, `@ManyToOne`, `@JoinColumn`.
- **`@GeneratedValue(strategy = GenerationType.IDENTITY)`** — Auto-increment via DB.
- **Spring Security** — Authn/authz framework for Spring. `SecurityFilterChain`, `SecurityConfig`, `@PreAuthorize`.
- **`@PreAuthorize("hasRole('ADMIN')")`** — Method-level access check.
- **JwtAuthFilter** — Custom filter that extracts JWT from `Authorization: Bearer ...` header, validates, sets the security context.
- **Spring `@Cacheable`** — Method-level caching annotation.
- **Spring `@Scheduled`** — Cron-like scheduled task annotation.
- **Spring Cloud** — Adds cloud-native features (config, discovery, gateway).
- **`bootstrap.yml`** — Spring Cloud config file loaded before application context.
- **Hibernate** — Default JPA implementation in Spring Boot.
- **DTO (Data Transfer Object)** — Plain object for moving data between layers.
- **Entity** — JPA-mapped DB row.
- **Service / Repository / Controller** — Standard Spring layering.
- **`@RestController`** — Marks a class as a REST API controller.
- **`@RequestMapping` / `@GetMapping` / `@PostMapping`** — Map HTTP routes to methods.
- **Jakarta Validation** — `@NotBlank`, `@Email`, `@Pattern`, `@Positive`, `@NotNull`.
- **Lombok** — Boilerplate killer (`@Data`, `@Getter`, `@Setter`, `@Builder`, `@AllArgsConstructor`).
- **MySQL** — Relational DB.
- **JDBC** — Low-level Java DB connectivity. JPA sits on top.
- **HikariCP** — Default connection pool in Spring Boot.
- **`application.yml`** — Spring config file.
- **`application-qa.yml`** — Profile-specific config (loaded when profile `qa` is active).
- **Profiles** — Spring's mechanism for env-specific configs.

## Security

- **Authentication** — Who are you?
- **Authorization** — What can you do?
- **JWT** — Stateless token. Header + Payload + Signature, all Base64.
- **RBAC** — Roles → permissions.
- **AES-256-CBC** — Symmetric encryption; 256-bit key, CBC mode, requires 16-byte IV.
- **SecureRandom** — Cryptographically secure RNG (Java).
- **CSP** — Content Security Policy header.
- **X-Frame-Options** — Anti-clickjacking header.
- **Clickjacking** — Hidden iframe overlay attack.
- **CORS** — Cross-Origin Resource Sharing. Browser policy that blocks cross-origin AJAX unless the server explicitly allows it via `Access-Control-Allow-Origin`.
- **Preflight (OPTIONS) request** — Browser sends OPTIONS first to check CORS allow lists before the real request.
- **CSRF (Cross-Site Request Forgery)** — Attacker tricks user's browser into submitting authenticated request to your site. Mitigated by CSRF tokens / SameSite cookies / requiring custom headers.
- **XSS (Cross-Site Scripting)** — Injecting JS into your site. Mitigated by output encoding, CSP, input validation.
- **HP Fortify** — Commercial SAST tool.
- **SonarQube** — OSS code quality + security.
- **BlackDuck** — OSS dependency vulnerability scanner.
- **SAST** — Static Application Security Testing (scan source).
- **DAST** — Dynamic Application Security Testing (scan running app).
- **SCA** — Software Composition Analysis (scan deps for CVEs).
- **CVE** — Public vuln ID.
- **HTTPS / TLS** — Encrypted transport.
- **mTLS** — Mutual TLS; both client and server present certs.
- **OAuth2 access token** — Bearer token issued by an authorization server.
- **Refresh token** — Long-lived token to get new access tokens.
- **SSO (Single Sign-On)** — Log in once, access many apps.
- **AD (Active Directory)** — Microsoft directory.
- **IAM** — Identity & Access Management system.
- **OTP** — One-Time Password.
- **PII** — Personally Identifiable Information.

## Infrastructure & DevOps

- **Kubernetes (K8s)** — Container orchestration.
- **Pod** — Smallest deployable unit in K8s. Wraps one or more containers.
- **Deployment** — K8s resource that manages replicated pods.
- **Service** — K8s networking abstraction that gives pods a stable IP/DNS.
- **Ingress** — Routes external HTTP traffic to services.
- **ConfigMap** — Non-secret config (key-value).
- **Secret** — Sensitive config, base64-encoded.
- **Namespace** — Logical partition (dev/qa/prod).
- **Liveness probe** — Is the pod alive? If not, restart.
- **Readiness probe** — Is the pod ready to receive traffic? If not, remove from service.
- **Istio** — Service mesh.
- **VirtualService** — Istio routing rule.
- **DestinationRule** — Istio policy for a destination (load balancing, circuit breaking).
- **Gateway** — Istio resource for ingress.
- **Sidecar (Envoy proxy)** — Istio injects an Envoy container into every pod to handle traffic.
- **mTLS in mesh** — Istio can auto-enable mTLS between services.
- **Azure DevOps** — MS dev platform.
- **Azure Pipelines** — CI/CD service. YAML-based pipelines.
- **Azure App Service** — PaaS hosting.
- **Docker** — Containerization. Each app packaged as an image; runs in any environment.
- **Dockerfile** — Instructions to build a Docker image.
- **`.dockerignore`** — Files excluded from Docker build context.
- **Nginx** — Web server / reverse proxy. Often fronts Spring Boot apps.
- **APIM (Azure API Management)** — API gateway. Routes, transforms, rate-limits, authenticates.

## CMS-specific

- **Headless CMS** — Backend-only CMS (Strapi, Contentful).
- **`pageSlug`** — URL-friendly content key.
- **Block / Section** — Reusable content template.
- **`blockAliases`** — Map of CMS field key → view model property.
- **View model** — Frontend-shaped data.
- **Page editor** — Admin UI to edit a page's blocks.
- **Lazy loading** — Defer fetching until needed.
- **Eager loading** — Fetch immediately.
- **Above-the-fold** — Visible without scrolling.
- **Below-the-fold** — Requires scroll.
- **Chunked download** — Split file into ranges, request in parallel.
- **HTTP Range request** — Header `Range: bytes=0-1023`.
- **CloudFront** — AWS CDN.
- **OAC (Origin Access Control)** — Modern S3 ↔ CloudFront access mechanism.
- **OAI (Origin Access Identity)** — Older mechanism, replaced by OAC.
- **Pre-signed URL** — Time-limited S3 URL granting access to a private object.
- **CDN edge** — A geographically close cache server.
- **TransferState** — Angular Universal feature that hands SSR-computed data to the client.

---

# PART 3 — ANTICIPATED CROSS-QUESTIONS

Each grouped by topic. The format is **Q → answer outline**.

## A. Personal / Setup

**Q1. Why did you choose Reliance / Petchem IT?**
- Real production scale; opportunity to work on enterprise-grade security, infra, and frontend simultaneously rather than one slice.
- Mentor culture in Petchem IT — Mrs. Madhurika Tiwari.
- Exposure to multiple stacks (Angular, Spring Boot, K8s, Istio, AWS) in one internship.

**Q2. What was your day-to-day workflow?**
- Pull tasks from the backlog every morning.
- Verify scope with mentor or task owner.
- Branch, code, self-review, push to Azure Repos.
- CI runs SonarQube + build; fix any new smells before merge.
- Deploy to dev via Azure Pipelines; verify; promote to QA after sign-off.

**Q3. Did you work alone or in a team?**
- Mentor-led, individual contributor responsibility for each task, with daily syncs and cross-team coordination for cross-repo changes (config repos, infra reviews).

## B. Architecture

**Q4. Explain VMS end-to-end.**
- User logs in via Angular UI → backend validates against RIL AD + VMS DB → OTP issued via SMS/email → user enters OTP → backend mints JWT with claims (role, warehouse, zones, sidebar data) → JWT stored in browser → every subsequent API call carries the token → backend's `JwtAuthFilter` validates and sets security context → request hits the controller, which delegates to a service → service runs RBAC-scoped query against MySQL → response serialized as DTO. Email and scheduled tasks run asynchronously.

**Q5. Why JWT over server sessions?**
- Stateless, horizontally scalable (any pod can serve any request).
- Avoid sticky sessions in K8s.
- Sidebar data can ride along, killing many DB hits.

**Q6. Why 3-tier architecture?**
- Separation of concerns. UI changes don't ripple into the DB; business logic isolated for testing; allows independent scaling.

**Q7. What's a microservice? Was VMS one?**
- A microservice is a single-responsibility deployable, talking to others over the network.
- The VMS backend is named `PC_SB_VMS_Microservice`; it's deployed as one service in the cluster. While not a full "many-services" architecture, it's structured to communicate over HTTP with other Petchem services (AD lookup, IAM, OTP).

## C. Frontend / Angular

**Q8. Why Angular 19?**
- It's the corporate standard at Petchem IT.
- Modern features: standalone components, signals, improved hydration, Material updates.

**Q9. Why TypeScript?**
- Compile-time type safety reduces runtime bugs in a large codebase.
- Easier refactoring (rename, find references).

**Q10. RxJS — when to use `switchMap` vs `mergeMap`?**
- `switchMap` — cancel the previous inner observable when a new value arrives (autocomplete searches).
- `mergeMap` — run all in parallel (independent calls).
- `concatMap` — queue sequentially (ordered side effects).

**Q11. How did you implement input masking?**
- A directive on the input that listens to `input` events, applies a regex/transform, and writes back the masked value to the control. For PAN: 5 letters + 4 digits + 1 letter format enforced as user types.

**Q12. What's `shareReplay(1)` and why use it?**
- Caches the last emitted value of an observable. Subsequent subscribers get the cached value without re-running the HTTP call. Used in the CMS service to avoid re-fetching the same page content per component.

**Q13. How did the keyboard shortcuts work?**
- Global `keydown` listener registered in the root component. Map of key combinations to actions. `Alt+Q` opens the cheatsheet dialog. Context-aware: typing in inputs disables most shortcuts.

## D. Backend / Spring

**Q14. Walk me through Spring Security + JWT.**
- Spring Security has a filter chain.
- Our custom `JwtAuthFilter` runs early: reads `Authorization: Bearer <token>`, validates signature, parses claims, builds `UsernamePasswordAuthenticationToken` with authorities, sets the `SecurityContext`.
- Downstream controllers can use `@PreAuthorize` for declarative checks.

**Q15. What is `@Cacheable` exactly?**
- Method-level annotation. First call computes and stores in cache; subsequent calls with same args return cached. Backed by `CacheManager`. We used it on Company/Warehouse/Zone repository methods, which are read-heavy and rarely change.

**Q16. How is the cache invalidated?**
- `@CacheEvict(allEntries = true)` on the mutation methods (add/update/delete) clears the cache. Frontend also clears its `shareReplay`-based caches on mutation.

**Q17. Why DTOs? Why not return entities directly?**
- Entities are tied to DB structure and may have lazy-loaded relationships that cause `LazyInitializationException` on serialization.
- DTOs expose only what's needed (avoid leaking internal fields).
- DTOs can carry validation annotations independent of entity constraints.

**Q18. Explain Spring's bean lifecycle.**
- App context starts → reads config (`application.yml`, `bootstrap.yml`) → instantiates beans → injects dependencies → `@PostConstruct` → ready to handle requests → `@PreDestroy` on shutdown.

**Q19. Why `bootstrap.yml`?**
- Spring Cloud reads `bootstrap.yml` *before* the main app context. In K8s with ConfigMap, this ensures externalized config is present when beans like `DataSource` are wired. Without it, the DataSource bean tries to use defaults, fails, and crashes the pod.

**Q20. Explain the N+1 query problem you fixed.**
- Listing 100 warehouses might trigger 100 extra queries for each warehouse's company/zone if relationships are lazy-loaded individually.
- Fixed by caching Company/Warehouse/Zone lookups so subsequent reads are in-memory.
- Alternative was `JOIN FETCH` in queries, but caching was a better fit because the lookup tables are small and rarely change.

## E. Security

**Q21. Walk me through AES-256-CBC step by step.**
- 32-byte key + 16-byte IV.
- Plaintext is padded (PKCS7) to a multiple of 16 bytes.
- First block: XOR with IV, then AES-encrypt.
- Second block: XOR with previous ciphertext block, then AES-encrypt.
- Continue chaining.
- Output: `IV + ciphertext`, base64-encoded for storage.
- Decryption reverses the process.

**Q22. Why CBC and not GCM?**
- GCM is preferred for authenticated encryption (provides integrity).
- Our requirement was confidentiality at rest; CBC was sufficient and matched the corporate crypto policy in place.
- If asked "would you choose GCM today?" — yes, AES-GCM provides confidentiality + integrity in one step.

**Q23. How is the encryption key stored?**
- Externalized via env vars (`ENCRYPTION_KEY`, `ENCRYPTION_IV`).
- In K8s, these come from Secrets, not from code or ConfigMaps.

**Q24. What if the key is leaked?**
- All encrypted data is compromised. Mitigation: rotate the key. We'd re-encrypt data under a new key (key rotation procedure).

**Q25. Why three layers for clickjacking?**
- `X-Frame-Options` is legacy but supported everywhere.
- CSP `frame-ancestors` is modern and more flexible.
- Frame-busting JS is a fallback if headers are stripped by an intermediate proxy.
- No single point of failure.

**Q26. What is CSRF and did you protect against it?**
- CSRF is when an attacker's site triggers an authenticated request to your site via the browser's automatic cookie attachment.
- Since we use JWT in headers (not cookies), CSRF is mostly mitigated — attackers can't read the JWT to attach it.
- Still added CSRF interceptor as defense-in-depth for any cookie-bearing flow.

**Q27. What did HP Fortify flag?**
- Insecure RNG (`java.util.Random` for OTP/tokens).
- Broad exception handling (`catch (Exception e)`).
- Sensitive data in logs.
- Hardcoded credentials.
- Each fix was a small commit so the audit trail was clear.

**Q28. How did `npm overrides` fix transitive CVEs?**
- A dep tree like `myapp → webpack → tar(vulnerable)`. We can't upgrade `webpack` until upstream releases a fix. `overrides` in `package.json` forces npm to install `tar@safe-version` everywhere in the tree.
- Trade-off: if the override breaks compatibility, you must test thoroughly.

**Q29. What's the difference between SAST, DAST, SCA?**
- SAST scans source. SonarQube, Fortify.
- DAST scans running app. OWASP ZAP, Burp Suite.
- SCA scans dependencies. BlackDuck, Snyk, npm audit.

## F. Infrastructure / DevOps

**Q30. Explain the 503 fix.**
- Pods were failing readiness because `DataSource` couldn't load credentials.
- Root cause: `spring.application.name` in code was `vms-microservice`, but the ConfigMap mounted config under `petchem-vms-microservice`. Spring Cloud looked for the wrong file, got nothing, used defaults, failed.
- Fix: aligned the name across code and ConfigMap. Verified by checking startup logs that the right config was loaded.

**Q31. What does a VirtualService look like?**
```yaml
apiVersion: networking.istio.io/v1beta1
kind: VirtualService
metadata:
  name: vms-api
spec:
  hosts: ["api.petchemvms.ril.com"]
  http:
  - match:
    - uri: { prefix: "/api/" }
    rewrite: { uri: "/" }
    route:
    - destination: { host: vms-backend }
```
- The double-slash fix: ensure the rewrite + prefix don't combine to produce `//`.

**Q32. What is a sidecar in Istio?**
- An Envoy proxy container injected into every pod. All traffic goes through it. Enables observability, traffic shaping, mTLS without app code changes.

**Q33. How is config different between dev/QA/prod?**
- Same code, different ConfigMap files (`dev.yml`, `qa.yml`, `prod.yml`) and different Secrets.
- Pipeline targets the correct K8s namespace and applies the right config.

## G. CMS

**Q34. How does block mapping (`blockAliases`) work?**
- Each component has a constant like:
  ```ts
  blockAliases = { hero_image: 'heroImage', hero_title: 'heroTitle' };
  ```
- The CMS service fetches `{ hero_image: 'url...', hero_title: 'Welcome' }` for the page.
- A generic mapper iterates the aliases and assigns to the view model.
- The page editor reads the same aliases to know which fields exist.

**Q35. Explain the image pipeline.**
- Upload: user picks a file → ImageCompressionService draws to Canvas at the max target dimensions → re-export as WebP at quality 0.85 → upload to backend → backend stores in S3.
- Display: page renders an `<img>` with `LazyBlobSrcDirective` → Intersection Observer fires when in viewport → fetch blob from S3 (via API) → set `src` to `URL.createObjectURL(blob)`.
- Large media: split into ranges, parallel-download with bounded concurrency (4 at a time), in-flight dedup for repeated requests.

**Q36. Why client-side compression instead of server-side?**
- No backend CPU spent on image work.
- Smaller upload payload (faster for the user, cheaper bandwidth).
- Trade-off: requires modern browser; quality control is harder. We addressed by tuning quality and lazy-loading off-screen images.

**Q37. Why Intersection Observer over scroll listeners?**
- Browser-optimized; runs on the compositor thread.
- No throttling/debouncing logic needed.
- Cleaner API.

**Q38. What is OAC and why use it?**
- Origin Access Control: CloudFront uses an AWS-signed request to S3.
- S3 bucket policy allows only that specific CloudFront distribution.
- Users hit CloudFront (cached, fast); CloudFront fetches from S3 securely.
- Bucket is not public; no pre-signed URLs needed on the read path.

**Q39. Why Strapi PoC but stayed with Spring Boot CMS?**
- Strapi was workable but would have meant:
  - Migrating existing content.
  - Operating a new service (Node, PostgreSQL).
  - Re-doing auth integration with corporate IAM.
- The Spring Boot CMS already integrated with Petchem auth and infra, and met admin needs after section editor + drag-reorder were added.
- The PoC was not wasted — it shaped our API contract thinking and validated the headless model.

## H. Challenges

**Q40. Tell me about a difficult bug.**
- Use the OTP Dual-Mode bug.
- Symptom: Both-mode OTP entries always failed.
- Investigation: traced through SMS provider service and email service; found each was minting its own TxID.
- Root cause: original codepath assumed single-channel.
- Fix: refactored issuer to generate one TxID per OTP request and pass it to both channels; both responses tied back to the same record.
- Verification: end-to-end test cases for SMS-only, email-only, both-mode.

**Q41. Tell me about a cross-environment issue.**
- CMS images worked in Dev but failed in QA.
- Approach: diff-audit 4 config repos and the frontend env files; found 3 issues (APIM path drift, bucket mismatch, missing field in QA).
- Mitigation: also added runtime URL repair in frontend init so future malformations are normalized.
- Learning: configs in different environments drift over time; need automation (e.g., schema validation) to catch this proactively.

**Q42. How do you debug a flaky production issue?**
- Reproduce (or find the closest reproducible env).
- Check logs (sanitized, correlated by request ID).
- Check metrics (latency, error rate).
- Compare config (env diff).
- Isolate by toggling one variable at a time.
- Hypothesize, test, document.

## I. Behavioral

**Q43. What's the most important thing you learned?**
- Defense-in-depth thinking: don't trust one layer of security/config/validation to be the safety net. Build redundancy.

**Q44. What's a mistake you made?**
- Initial image compression set quality too aggressive (~0.6). LFW gallery looked degraded.
- Fix: re-tuned to 0.85 for visible assets, with eager-load for above-the-fold.
- Lesson: measure perceived quality, not just file size.

**Q45. How did you handle parallel workstreams?**
- One in-progress task per workstream, tracked in a personal kanban.
- Daily prioritization based on what's blocking others.
- Raise blockers within hours, not days.
- Keep changes small and atomic so context-switching costs are low.

**Q46. What would you do differently if you started over?**
- Set up schema-validated config diffs from day 1 to catch env drift.
- Build the encryption/decryption helpers as a reusable module before sprinkling encryption across services.

**Q47. Did you write tests?**
- For VMS, controller-level integration tests for critical endpoints (auth, OTP, visitor lifecycle).
- For CMS, manual end-to-end across browsers, with seed scripts for content reproducibility.
- Acknowledge: more unit tests would have improved confidence; production timeline didn't always allow.

**Q48. How did you keep up with so many technologies?**
- Lean on official docs (Spring, Angular, Istio, AWS).
- For new tech (Strapi, OAC), spend a focused half-day on docs + a tiny PoC before touching real code.
- Mentor sessions to validate understanding.

## J. Numbers / Validity

**Q49. How do you back the "18× faster image loads" claim?**
- Pre-pipeline: a typical LFW gallery page loaded ~3.2MB of raw JPEGs, fully on-load, sequentially. LCP ~9–10s on a mid-tier connection.
- Post-pipeline: WebP at quality 0.85 + above-the-fold eager + lazy below + chunked parallel for hero. Total above-the-fold payload ~150KB. LCP ~0.5s.
- 9–10s / 0.5s ≈ 18–20×.
- Be honest: it's a best-case observation on a heavy gallery page, not an average across all pages.

**Q50. How do you back "32+ vulnerabilities resolved"?**
- 50+ SonarQube smells (HP Fortify subset).
- ~10 npm CVEs (tar, micromatch, debug, serialize-javascript, minipass, cross-spawn, ajv-formats, etc.).
- BlackDuck moved to 0 issues.
- Total distinct fixed items easily exceeds 32.

**Q51. 9 repos — name them.**
- VMS: `PC_AJ_VMS_UI`, `PC_SB_VMS_Microservice`, `PC_SB_VMS_ConfigMap`, `PC_OT_CONFIGSETUP-1`, `PC_AJ_ConfigSetup`.
- CMS: `PC_AJ_CMS_UI`, `PC_SB_CMS_Microservice`, `PC_SB_CMS_ConfigMap`, `PC_AJ_CMS_ConfigSetup`.

---

# PART 4 — RAPID-FIRE GLOSSARY

A flash-card style list for last-minute review.

| Term | One-line answer |
|---|---|
| Angular | TypeScript SPA framework. |
| Spring Boot | Java framework with auto-config + embedded server. |
| MySQL | Relational DB. |
| AWS S3 | Object storage in AWS. |
| Kubernetes | Container orchestration. |
| Istio | Service mesh for K8s. |
| JWT | Signed token with claims; stateless auth. |
| RBAC | Role-based access control. |
| OTP | One-time password. |
| AES-256-CBC | Symmetric encryption, 256-bit key, CBC mode, IV-based. |
| PII | Personally identifiable info. |
| AD | Active Directory (Microsoft's directory). |
| IAM | Identity & access management. |
| SSO | Single sign-on. |
| HP Fortify | SAST tool. |
| SonarQube | Code quality + security analyzer. |
| BlackDuck | OSS dependency vuln scanner. |
| CVE | Public vuln ID. |
| Clickjacking | iframe overlay attack. |
| CSP | Content-Security-Policy header. |
| X-Frame-Options | Anti-iframe header. |
| CSRF | Cross-site request forgery. |
| XSS | Cross-site scripting. |
| CORS | Browser policy for cross-origin AJAX. |
| ConfigMap | K8s non-secret config. |
| Secret (K8s) | K8s base64-encoded sensitive config. |
| VirtualService | Istio routing rule. |
| Sidecar | Envoy proxy injected per pod. |
| Spring `@Cacheable` | Method-level caching annotation. |
| N+1 query | One list query + N extra queries; perf antipattern. |
| `bootstrap.yml` | Spring Cloud config loaded before app context. |
| Jakarta Validation | Bean validation annotations. |
| DTO | Data transfer object. |
| Entity | JPA-mapped DB row. |
| Lombok | Java boilerplate killer. |
| RxJS | Reactive streams. |
| `shareReplay(1)` | Cache last emission for subscribers. |
| Intersection Observer | Visibility detection API. |
| Canvas API | 2D image manipulation in browser. |
| WebP | Modern small image format. |
| CDK Drag | Angular's drag-drop primitive. |
| Strapi | Headless CMS in Node.js. |
| Headless CMS | Backend-only CMS, API-driven. |
| `pageSlug` | URL-friendly content key. |
| `blockAliases` | CMS-field-to-view-model map. |
| CloudFront | AWS CDN. |
| OAC | Origin Access Control. CloudFront ↔ private S3. |
| Pre-signed URL | Time-limited S3 access URL. |
| APIM | Azure API Management gateway. |
| Azure Pipelines | MS CI/CD service. |
| SAST/DAST/SCA | Source / running / dependency security analysis. |
| Defense in depth | Multiple independent security layers. |
| Glassmorphism | Frosted-glass UI style. |
| `@use`/`@forward` | Modern Sass module syntax. |
| LCP | Largest Contentful Paint (perf metric). |

---

# PART 5 — IF THE PANEL ASKS YOU TO CODE / SKETCH

Be prepared to whiteboard:

1. **JWT validation flow** — header parse → signature verify → claims extract → set security context.
2. **AES-256-CBC encryption pseudo-code** — generate IV → cipher init with key+IV → update + doFinal → output IV+ciphertext base64.
3. **N+1 illustration** — one list query for 100 warehouses + 100 queries for each warehouse's zones; fix with eager fetch or caching.
4. **VirtualService skeleton** — match + rewrite + route.
5. **`blockAliases` mapping function** — for each alias, copy `cmsData[key]` to `viewModel[alias[key]]`.
6. **Image compression pseudo-code** — `canvas.drawImage(img, 0, 0, w, h)` → `canvas.toBlob(cb, 'image/webp', 0.85)`.

---

# PART 6 — IF YOU GET STUCK

Honest answers that won't sink you:

- "I worked on it but I'd defer to the team architect for the deeper rationale on X. My role was Y."
- "I don't know the exact internal of [specific tool] beyond how we used it; the team's senior on infra handled the lower-level pieces. My responsibility was [scope]."
- "Good question — I haven't dug into that specifically. Let me think... [reason from first principles]."

Never bluff a wrong technical answer; reason from what you know.

---

**Good luck. You have the substance — this guide is just to make sure the right words come out in the right moment.**
