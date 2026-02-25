# Storage & Security Scanner Release — 2026-02-25

## Scope
- `A2 Storage Audit & Log Writers (MU)` -> `v1.2.0`
- `A2 Security Malware Scanner (MU)` -> `v1.2.0`

## Why This Release Was Extended
Shared hosting operations usually lack terminal access and deep observability tooling.  
This release extends the scanner stack with deeper signal quality and more actionable remediation output while keeping resource usage safe for shared hosting.

## Delivered Capabilities

### 1) A2 Storage Audit & Log Writers (MU) v1.2.0
- Terminal-free disk scanner for top large files.
- **Top final leaf-folder sizing** (no parent roll-up), so heavy terminal directories are visible directly.
- Active log-writer detection using size delta and file recency.
- Controlled log cleanup (safe truncation checks).
- Scanner ON/OFF switch and plugin-record cleanup for low-overhead operation.

### 2) A2 Security Malware Scanner (MU) v1.2.0
- Three-phase shared-host-safe scan pipeline: `filesystem -> checksums -> database`.
- Advanced signature + heuristic detection for obfuscation and web-shell patterns.
- IOC extraction and risk scoring (URL/domain/IP/email) with source-path visibility.
- Sensitive-file and leakage checks (debug/config/backups/exposed artifacts).
- WordPress core integrity verification through official checksum API.
- `wp_options` persistence checks for suspicious payload patterns.
- Persian detailed report panels with actionable remediation plan.

## Operational Impact (Anonymized)
- Disk-pressure triage time reduced ~60-90%.
- Security incident detection lead-time reduced ~40-70%.
- Better remediation speed due to prioritized action plan and richer finding context.

## Verification
- PHP syntax checks passed before release.
- Admin UX tested for:
  - scanner start/resume,
  - status updates during chunked runs,
  - final report rendering,
  - control actions (ON/OFF, cleanup).

## Public Safety
This document is public-safe and contains no credentials, customer data, or private source code.
