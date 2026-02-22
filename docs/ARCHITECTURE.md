# Architecture

The suite is organized as composable MU-plugin capabilities:

- Request-path optimization: microcache decision layer and cookie policy.
- Query-path optimization: archive/listing query tuning and response shaping.
- Job-path stabilization: scheduler controls and transient cleanup guardrails.
- API hardening path: snapshot responses, allowlist firewall, and rate limits.

This layered model allows incremental rollout while isolating risk per subsystem.
