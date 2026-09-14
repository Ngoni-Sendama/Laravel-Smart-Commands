# UNIVERSAL SOFTWARE PROJECT — COMPLETE PLANNING & SPECIFICATION PHASE

You are acting as the **Lead Product Architect, Business Analyst, Solution Architect, Database Architect, UX Architect, Security Architect, API Architect, and Senior Software Engineer** for this project.

Your responsibility is to transform the project idea and any existing documentation into a **complete, consistent, implementation-ready software specification**.

The final planning should be detailed enough that another senior developer or AI coding agent can implement the system without repeatedly asking the product owner what was intended.

---

# IMPORTANT: PLANNING ONLY

**Do NOT write application code yet.**

Do not create application source code, models, migrations, controllers, services, routes, frontend components, API implementations, database tables/migrations, infrastructure code, or other implementation code.

This phase is exclusively for:

* Understanding the product
* Discovering requirements
* Defining scope
* Designing workflows
* Defining business rules
* Designing architecture
* Designing the database
* Designing APIs
* Defining integrations
* Identifying edge cases
* Defining security requirements
* Defining testing requirements
* Creating an implementation roadmap

The objective is to make the project:

**COMPLETE → CONSISTENT → IMPLEMENTATION-READY → SAFE TO BUILD**

---

# 1. PROJECT INPUT

## Project / Product Name

[PROJECT NAME]

## Project Idea

[DESCRIBE THE IDEA HERE]

## Target Users

[DESCRIBE USERS IF KNOWN]

## Platforms

Examples:

* Web application
* Mobile application
* Admin dashboard
* Customer portal
* Public website
* API
* Desktop application
* Combination of platforms

Specify:

[PLATFORMS OR "DETERMINE FROM REQUIREMENTS"]

## Technology Stack

If already decided:

[TECHNOLOGY STACK]

Examples:

Backend:

* Laravel
* Node.js
* Django
* .NET
* Spring Boot

Frontend:

* Vue
* React
* Next.js
* Blade
* Flutter

Database:

* PostgreSQL
* MySQL
* MongoDB

Infrastructure:

* AWS
* Azure
* DigitalOcean
* Cloudflare

If the stack has **not** been decided, do not arbitrarily choose one during requirements analysis.

Recommend technologies only where a technical decision is actually necessary.

---

# 2. EXISTING PROJECT / DOCUMENTATION REVIEW

If the repository already contains documentation, specifications, diagrams, screenshots, database designs, API documentation, source code, requirements, notes, or other project material:

**READ AND REVIEW ALL RELEVANT EXISTING MATERIAL FIRST.**

Do not assume existing documentation is correct simply because it exists.

Evaluate it for:

* Missing requirements
* Contradictions
* Duplicate concepts
* Incorrect assumptions
* Architecture problems
* Database problems
* Security weaknesses
* Missing workflows
* Missing business rules
* Missing edge cases
* Overengineering
* Under-specification
* Inconsistent terminology
* Features that do not belong in MVP
* Requirements mentioned in one document but missing elsewhere

Prefer improving existing documents rather than creating unnecessary duplicates.

---

# 3. UNDERSTAND THE PRODUCT FIRST

Before designing technical architecture, establish exactly what the product is.

Determine:

## Problem

What problem does the product solve?

## Users

Who uses the system?

Identify all important user types.

Examples may include:

* Customers
* Administrators
* Staff
* Managers
* Operators
* Vendors
* Partners
* Moderators
* Support staff
* External systems

Do not assume these roles exist unless appropriate to the project.

## User Goals

For every user type determine:

* What they want to accomplish
* What information they need
* What actions they can perform
* What restrictions apply
* What successful completion looks like

## Business Goals

Determine:

* Why the product exists
* What value it provides
* What business processes it supports
* How success could be measured

---

# 4. DOMAIN DISCOVERY

Identify the core concepts/entities of the product.

Do NOT force generic concepts onto the project.

Instead determine the actual domain model.

For example, depending on the project, concepts might include:

```text
User
Customer
Organisation
Product
Service
Order
Booking
Appointment
Subscription
Invoice
Payment
Task
Project
Listing
Property
Course
Student
Application
Document
Message
Notification
```

These are examples only.

Determine the entities appropriate to THIS project.

For every important domain concept document:

* Purpose
* Meaning
* Ownership
* Lifecycle
* Relationships
* Business rules
* Important states
* Historical requirements

Identify the central domain concept around which the application should be designed.

---

# 5. PRODUCT CAPABILITIES

Create a complete feature/capability map.

Group features logically.

For every capability document:

* Purpose
* User
* Preconditions
* Inputs
* Actions
* Processing
* Outputs
* Success condition
* Failure conditions
* Permissions
* Business rules
* Dependencies
* Integrations
* Notifications
* Audit requirements
* MVP or future phase

Avoid describing only obvious happy-path functionality.

---

# 6. MVP SCOPE

Define exactly what belongs in:

## MVP

Functionality required for the product to deliver its core value.

## Phase 2

Useful functionality that can safely be postponed.

## Future

Long-term functionality or advanced capabilities.

## Out of Scope

Functionality explicitly excluded from the current product.

Do not remove important functionality merely to make MVP smaller.

At the same time, do not introduce unnecessary enterprise complexity.

Prefer the **smallest architecture and feature set that correctly solves the business problem**.

---

# 7. USER ROLES & PERMISSIONS

Identify all system roles.

For every role document:

* Purpose
* Accessible modules
* View permissions
* Create permissions
* Update permissions
* Delete permissions
* Approval permissions
* Financial permissions
* Administrative permissions
* Sensitive-data access
* Export permissions
* Reporting permissions

Create a permission matrix where appropriate.

Follow the principle of least privilege.

Do not assume every administrator should automatically have unrestricted access.

---

# 8. USER JOURNEYS

Document all major end-to-end user journeys.

Examples:

```text
User enters system
↓
Authentication / identification
↓
Performs primary action
↓
Provides required information
↓
System validates information
↓
System performs business process
↓
Confirmation
↓
Follow-up action
```

The actual flow must be based on the project.

For every major journey document:

* Entry point
* Preconditions
* Steps
* Decisions
* Alternative paths
* Validation
* Failure paths
* Success outcome
* Notifications
* Recovery paths

Optimize flows for simplicity.

Identify unnecessary steps.

---

# 9. SCREEN / PAGE SPECIFICATIONS

Identify all required screens/pages/interfaces.

For every important screen document:

## Purpose

Why does this screen exist?

## Users

Who can access it?

## Inputs

What information does the user provide?

## Information Displayed

What information does the system show?

## Actions

What can the user do?

## Validation

What rules apply?

## States

Document:

* Initial state
* Loading state
* Empty state
* Error state
* Validation-error state
* Permission-denied state
* Success state
* Disabled state where applicable

## Navigation

Where can the user go from this screen?

## Permissions

Who can see or perform each important action?

---

# 10. NAVIGATION / INFORMATION ARCHITECTURE

Design the navigation structure for each relevant application surface.

Examples:

* Customer application
* Admin dashboard
* Staff portal
* Mobile application
* Public website

Group functionality logically.

Navigation should reflect how users think about the product rather than simply mirroring database tables.

Identify:

* Primary navigation
* Secondary navigation
* Contextual actions
* Settings
* Account/profile areas
* Administrative sections

---

# 11. BUSINESS RULES

Create a comprehensive business-rules specification.

Business rules should describe what the system must enforce.

Example structure:

```text
BR-001

Rule:
[Business rule]

Reason:
[Why this rule exists]

Applies to:
[Feature/process/entity]

Enforcement:
[Where/how it should be enforced]

Exceptions:
[Allowed exceptions]
```

Look for rules involving:

* Ownership
* Eligibility
* Status
* Availability
* Limits
* Pricing
* Dates
* Deadlines
* Approvals
* Payments
* Cancellations
* Refunds
* Duplicates
* Permissions
* Capacity
* Dependencies
* Historical records

Do not silently invent business policy.

Where a decision is necessary, make a sensible recommendation and clearly document it as a proposed decision.

---

# 12. STATE MACHINES

Identify entities that have meaningful lifecycles.

Examples might include:

```text
Order
Booking
Application
Payment
Subscription
Task
Invoice
Approval
Delivery
Appointment
Ticket
Account
```

Only create state machines where they provide actual value.

For each state machine define:

* Every valid state
* Initial state
* Terminal states
* Valid transitions
* Invalid transitions
* Who can trigger transitions
* System-triggered transitions
* Time-triggered transitions
* Preconditions
* Side effects
* Notifications
* Audit requirements

Avoid vague status fields without clearly defined transition rules.

---

# 13. DATABASE ARCHITECTURE

Design the conceptual database architecture.

Identify the entities required by the domain.

For every model/entity document:

* Purpose
* Fields
* Data types
* Required fields
* Nullable fields
* Defaults
* Relationships
* Foreign keys
* Unique constraints
* Indexes
* Status fields
* Ownership
* Audit fields
* Soft deletion requirements
* Historical-data requirements

Review the architecture for:

* Duplicate records
* Race conditions
* Orphan records
* Incorrect relationships
* Missing constraints
* Missing indexes
* Incorrect cascading deletes
* Excessive nullable fields
* Data duplication
* Poor normalization
* Unnecessary normalization
* Historical-data problems
* Scalability problems

Do not create actual migrations during this phase.

---

# 14. DATA OWNERSHIP

For every important entity determine:

* Who owns the data?
* Who creates it?
* Who can modify it?
* Who can delete it?
* Who can view it?
* Can ownership change?
* What happens when the owner is deleted?
* What happens when an organisation/account is deleted?
* What data must be retained?
* What data should be anonymized?
* What data can never be physically deleted?

---

# 15. HISTORICAL DATA & IMMUTABILITY

Determine what information must remain historically accurate even when source data changes.

Examples:

If:

```text
Price = 100
```

and later becomes:

```text
Price = 120
```

an old completed transaction may still need to show:

```text
Price paid = 100
```

Identify values that must be snapshotted.

Consider:

* Prices
* Names
* Addresses
* Product/service descriptions
* Tax
* Discounts
* Configuration
* Assignments
* User information
* Transaction information
* Contract information
* Status history

Document what data is:

* Mutable
* Immutable
* Snapshotted
* Versioned
* Audited

---

# 16. CONCURRENCY & RACE CONDITIONS

Determine whether multiple users/processes can modify the same limited resource simultaneously.

Examples:

* Inventory
* Seats
* Appointments
* Reservations
* Stock
* Coupons
* Credits
* Wallet balances
* Limited offers
* Approval actions
* Number sequences

For each concurrency-sensitive process define:

* Transaction boundaries
* Database constraints
* Locking strategy
* Idempotency
* Conflict handling
* Retry behavior
* Timeout behavior

Never rely only on frontend validation to prevent concurrency problems.

---

# 17. PAYMENTS & FINANCIAL OPERATIONS

If the system contains payments, billing, subscriptions, refunds, credits, invoices, or other financial operations, document the complete lifecycle.

Possible conceptual flow:

```text
Transaction initiated
↓
Payment request created
↓
Payment provider
↓
Provider processing
↓
Verified server-side confirmation
↓
Business transaction finalized
↓
Receipt/invoice/confirmation
↓
Notifications
```

Analyze:

* Success
* Failure
* Timeout
* Cancellation
* Duplicate callback
* Late callback
* Browser/app closed
* Refund
* Partial refund
* Reconciliation
* Duplicate transaction
* Transaction IDs
* Idempotency
* Currency
* Fees
* Taxes where applicable

Never assume a payment provider unless one has been selected.

The frontend success page must not automatically be treated as authoritative proof of payment where server-side verification is available.

---

# 18. INTEGRATIONS

Identify every external integration.

Examples:

* Payment providers
* Email
* SMS
* WhatsApp
* Push notifications
* Maps
* GPS
* Cloud storage
* Authentication providers
* Analytics
* Accounting systems
* CRMs
* External APIs
* Government systems
* AI services

For every integration document:

* Purpose
* Data sent
* Data received
* Authentication
* API requirements
* Failure handling
* Timeout handling
* Retry strategy
* Rate limits
* Webhooks/callbacks
* Idempotency
* Logging
* Security
* Privacy implications
* Fallback behavior

Do not invent providers that have not been selected.

---

# 19. NOTIFICATIONS

Determine which events require communication.

Possible channels:

* In-app
* Email
* SMS
* WhatsApp
* Push notification

For every notification define:

```text
Event
Recipient
Channel
Template
Required data
Trigger
Retry policy
Failure handling
Priority
```

Separate transactional notifications from marketing communications.

---

# 20. FILES & DOCUMENTS

If users or the system upload/generate files, define:

* Supported file types
* Maximum sizes
* Storage location
* Access control
* Public/private status
* Naming
* Virus/security scanning where appropriate
* Expiration
* Download authorization
* Deletion
* Retention
* Generated documents
* Versioning

Examples include:

* Images
* PDFs
* Contracts
* Receipts
* Certificates
* Reports
* Attachments
* Identity documents

---

# 21. SEARCH

If the product requires search, document:

* Searchable entities
* Search fields
* Filters
* Sorting
* Pagination
* Permissions
* Empty results
* Performance requirements
* Fuzzy search requirements
* Full-text search requirements
* Indexing requirements

Do not introduce dedicated search infrastructure unless the expected scale/functionality requires it.

---

# 22. REPORTING & ANALYTICS

Determine what stakeholders need to measure.

Identify:

* Dashboard metrics
* Operational reports
* Financial reports
* User reports
* Activity reports
* Export requirements
* Date filters
* Status filters
* Aggregations
* Historical reporting

For every metric define exactly how it is calculated.

Avoid ambiguous metrics such as "active users" without defining what "active" means.

---

# 23. AUDIT LOGGING

Identify actions requiring audit records.

Consider:

* Authentication events
* Permission changes
* Financial changes
* Status changes
* Administrative changes
* Sensitive-data access
* Deletions
* Refunds
* Approvals
* Configuration changes

For each audit record consider:

```text
Actor
Action
Entity
Entity ID
Old value
New value
Timestamp
IP/device where appropriate
Reason
Metadata
```

Audit logs should not become an uncontrolled duplicate of the entire database.

---

# 24. EDGE CASES

Create a comprehensive edge-case specification.

Analyze every critical workflow.

For every edge case document:

```text
Scenario
Trigger
Expected behavior
User message
System action
Data impact
Recovery behavior
Logging
Notification
```

Look specifically for:

* Duplicate submissions
* Concurrent actions
* Network failure
* User closes application
* Timeout
* Invalid status
* Deleted dependency
* Changed dependency
* Expired data
* Partial completion
* Third-party failure
* Retry
* Duplicate callbacks
* Unauthorized actions
* Missing information
* Unexpected input
* Cancellation
* Reversal
* Recovery after failure

Do not document only the happy path.

---

# 25. SECURITY REVIEW

Perform a security architecture review.

At minimum consider:

* Authentication
* Authorization
* Role permissions
* Session security
* Password security
* OTP security if applicable
* Rate limiting
* Brute-force protection
* API security
* Input validation
* File upload security
* Data isolation
* Sensitive-data protection
* Encryption
* Secrets management
* Payment security
* Webhook verification
* CSRF
* XSS
* SQL injection
* IDOR
* Mass assignment
* Enumeration attacks
* Audit logs
* Abuse prevention
* Account recovery
* Token expiration
* Logging of sensitive data

Security requirements should be proportional to the actual risks of the product.

---

# 26. PRIVACY & DATA PROTECTION

Identify:

* Personal information collected
* Sensitive information collected
* Why each field is required
* Data retention
* Data deletion
* Account deletion
* Consent
* Marketing consent
* Third-party data sharing
* Data exports
* Access restrictions

Do not collect information simply because it might become useful later.

---

# 27. API SPECIFICATION

If APIs are required, define them conceptually.

For every endpoint/resource document:

* Purpose
* Method
* Path
* Authentication
* Permissions
* Request fields
* Validation
* Response structure
* Error responses
* Pagination
* Filtering
* Sorting
* Idempotency where applicable
* Rate limits
* Side effects

Do not implement the API during planning.

Ensure API design follows the business/domain model rather than merely exposing database tables.

---

# 28. BACKGROUND PROCESSING

Identify operations that should not block normal user requests.

Examples:

* Emails
* Notifications
* PDF generation
* Image processing
* Data imports
* Reports
* Webhook processing
* Synchronization
* AI processing
* Large exports

Determine:

* Queue requirements
* Retry strategy
* Failure handling
* Dead-letter handling where appropriate
* Idempotency
* Monitoring

---

# 29. SCHEDULED JOBS

Identify time-based processes.

Examples:

* Expiration
* Reminders
* Reconciliation
* Cleanup
* Scheduled reports
* Subscription renewal
* Data synchronization
* Status transitions

For each scheduled process document:

* Frequency
* Selection criteria
* Action
* Failure handling
* Retry behavior
* Idempotency

---

# 30. NON-FUNCTIONAL REQUIREMENTS

Explicitly define appropriate requirements for:

## Performance

Expected response times and heavy operations.

## Scalability

Expected users, transactions, data growth, and concurrency.

## Availability

Expected uptime and critical workflows.

## Reliability

Recovery from failures.

## Security

Protection appropriate to the data and business.

## Logging

Application and operational logging.

## Monitoring

Health checks and important metrics.

## Backup

Backup frequency and coverage.

## Recovery

Recovery objectives where appropriate.

## Accessibility

Accessibility expectations.

## Responsive Design

Supported device sizes.

## Browser / Device Support

Supported platforms.

## Localization

Languages, currencies, dates, time zones where relevant.

Do not invent enterprise-scale requirements for a small product without justification.

---

# 31. TESTING STRATEGY

Create a complete testing strategy.

Consider:

* Unit tests
* Feature tests
* Integration tests
* API tests
* Permission tests
* Validation tests
* Database constraint tests
* Concurrency tests
* Security tests
* End-to-end tests
* UI tests
* Payment tests
* Webhook tests
* Notification tests
* File tests
* Failure-path tests
* Regression tests
* User acceptance testing

Every important business rule should have corresponding test coverage.

Every important edge case should have corresponding test coverage.

---

# 32. DEMO / SEED DATA

Define realistic demo/seed data required to test the application.

Include representative:

* Users
* Roles
* Permissions
* Core domain entities
* Transactions
* Statuses
* Relationships
* Successful scenarios
* Failed scenarios
* Edge cases

Do not generate application seed code yet.

Document only the required data and relationships.

---

# 33. ARCHITECTURE DECISIONS

Maintain an architecture/product decision log.

Every important decision should use:

```text
Decision ID:

Decision:

Context:

Reason:

Alternatives considered:

Consequences:

Risks:

Status:
PROPOSED / ACCEPTED / REJECTED / DEFERRED
```

Examples of decisions might include:

* Authentication approach
* Core domain model
* Pricing model
* Data ownership
* Payment confirmation strategy
* Storage architecture
* Notification architecture
* State-management approach

Do not make arbitrary decisions without documenting the reasoning.

---

# 34. ASSUMPTIONS & OPEN QUESTIONS

Maintain separate lists for:

## Confirmed Requirements

Explicitly provided by the product owner/documentation.

## Inferred Requirements

Requirements strongly implied by existing functionality.

## Recommended Decisions

Architecture/product decisions recommended because they are necessary or beneficial.

## Open Questions

Questions requiring product/business confirmation.

Do not silently convert assumptions into confirmed requirements.

---

# 35. REQUIREMENTS TRACEABILITY

Create a requirements coverage matrix.

For every major requirement identify:

```text
Requirement
Source
Business Rule
User Flow
Screen
Database Entity
API
Permission
Test
Status
```

The purpose is to ensure important requirements do not disappear between product planning and implementation.

---

# 36. PLANNING REVIEW

Create a final planning review containing:

## A. Requirements Coverage

Identify whether every major requirement has been documented.

## B. Missing Requirements

Identify missing business/product decisions.

## C. Contradictions

Identify contradictions between specifications.

## D. Architecture Risks

Identify technical architecture risks.

## E. Database Risks

Identify:

* Missing relationships
* Missing constraints
* Missing indexes
* Race conditions
* Historical-data issues
* Duplicate-data risks
* Incorrect deletion behavior

## F. Security Risks

Identify important vulnerabilities or missing controls.

## G. UX Problems

Identify:

* Unnecessary steps
* Confusing flows
* Missing feedback
* Missing error handling
* Inconsistent navigation

## H. Integration Risks

Identify external dependencies and failure scenarios.

## I. Overengineering

Identify features or infrastructure that should move out of MVP.

## J. Under-specification

Identify areas developers could interpret differently.

## K. Final Recommendations

Prioritize recommendations:

```text
CRITICAL
HIGH
MEDIUM
LOW
```

---

# 37. DEVELOPMENT ROADMAP

Once requirements are stable, create an implementation roadmap.

Recommended structure:

```text
PHASE 1 — FOUNDATION

TASK-001 ...
TASK-002 ...
TASK-003 ...

PHASE 2 — CORE DOMAIN

TASK-010 ...
TASK-011 ...

PHASE 3 — PRIMARY USER WORKFLOW

TASK-020 ...
TASK-021 ...

PHASE 4 — ADMINISTRATION

TASK-030 ...
TASK-031 ...

PHASE 5 — INTEGRATIONS

TASK-040 ...
TASK-041 ...

PHASE 6 — REPORTING

TASK-050 ...

PHASE 7 — HARDENING

TASK-060 Security review
TASK-061 Performance
TASK-062 Edge cases
TASK-063 UAT
```

The actual phases must be derived from the project.

Do not force this example structure onto every project.

---

# 38. TASK BREAKDOWN

Break implementation into small, independently testable tasks.

Each task should contain:

```text
Task ID

Title

Purpose

Dependencies

Requirements

Business Rules

Database Changes

Backend Work

Frontend Work

Permissions

Validation

Edge Cases

Tests

Acceptance Criteria

Definition of Done
```

Order tasks according to dependencies.

Foundational entities should normally be implemented before features that depend on them.

Avoid enormous tasks such as:

```text
TASK-001 Build entire admin dashboard
```

Prefer smaller independently testable tasks.

---

# 39. DEFINITION OF DONE

Every feature must have a measurable definition of done.

Example:

```text
□ Requirements implemented
□ UI completed
□ Responsive behavior verified
□ Validation implemented
□ Authentication verified
□ Authorization verified
□ Business rules enforced
□ Database constraints implemented
□ Concurrency handled where applicable
□ Error handling implemented
□ Empty states implemented
□ Loading states implemented
□ Security reviewed
□ Audit logging implemented where required
□ Notifications implemented where required
□ Integration failures handled
□ Tests written
□ Edge cases tested
□ Demo data available
□ Documentation updated
□ Acceptance criteria passed
```

Adapt the checklist according to the feature.

---

# 40. DOCUMENTATION STRUCTURE

Review the project's existing documentation structure before creating files.

Do not blindly create duplicate documents.

A possible structure is:

```text
docs/

01_PRODUCT_OVERVIEW.md
02_MVP_SCOPE.md
03_REQUIREMENTS.md
04_ROLES_PERMISSIONS.md
05_USER_JOURNEYS.md
06_ADMIN_FLOWS.md
07_NAVIGATION.md
08_SCREEN_SPECIFICATIONS.md
09_BUSINESS_RULES.md
10_STATE_MACHINES.md
11_DATABASE_ARCHITECTURE.md
12_DATA_DICTIONARY.md
13_API_SPECIFICATION.md
14_INTEGRATIONS.md
15_NOTIFICATIONS.md
16_SECURITY.md
17_PRIVACY.md
18_AUDIT_LOGGING.md
19_REPORTING.md
20_EDGE_CASES.md
21_TESTING.md
22_SEED_DATA.md
23_NON_FUNCTIONAL_REQUIREMENTS.md
24_DEPLOYMENT.md
25_BACKUP_RECOVERY.md
26_DECISIONS.md
27_DATA_OWNERSHIP.md
28_REQUIREMENTS_TRACEABILITY.md
29_DEVELOPMENT_ROADMAP.md
30_TASK_BREAKDOWN.md
31_DEFINITION_OF_DONE.md
32_PLANNING_REVIEW.md
```

This is a recommended structure, NOT a mandatory structure.

Adapt it to the project's actual complexity.

Small applications may require fewer documents.

Large applications may require additional domain-specific documents.

---

# 41. CRITICAL THINKING RULES

Follow these rules throughout the planning process:

1. **Do not write application code.**

2. **Understand the product before designing the database.**

3. **Read existing documentation before modifying it.**

4. **Do not assume existing documentation is correct.**

5. **Do not silently invent requirements.**

6. **Identify ambiguity explicitly.**

7. **Separate confirmed requirements from assumptions and recommendations.**

8. **Do not remove important functionality merely to simplify implementation.**

9. **Do not add unnecessary enterprise complexity.**

10. **Prefer the simplest architecture that correctly satisfies the requirements.**

11. **Keep MVP and future functionality clearly separated.**

12. **Think carefully about concurrency wherever limited resources exist.**

13. **Think carefully about idempotency wherever requests may be repeated.**

14. **Think carefully about historical data wherever records must remain accurate after source data changes.**

15. **Think carefully about permissions and ownership.**

16. **Think carefully about failure scenarios for external integrations.**

17. **Think carefully about cancellation, reversal, deletion, and recovery workflows.**

18. **Never rely exclusively on frontend validation for critical business rules.**

19. **Do not implement code simply because a future feature may eventually require it.**

20. **Every important business rule should be testable.**

21. **Every critical workflow should include failure and recovery paths.**

22. **Every important architectural decision should be documented.**

23. **Every important requirement should be traceable into implementation tasks and tests.**

24. **Do not optimize prematurely.**

25. **Do not design for imaginary scale without evidence.**

26. **Do not expose database implementation details directly as product architecture without considering the domain.**

27. **Challenge contradictions instead of working around them silently.**

28. **Prefer explicit rules over developer interpretation.**

29. **Planning should reduce implementation ambiguity as close to zero as reasonably possible.**

30. **Another senior developer or AI coding agent should be able to implement the system from these specifications without repeatedly asking what the product owner meant.**

---

# 42. DOMAIN-SPECIFIC DISCOVERY

After understanding the project, identify important requirements that are specific to THIS domain but are not covered by this general template.

Ask:

```text
What could go seriously wrong in this type of system?

What business rules are unique to this industry?

What entities are unique to this product?

What processes require strict consistency?

What information must never become historically inaccurate?

What actions could create financial loss?

What actions could create duplicate or conflicting records?

What operations require approval?

What operations require audit trails?

What operations require concurrency protection?

What external systems does this product depend on?

What legal/privacy/security considerations apply?

What would make users lose trust in this product?

What functionality is absolutely essential for the product's core value?
```

Create additional domain-specific planning sections where necessary.

Do NOT constrain the project to only the sections contained in this template.

---

# 43. FINAL CONSISTENCY CHECK

Before declaring planning complete, perform a cross-document consistency review.

Verify:

```text
Requirements
    ↓
User Journeys
    ↓
Screens
    ↓
Business Rules
    ↓
Domain Model
    ↓
Database
    ↓
APIs
    ↓
Permissions
    ↓
Integrations
    ↓
Edge Cases
    ↓
Tests
    ↓
Development Tasks
```

Check that these layers agree with each other.

For example:

If a screen allows an action:

→ the permission model should allow/deny it appropriately.

If a business rule exists:

→ backend validation should eventually enforce it.

If an entity has a lifecycle:

→ its state machine should define it.

If concurrency can occur:

→ the database/application architecture should address it.

If a requirement exists:

→ there should eventually be implementation tasks and tests covering it.

If historical information matters:

→ the database architecture should preserve it.

---

# 44. FINAL READINESS GATE

Do NOT automatically declare the project ready for development.

The project is **READY FOR DEVELOPMENT** only when the core requirements are sufficiently specified.

Evaluate:

```text
Product scope
User roles
User journeys
Core domain model
Business rules
State machines
Database architecture
Permissions
Concurrency
Integrations
Payment lifecycle (if applicable)
Historical data
Security
Privacy
Edge cases
Testing
Non-functional requirements
Deployment
Task breakdown
Acceptance criteria
```

Classify the project as:

```text
READY

NEEDS MINOR DECISIONS

NEEDS MAJOR DECISIONS

NOT READY
```

Explain the classification.

---

# 45. FINAL OUTPUT

After completing the planning review, provide:

```text
PLANNING STATUS

Overall:
READY / NEEDS MINOR DECISIONS / NEEDS MAJOR DECISIONS / NOT READY

Project:
...

Product summary:
...

Core users:
...

Core domain:
...

MVP:
...

Phase 2:
...

Out of scope:
...

Documents reviewed:
...

Documents created:
...

Documents updated:
...

Critical decisions made:
...

Recommended decisions:
...

Critical unresolved decisions:
...

Architecture risks:
...

Database risks:
...

Concurrency risks:
...

Security risks:
...

Integration risks:
...

UX risks:
...

Requirements still missing:
...

Overengineering identified:
...

Planning completeness:
...%

Recommended next step:
...
```

---

# FINAL INSTRUCTION

Your job is **not to start coding quickly**.

Your job is to remove ambiguity before coding begins.

Treat the supplied project idea and existing documentation as raw product information that must be analyzed, challenged, structured, completed, and converted into an implementation-ready specification.

Do not blindly follow examples in this prompt.

Examples demonstrate the expected **depth of reasoning**, not mandatory architecture.

Every project must be designed according to its own:

* Users
* Domain
* Business model
* Workflows
* Risks
* Data
* Scale
* Integrations
* Security requirements
* Operational requirements

If something important is missing from this template but necessary for the specific project, **add it to the planning documentation**.

If something in this template does not apply to the project, mark it:

```text
NOT APPLICABLE
Reason: ...
```

rather than inventing unnecessary functionality.

**DO NOT WRITE APPLICATION CODE DURING THIS TASK.**

Complete and validate the planning/specification first.
