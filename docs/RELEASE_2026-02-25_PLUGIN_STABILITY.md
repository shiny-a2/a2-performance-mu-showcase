# Plugin Stability Release — 2026-02-25

## Release Scope
- `A2 Fast Archive Filters (MU)` -> `v1.3.8`
- `A2 Order Fix Box (MU)` -> `v1.7.1`
- `MU Admin + Action Scheduler Core` -> `v1.1.0`
- `A2 CRM Plugin` -> `v3.2.1`

## Incident Context
- A production SEO workflow was blocked: the Rank Math Redirections screen failed on `Add New Redirection`.
- Browser runtime showed duplicate redirections bundles and missing field-shape guards.
- Admin host-alias requests intermittently failed due to cross-origin admin AJAX URL resolution.

## Root Causes
- Two redirections runtimes were loaded on the same page (free + pro), causing inconsistent app state.
- Redirections frontend expected a complete field object and crashed when `start-date` was undefined.
- Some admin scripts consumed `admin-ajax.php` through non-canonical host aliases.

## Implemented Mitigations
- Added a targeted compatibility filter for Rank Math redirections field defaults.
- Added page-scoped same-origin normalization for admin AJAX URLs.
- Prevented duplicate redirections runtime load on the redirections admin page.
- Hardened typed min/max price input handling in archive filters.
- Tightened admin asset enqueue scope for order-fix UI to order screens only.
- Synced release versions in plugin headers and runtime asset versions.

## Verification
- PHP syntax checks passed for updated MU and CRM PHP modules.
- Console validation confirmed:
  - redirections compatibility filter is registered,
  - duplicate runtime condition is mitigated,
  - `Add New Redirection` flow executes without the previous runtime crash.
- Functional smoke checks passed for archive filter typing behavior and order admin workflows.

## Employer-Facing Impact
- Restored a critical SEO admin flow with no code rollback.
- Reduced repeat incident risk by adding deterministic page-scoped compatibility guards.
- Improved operational confidence with versioned release records and rollback tags in private source repositories.

## Privacy Note
- This document is public-safe and excludes private code and customer-sensitive data.
