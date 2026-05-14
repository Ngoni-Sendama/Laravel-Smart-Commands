# Laravel Authorization Migration Impact Analysis Prompt

## Objective

Perform a complete migration impact analysis for converting this Laravel application to use ONLY Spatie Roles & Permissions as the single authorization system.

The application currently has a hybrid authorization architecture using:

1. UserRole enum / users.role column
2. Spatie Laravel Permission roles & permissions
3. FilamentShield-generated permissions
4. Custom role middleware
5. Policy-based authorization

The goal of this review is to identify ALL files, logic, database structures, middleware, routes, policies, controllers, enums, and frontend components that would be affected if the application fully migrates to:

# Single Source of Truth:

Spatie Roles & Permissions ONLY

---

# Migration Goal

After migration:

* ALL authorization should use Spatie roles/permissions
* users.role column should eventually be removable
* UserRole enum should no longer control authorization
* Custom role middleware should be removed or rewritten
* Policies should use permissions consistently
* Filament and frontend should share the same authorization layer

---

# Required Review Scope

## 1. Database Impact Analysis

Review all migrations and database structures.

Identify:

* tables affected
* columns affected
* enums affected
* foreign keys affected
* indexes affected
* seeders affected

Specifically identify:

* where users.role is used
* where onboarding/verification logic overlaps authorization
* where role values are duplicated

Provide:

* migration plan
* safe deprecation strategy
* rollback concerns
* data migration risks

---

## 2. Model Impact Analysis

Review all models.

Identify:

* models using UserRole enum
* models using hasRole()
* models using can()
* models using direct role comparisons
* models using custom authorization logic

Find all code like:

```php
$user->role === UserRole::ADMIN
$user->role === 'seller'
$user->isAdmin()
$user->isSeller()
```

Determine:

* what breaks if users.role is removed
* what should be replaced with Spatie role checks
* what helper methods should be rewritten

Provide:

* exact methods requiring updates
* recommended replacements

---

## 3. Middleware Impact Analysis

Review all middleware.

Especially:

* CheckRole middleware
* seller verification middleware
* onboarding middleware
* Filament middleware
* custom authorization middleware

Identify:

* middleware depending on UserRole enum
* middleware depending on users.role column
* middleware already compatible with Spatie

Determine:

* which middleware can be deleted
* which middleware should use:

  * role middleware
  * permission middleware
  * policies
  * gates

Provide:

* exact middleware replacement plan

---

## 4. Route Impact Analysis

Review all route files.

Identify:

* routes using custom role middleware
* routes checking UserRole enum
* routes using direct role logic
* routes already using Spatie middleware

Analyze:

* admin routes
* seller routes
* buyer routes
* dashboard redirects
* onboarding routes
* Filament routes

Determine:

* what breaks after removing enum roles
* route protection gaps
* route middleware conflicts

Provide:

* exact route migration strategy

---

## 5. Policy Impact Analysis

Review all policies.

Identify:

* policies using hasRole()
* policies using can()
* policies using direct enum checks
* policies mixing roles and permissions

Determine:

* policies needing refactor
* policies that should trust permissions only
* duplicated authorization logic

Provide:

* policy standardization recommendations

---

## 6. Blade & Frontend Impact Analysis

Review all Blade files, Livewire components, and frontend authorization logic.

Identify all usage of:

```blade
@role
@can
@if(auth()->user()->role === ...)
@if($user->role === ...)
```

Determine:

* what breaks if users.role is removed
* where frontend logic depends on enum roles
* where permissions should replace roles

Provide:

* frontend authorization migration plan

---

## 7. Filament Impact Analysis

Review:

* Filament resources
* pages
* widgets
* navigation visibility
* panel access
* Shield integration

Identify:

* resources relying on UserRole enum
* resources relying on Spatie roles
* mixed authorization logic

Determine:

* whether Shield permissions are correctly integrated
* whether generated permissions align with business authorization

Provide:

* Filament migration safety analysis

---

## 8. Seeder & Permission Generation Analysis

Review:

* RolesAndPermissionsSeeder
* Shield-generated permissions
* custom permission seeders

Identify:

* permission naming inconsistencies
* duplicated permissions
* unused permissions
* missing permissions

Determine:

* whether current permissions are sufficient
* whether additional business permissions are needed

Provide:

* recommended permission structure

---

## 9. Enum Impact Analysis

Review all enums.

Identify:

* enums used for authorization
* enums safe to keep
* enums that should be removed

Determine:

* which enums become obsolete
* which enums should remain for:

  * status
  * verification
  * onboarding
  * moderation

Provide:

* enum cleanup strategy

---

## 10. Authentication & Redirect Logic

Review:

* login redirects
* dashboard redirects
* onboarding redirects
* post-registration logic

Identify:

* role-based redirects
* enum-dependent redirects
* admin/seller/buyer branching

Determine:

* how redirects should work after migration

Provide:

* updated redirect architecture

---

## 11. Cache & Performance Impact

Review:

* Spatie permission cache
* role lookups
* repeated permission queries
* eager loading

Determine:

* performance risks after migration
* cache invalidation needs
* middleware overhead

Provide:

* recommended optimization strategy

---

# Required Deliverables

## A. Files Affected

Provide a categorized list of ALL affected files including:

* migrations
* models
* middleware
* routes
* policies
* providers
* Blade files
* Livewire components
* Filament resources
* seeders
* services
* enums

For each file explain:

* why it is affected
* what needs changing
* migration complexity
* migration risk

---

## B. Breaking Changes Analysis

Identify:

* immediate breaking changes
* hidden breaking changes
* authorization regressions
* policy conflicts
* route access risks

---

## C. Migration Strategy

Provide:

### Phase 1

Safe preparation steps.

### Phase 2

Parallel compatibility mode.

### Phase 3

Spatie-only migration.

### Phase 4

Cleanup and removal of enum authorization.

---

## D. Risk Assessment

Categorize risks as:

* Critical
* High
* Medium
* Low

Explain:

* what can break
* how severe
* mitigation strategy

---

## E. Final Recommendation

Answer:

1. Is migration to pure Spatie authorization recommended?
2. Is the current architecture salvageable?
3. What is the safest migration path?
4. What should NOT be migrated?
5. Which authorization patterns should remain?

---

# Important Instructions

* Be extremely detailed.
* Trace ALL authorization flows.
* Identify hidden dependencies.
* Search for direct role string comparisons.
* Search for enum comparisons.
* Search for middleware assumptions.
* Search for frontend authorization coupling.
* Search for Filament-specific authorization logic.
* Explain WHY each affected file matters.
* Focus on production-safe migration strategy.
* Prioritize maintainability and consistency.
* Assume Laravel 12 + Filament + Spatie best practices.

---

# Files To Review

Review all relevant files including:

* database/migrations/*
* app/Models/*
* app/Enums/*
* app/Policies/*
* app/Http/Middleware/*
* app/Providers/*
* routes/*
* app/Filament/*
* resources/views/*
* app/Livewire/*
* app/Services/*
* database/seeders/*
* config/permission.php
* auth-related traits/helpers/services

---

# Expected Review Style

The analysis should resemble:

* enterprise migration audit
* senior Laravel architecture review
* production authorization migration plan
* security-focused refactor assessment

The review must be highly technical, thorough, and realistic about migration risks.
