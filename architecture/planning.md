# MANDATORY DOCUMENTATION OUTPUT

The purpose of this planning phase is to produce a **complete implementation-ready documentation package** under:

```text
docs/
```

You MUST create, review, complete, and cross-check the following documentation structure:

```text
docs/
│
├── 01_PRODUCT_OVERVIEW.md
├── 02_REQUIREMENTS.md
├── 03_USER_ROLES_PERMISSIONS.md
├── 04_USER_STORIES.md
├── 05_APP_FLOWS.md
├── 06_NAVIGATION.md
├── 07_SCREEN_SPECIFICATIONS.md
├── 08_ARCHITECTURE.md
├── 09_DATABASE.md
├── 10_MODELS_MIGRATIONS.md
├── 11_BUSINESS_RULES.md
├── 12_STATUS_STATE_MACHINES.md
├── 13_API_SPECIFICATION.md
├── 14_VALIDATION_RULES.md
├── 15_ERROR_HANDLING.md
├── 16_NOTIFICATIONS.md
├── 17_BACKGROUND_JOBS.md
├── 18_INTEGRATIONS.md
├── 19_SECURITY.md
├── 20_AUDIT_LOGGING.md
├── 21_FILE_STORAGE.md
├── 22_REPORTS_ANALYTICS.md
├── 23_SETTINGS.md
├── 24_ENVIRONMENT_CONFIG.md
├── 25_DEPLOYMENT.md
├── 26_BACKUP_RECOVERY.md
├── 27_TESTING.md
├── 28_SEED_DATA.md
├── 29_DEFINITION_OF_DONE.md
├── 30_DEVELOPMENT_ROADMAP.md
└── 31_TASK_BREAKDOWN.md
```

These documents are **mandatory planning deliverables**.

Do not replace them with one large planning document.

Do not omit a document simply because the project is small.

If a subject genuinely does not apply, create the document and explicitly state:

```text
STATUS: NOT APPLICABLE

Reason:
[Explain why this area does not apply to this project.]
```

Do NOT invent functionality simply to populate a document.

---

# 01_PRODUCT_OVERVIEW.md

Define the product at the highest level.

Include:

- Product name
- Product vision
- Problem statement
- Proposed solution
- Target users
- User problems
- Business objectives
- Product objectives
- Core value proposition
- Primary capabilities
- Platforms
- Business model if known
- Stakeholders
- Assumptions
- Constraints
- MVP summary
- Phase 2 summary
- Future possibilities
- Out-of-scope functionality
- Success criteria
- Product terminology/glossary

A developer reading this document should understand **what is being built and why** before reading technical specifications.

---

# 02_REQUIREMENTS.md

Create the master requirements specification.

Separate requirements into:

## Functional Requirements

Use identifiers:

```text
FR-001
FR-002
FR-003
```

For each requirement document:

- Requirement
- Description
- Actor
- Preconditions
- Expected behavior
- Dependencies
- Priority
- MVP / Phase 2 / Future
- Related business rules

## Non-Functional Requirements

Use:

```text
NFR-001
NFR-002
```

Cover where applicable:

- Performance
- Security
- Availability
- Reliability
- Scalability
- Accessibility
- Responsive behavior
- Compatibility
- Logging
- Monitoring
- Backup
- Recovery
- Privacy
- Data retention
- Localization
- Time zones
- Concurrent usage

Clearly distinguish:

```text
CONFIRMED
INFERRED
RECOMMENDED
OPEN DECISION
```

Never silently convert assumptions into requirements.

---

# 03_USER_ROLES_PERMISSIONS.md

Identify every system actor and role.

For each role define:

- Purpose
- Responsibilities
- Accessible modules
- Read permissions
- Create permissions
- Update permissions
- Delete permissions
- Approval permissions
- Administrative permissions
- Financial permissions
- Export permissions
- Sensitive-data access

Create a permission matrix.

Consider:

- Ownership
- Record-level access
- Organisation-level access
- Self-service access
- Administrative override
- Least privilege
- Role inheritance if appropriate

---

# 04_USER_STORIES.md

Convert requirements into user-centered stories.

Use identifiers:

```text
US-001
US-002
US-003
```

Format:

```text
As a [user],
I want to [action],
so that [benefit].
```

For every important story include:

- User Story ID
- Actor
- Story
- Preconditions
- Acceptance criteria
- Business rules
- Validation
- Failure scenarios
- Permissions
- Dependencies
- Priority
- MVP/Phase
- Related requirements

Use acceptance criteria that can eventually be tested.

---

# 05_APP_FLOWS.md

Document all important end-to-end workflows.

Examples depend on the project.

Document flows such as:

- Registration
- Authentication
- Primary customer journey
- Creation workflows
- Purchase/booking/order workflows
- Approval workflows
- Administrative workflows
- Cancellation
- Refund
- Recovery
- Account management

Use clear flows such as:

```text
Start
↓
Action
↓
Validation
↓
Decision
├── Success → Continue
└── Failure → Recovery
↓
Completion
```

For every flow include:

- Trigger
- Actor
- Preconditions
- Main flow
- Alternative flows
- Failure flows
- Completion state
- Side effects
- Notifications
- Related screens
- Related APIs
- Related business rules

---

# 06_NAVIGATION.md

Define application information architecture.

Cover every relevant interface:

- Public application
- Customer application
- Mobile application
- Admin dashboard
- Staff portal
- Partner portal

Document:

- Main navigation
- Secondary navigation
- Menu hierarchy
- Route/page hierarchy
- Permission visibility
- Entry points
- Breadcrumb behavior if applicable
- Profile/account navigation
- Settings navigation
- Contextual actions

Navigation should represent the **user's mental model**, not simply database entities.

---

# 07_SCREEN_SPECIFICATIONS.md

Create specifications for every important screen.

Assign IDs:

```text
SCR-001
SCR-002
SCR-003
```

For each screen define:

- Screen name
- Purpose
- Users
- Entry conditions
- Information displayed
- Inputs
- Actions
- Validation
- Permissions
- Business rules
- Navigation destinations

Document UI states:

- Initial
- Loading
- Loaded
- Empty
- Error
- Validation error
- Permission denied
- Disabled
- Success

Document tables where relevant:

- Columns
- Filters
- Search
- Sorting
- Pagination
- Row actions
- Bulk actions

Document forms:

- Fields
- Types
- Required/optional
- Defaults
- Validation
- Conditional fields
- Help text where necessary

---

# 08_ARCHITECTURE.md

Define the high-level system architecture.

Include:

- Architecture overview
- System components
- Frontend architecture
- Backend architecture
- Database architecture
- API architecture
- Authentication architecture
- Authorization architecture
- File architecture
- Integration architecture
- Notification architecture
- Queue architecture
- Cache architecture where needed
- Scheduled processing
- Deployment architecture

Explain major architectural decisions.

Prefer the simplest architecture that correctly handles the requirements.

Do not introduce unnecessary microservices, queues, caches, event buses, search clusters, or other infrastructure without justification.

Include diagrams using Mermaid/text where useful.

---

# 09_DATABASE.md

Define the conceptual and logical database design.

Include:

- Entity overview
- ERD
- Relationships
- Ownership
- Cardinality
- Foreign-key strategy
- Referential integrity
- Unique constraints
- Index strategy
- Historical data
- Soft deletion
- Audit requirements
- Concurrency considerations

Analyze:

- Duplicate-record risks
- Orphan records
- Race conditions
- Incorrect cascading deletes
- Historical accuracy
- Data integrity
- Query performance

---

# 10_MODELS_MIGRATIONS.md

Specify every expected model/table without writing actual migration code.

For each model define:

```text
Model
Purpose
Table
Fields
Data Types
Required/Nullable
Defaults
Primary Key
Foreign Keys
Relationships
Indexes
Unique Constraints
Status Fields
Soft Deletes
Timestamps
Audit Requirements
Historical/Snapshot Fields
```

Also document expected migration order based on foreign-key dependencies.

Example:

```text
users
↓
organisations
↓
products
↓
orders
↓
order_items
```

The actual order must come from the project's domain.

---

# 11_BUSINESS_RULES.md

Create the authoritative business-rule catalogue.

Use:

```text
BR-001
BR-002
BR-003
```

For each rule:

- Rule
- Reason
- Applies to
- Preconditions
- Enforcement
- Exceptions
- Failure behavior
- Related requirements
- Related validation
- Related tests

Business rules must be explicit enough that developers do not have to guess.

---

# 12_STATUS_STATE_MACHINES.md

Identify every entity with a meaningful lifecycle.

For each define:

- Initial state
- Valid states
- Terminal states
- Valid transitions
- Invalid transitions
- Trigger
- Actor
- Preconditions
- Side effects
- Automatic transitions
- Time-based transitions

Example only:

```text
DRAFT
  ↓
PENDING
  ↓
APPROVED
  ↓
COMPLETED
```

Do not copy generic statuses into the project.

Determine the states from actual business requirements.

---

# 13_API_SPECIFICATION.md

Define the expected application API.

Group endpoints by domain/module.

For each endpoint document:

```text
API ID
Purpose
Method
Path
Authentication
Permission
Request
Validation
Response
Errors
Side Effects
Idempotency
Rate Limiting
```

Include:

- Authentication APIs
- CRUD APIs
- Workflow APIs
- Search APIs
- Reporting APIs
- Integration/webhook APIs

The API should model business operations rather than simply exposing database tables.

---

# 14_VALIDATION_RULES.md

Create the centralized validation specification.

For every important input define:

- Field
- Type
- Required/optional
- Minimum
- Maximum
- Format
- Allowed values
- Conditional requirements
- Uniqueness
- Cross-field validation
- Database-dependent validation
- Business-rule validation
- Error message expectation

Separate:

```text
Frontend convenience validation

from

Authoritative backend validation
```

Critical rules must never depend exclusively on frontend validation.

---

# 15_ERROR_HANDLING.md

Define the application's error strategy.

Cover:

- Validation errors
- Authentication errors
- Authorization errors
- Not found
- Conflict
- Duplicate submission
- Business-rule violation
- Rate limiting
- Integration failure
- Payment failure
- Network failure
- Database failure
- File failure
- Background-job failure
- Unexpected server errors

For each category define:

- Expected behavior
- User-facing message
- API response
- Logging
- Retry behavior
- Recovery behavior
- Alerting where appropriate

Do not expose sensitive technical details to end users.

---

# 16_NOTIFICATIONS.md

Create the notification catalogue.

For every notification define:

```text
NOT-001

Event
Recipient
Channel
Trigger
Required data
Template purpose
Priority
Retry
Failure behavior
Audit requirement
```

Possible channels:

- In-app
- Email
- SMS
- WhatsApp
- Push

Separate transactional and marketing notifications.

---

# 17_BACKGROUND_JOBS.md

Identify asynchronous work.

For each job define:

```text
JOB-001

Purpose
Trigger
Payload
Queue
Priority
Retries
Timeout
Idempotency
Failure behavior
Logging
Monitoring
```

Possible jobs include:

- Email
- Notifications
- File generation
- Imports
- Exports
- Image processing
- Integration synchronization
- AI processing
- Reports

Only introduce background jobs where appropriate.

---

# 18_INTEGRATIONS.md

Document every external dependency.

For each integration:

- Purpose
- Provider if selected
- Authentication
- Data sent
- Data received
- API operations
- Webhooks
- Verification
- Rate limits
- Timeout
- Retry
- Idempotency
- Failure handling
- Security
- Privacy
- Logging
- Sandbox/test requirements

Do not invent providers where the product owner has not selected one.

---

# 19_SECURITY.md

Perform a complete security design review.

Cover where applicable:

- Authentication
- Authorization
- Password security
- OTP
- Sessions
- Tokens
- Rate limiting
- Brute-force prevention
- CSRF
- XSS
- SQL injection
- IDOR
- Input validation
- File security
- API security
- Webhook security
- Payment security
- Secrets
- Encryption
- Data isolation
- Sensitive data
- Account recovery
- Admin security
- Auditability
- Abuse prevention

Identify threats specific to the project's domain.

---

# 20_AUDIT_LOGGING.md

Define what actions require permanent audit history.

For each event consider:

```text
Actor
Action
Entity
Entity ID
Old values
New values
Timestamp
Reason
IP
Device
Metadata
```

Define:

- Audited actions
- Who can view audit logs
- Search/filter requirements
- Retention
- Sensitive-data handling
- Immutability expectations

---

# 21_FILE_STORAGE.md

If files are involved, define:

- File categories
- Allowed formats
- Maximum size
- Storage
- Naming
- Directory/object organization
- Public/private status
- Authorization
- Upload validation
- Malware considerations
- Download
- Preview
- Deletion
- Retention
- Generated files
- Temporary files
- Backups

If the system does not use files, document why this is not applicable.

---

# 22_REPORTS_ANALYTICS.md

Define all reporting and analytics requirements.

For each report:

- Report ID
- Purpose
- Audience
- Data source
- Columns/metrics
- Calculation definitions
- Filters
- Grouping
- Sorting
- Date range
- Permissions
- Export options

Define dashboard KPIs precisely.

Never use ambiguous metrics without defining their calculation.

---

# 23_SETTINGS.md

Identify configurable business/system settings.

For each setting:

- Setting key
- Purpose
- Type
- Default
- Allowed values
- Who can change it
- Validation
- Effect
- Audit requirement
- Environment-specific or business-configurable

Do not turn values into settings unless they genuinely need runtime configuration.

---

# 24_ENVIRONMENT_CONFIG.md

Document required configuration categories.

Examples:

```text
Application
Database
Cache
Queue
Mail
Storage
Authentication
External APIs
Payment
Notifications
Logging
Monitoring
```

For each variable/configuration item define:

- Purpose
- Required/optional
- Example format without real secrets
- Development behavior
- Testing behavior
- Staging behavior
- Production behavior

Never place actual secrets in documentation.

---

# 25_DEPLOYMENT.md

Define the deployment strategy.

Cover:

- Environments
- Build process
- Deployment process
- Database migration strategy
- Static assets
- Queues
- Scheduled jobs
- File storage
- HTTPS
- Domain/DNS
- Environment variables
- Health checks
- Logging
- Monitoring
- Rollback
- Zero/minimal downtime where appropriate

Keep infrastructure proportional to expected project scale.

---

# 26_BACKUP_RECOVERY.md

Define:

- What is backed up
- Database backup
- File backup
- Frequency
- Retention
- Encryption
- Backup storage
- Restore process
- Restore testing
- Disaster scenarios
- Recovery Point Objective if appropriate
- Recovery Time Objective if appropriate

A backup strategy is incomplete unless restoration is also considered.

---

# 27_TESTING.md

Create the complete test strategy.

Map testing back to requirements and business rules.

Include:

- Unit tests
- Feature tests
- Integration tests
- API tests
- Validation tests
- Permission tests
- State-transition tests
- Database-constraint tests
- Concurrency tests
- Security tests
- File tests
- Notification tests
- Background-job tests
- Integration tests
- Failure-path tests
- End-to-end tests
- UAT

Every critical business rule and edge case should have a corresponding test expectation.

---

# 28_SEED_DATA.md

Define realistic seed/demo data.

Include:

- Roles
- Permissions
- Users
- Core entities
- Relationships
- Status variations
- Successful scenarios
- Failure scenarios
- Edge cases

Specify dependencies/order.

Do not write actual seed code yet.

The seed data should allow developers and testers to exercise the major application flows.

---

# 29_DEFINITION_OF_DONE.md

Define global completion requirements.

Every applicable feature should satisfy:

```text
□ Requirement implemented
□ Acceptance criteria passed
□ UI completed
□ Responsive behavior verified
□ Validation implemented
□ Authentication verified
□ Authorization verified
□ Business rules enforced
□ Database constraints implemented
□ Error handling completed
□ Loading states completed
□ Empty states completed
□ Security reviewed
□ Audit logging implemented where applicable
□ Notifications implemented where applicable
□ Background processing verified where applicable
□ Tests written
□ Edge cases tested
□ Demo data available
□ Documentation updated
```

Also create feature-specific Definition of Done requirements where necessary.

---

# 30_DEVELOPMENT_ROADMAP.md

Convert the completed architecture into a logical implementation sequence.

Determine phases from actual dependencies.

Possible structure:

```text
PHASE 1 — FOUNDATION
PHASE 2 — CORE DOMAIN
PHASE 3 — PRIMARY WORKFLOWS
PHASE 4 — ADMINISTRATION
PHASE 5 — INTEGRATIONS
PHASE 6 — REPORTING
PHASE 7 — HARDENING & RELEASE
```

Do not blindly use these phases.

For every phase define:

- Objective
- Dependencies
- Features
- Expected outcome
- Exit criteria

Implementation order should respect dependencies.

---

# 31_TASK_BREAKDOWN.md

This document must convert the entire specification into **small, independently implementable and testable development tasks**.

Use IDs:

```text
TASK-001
TASK-002
TASK-003
```

For every task define:

```text
Task ID

Title

Module

Purpose

Requirements Covered

User Stories Covered

Dependencies

Database Work

Backend Work

API Work

Frontend Work

Validation

Permissions

Business Rules

Error Handling

Notifications

Audit Requirements

Tests

Acceptance Criteria

Definition of Done
```

Tasks must be ordered by dependency.

For example:

```text
Foundation
↓
Authentication
↓
Roles & Permissions
↓
Core Parent Entities
↓
Dependent Entities
↓
Primary Workflows
↓
Integrations
↓
Reports
↓
Hardening
```

The actual order must come from the project's architecture.

Avoid tasks such as:

```text
TASK-001 Build the backend
TASK-002 Build the frontend
TASK-003 Build admin dashboard
```

These are too large.

Tasks should normally represent one coherent, independently testable implementation unit.

---

# CROSS-DOCUMENT TRACEABILITY

The 31 documents must NOT behave like independent documents.

They form one specification.

Maintain consistency across:

```text
PRODUCT OVERVIEW
        ↓
REQUIREMENTS
        ↓
USER STORIES
        ↓
APP FLOWS
        ↓
NAVIGATION
        ↓
SCREENS
        ↓
ARCHITECTURE
        ↓
DATABASE / MODELS
        ↓
BUSINESS RULES
        ↓
STATE MACHINES
        ↓
APIs
        ↓
VALIDATION
        ↓
ERROR HANDLING
        ↓
SECURITY
        ↓
TESTING
        ↓
ROADMAP
        ↓
TASK BREAKDOWN
```

For example:

If:

```text
FR-023
```

requires a user to cancel something:

There should be:

- Appropriate user story
- Flow
- Screen/action
- Permission
- Business rule
- State transition
- API operation
- Validation
- Error handling
- Audit requirement if necessary
- Tests
- Implementation task

No major requirement should disappear between planning and implementation.

---

# DOCUMENT GENERATION ORDER

Create/review the documentation in dependency order.

Use approximately:

```text
01 Product Overview
        ↓
02 Requirements
        ↓
03 Roles & Permissions
        ↓
04 User Stories
        ↓
05 App Flows
        ↓
06 Navigation
        ↓
07 Screen Specifications
        ↓
08 Architecture
        ↓
09 Database
        ↓
10 Models & Migrations
        ↓
11 Business Rules
        ↓
12 State Machines
        ↓
13 API
        ↓
14 Validation
        ↓
15 Error Handling
        ↓
16 Notifications
        ↓
17 Background Jobs
        ↓
18 Integrations
        ↓
19 Security
        ↓
20 Audit Logging
        ↓
21 File Storage
        ↓
22 Reports & Analytics
        ↓
23 Settings
        ↓
24 Environment Configuration
        ↓
25 Deployment
        ↓
26 Backup & Recovery
        ↓
27 Testing
        ↓
28 Seed Data
        ↓
29 Definition of Done
        ↓
30 Development Roadmap
        ↓
31 Task Breakdown
```

However, planning is iterative.

When a later document reveals a missing requirement, go back and update the earlier documents.

Do not leave contradictions simply because an earlier document has already been written.

---

# MANDATORY FINAL REVIEW

After producing all 31 documents, perform a final cross-document review.

Check for:

## Requirements

- Missing requirements
- Duplicate requirements
- Contradictory requirements
- Unclear requirements

## Product

- Missing workflows
- Missing actors
- Missing administrative functionality
- Missing failure paths

## Database

- Missing entities
- Incorrect relationships
- Missing foreign keys
- Missing unique constraints
- Missing indexes
- Race conditions
- Historical-data problems

## Architecture

- Unnecessary complexity
- Missing infrastructure
- Incorrect boundaries
- Scalability risks

## Security

- Missing authorization
- Data exposure
- Manipulation risks
- Abuse risks
- Missing rate limits
- Missing auditability

## UX

- Missing screens
- Dead-end flows
- Unnecessary steps
- Missing loading/error/empty states

## APIs

- Missing operations
- Incorrect permissions
- Missing validation
- Missing idempotency

## Testing

- Requirements without tests
- Business rules without tests
- State transitions without tests
- Edge cases without tests

## Tasks

- Requirements without implementation tasks
- Tasks with missing dependencies
- Tasks that are too large
- Incorrect implementation order

Correct the documentation before declaring planning complete.

---

# COMPLETENESS MATRIX

Before finishing, verify:

```text
01_PRODUCT_OVERVIEW.md             COMPLETE / INCOMPLETE
02_REQUIREMENTS.md                 COMPLETE / INCOMPLETE
03_USER_ROLES_PERMISSIONS.md       COMPLETE / INCOMPLETE
04_USER_STORIES.md                 COMPLETE / INCOMPLETE
05_APP_FLOWS.md                    COMPLETE / INCOMPLETE
06_NAVIGATION.md                   COMPLETE / INCOMPLETE
07_SCREEN_SPECIFICATIONS.md        COMPLETE / INCOMPLETE
08_ARCHITECTURE.md                 COMPLETE / INCOMPLETE
09_DATABASE.md                     COMPLETE / INCOMPLETE
10_MODELS_MIGRATIONS.md            COMPLETE / INCOMPLETE
11_BUSINESS_RULES.md               COMPLETE / INCOMPLETE
12_STATUS_STATE_MACHINES.md        COMPLETE / INCOMPLETE
13_API_SPECIFICATION.md            COMPLETE / INCOMPLETE
14_VALIDATION_RULES.md             COMPLETE / INCOMPLETE
15_ERROR_HANDLING.md               COMPLETE / INCOMPLETE
16_NOTIFICATIONS.md                COMPLETE / INCOMPLETE
17_BACKGROUND_JOBS.md              COMPLETE / INCOMPLETE
18_INTEGRATIONS.md                 COMPLETE / INCOMPLETE
19_SECURITY.md                     COMPLETE / INCOMPLETE
20_AUDIT_LOGGING.md                COMPLETE / INCOMPLETE
21_FILE_STORAGE.md                 COMPLETE / INCOMPLETE
22_REPORTS_ANALYTICS.md            COMPLETE / INCOMPLETE
23_SETTINGS.md                     COMPLETE / INCOMPLETE
24_ENVIRONMENT_CONFIG.md           COMPLETE / INCOMPLETE
25_DEPLOYMENT.md                   COMPLETE / INCOMPLETE
26_BACKUP_RECOVERY.md              COMPLETE / INCOMPLETE
27_TESTING.md                      COMPLETE / INCOMPLETE
28_SEED_DATA.md                    COMPLETE / INCOMPLETE
29_DEFINITION_OF_DONE.md           COMPLETE / INCOMPLETE
30_DEVELOPMENT_ROADMAP.md          COMPLETE / INCOMPLETE
31_TASK_BREAKDOWN.md               COMPLETE / INCOMPLETE
```

Planning cannot be marked READY if a critical applicable document remains incomplete.

---

# FINAL PLANNING STATUS

After completing and reviewing the documentation, report:

```text
PLANNING STATUS

Overall:
READY / NEEDS MINOR DECISIONS / NEEDS MAJOR DECISIONS / NOT READY

Documentation:
XX / 31 COMPLETE

Confirmed requirements:
...

Inferred requirements:
...

Recommended decisions:
...

Open product decisions:
...

Critical architecture decisions:
...

Architecture risks:
...

Database risks:
...

Security risks:
...

Integration risks:
...

UX risks:
...

MVP scope:
...

Phase 2 scope:
...

Development phases:
...

Total implementation tasks:
...

Blocking decisions:
...

Recommended next step:
...
```

Do NOT declare:

```text
READY FOR DEVELOPMENT
```

simply because all 31 files exist.

READY means the **contents are sufficiently complete, consistent, cross-referenced, technically sound, and implementation-ready**.

---

# CRITICAL RULE

The filenames are standardized.

The **content is project-specific**.

For every new project, discover:

- Domain entities
- Actors
- Workflows
- Business rules
- States
- Validation
- Risks
- Integrations
- Concurrency problems
- Security requirements
- Reporting requirements
- Operational requirements

Do not force concepts from previous projects into the new project.

A hospital system should be designed around its healthcare domain.

A school system should be designed around its education domain.

A marketplace should be designed around its marketplace domain.

A booking system should be designed around its booking domain.

A SaaS platform should be designed around its SaaS domain.

A logistics system should be designed around its logistics domain.

The **31-document framework stays consistent while the architecture inside those documents changes according to the project.**
