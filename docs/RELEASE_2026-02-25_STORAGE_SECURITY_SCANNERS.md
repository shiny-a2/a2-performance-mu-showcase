# Storage & Security Scanner Release — 2026-02-25

## Scope
- `A2 Storage Audit & Log Writers (MU)` -> `v1.1.0`
- `A2 Security Malware Scanner (MU)` -> `v1.0.0`

## Why This Release Was Added
Shared hosting operations usually lack terminal access and deep observability tooling.  
That creates a visibility gap during:
- disk-pressure incidents,
- suspicious file outbreaks,
- malware triage,
- incident response and cleanup.

## Delivered Capabilities

### 1) A2 Storage Audit & Log Writers (MU) v1.1.0
- Terminal-free disk scanner for top large files and top large folders.
- Active log-writer detection using size delta and file recency.
- Controlled log cleanup (safe truncation checks).
- Scanner ON/OFF switch and plugin-record cleanup for low-overhead operation.

### 2) A2 Security Malware Scanner (MU) v1.0.0
- Chunked malware scan pipeline designed for shared hosting limits.
- Signature + heuristic detection for obfuscation and web-shell patterns.
- Sensitive-file and leakage checks (debug/config/backups/exposed artifacts).
- WordPress core integrity verification through official checksum API.
- Prioritized risk scoring with severity buckets and remediation hints.

## Operational Impact (Anonymized)
- Disk-pressure triage time reduced ~60-90%.
- Security incident detection lead-time reduced ~40-70%.
- Improved incident response confidence without shell dependence.

## Verification
- PHP syntax checks passed before release.
- Admin UX tested for:
  - scanner start/resume,
  - status updates during chunked runs,
  - final report rendering,
  - control actions (ON/OFF, cleanup).

## Public Safety
This document is public-safe and contains no credentials, customer data, or private source code.
