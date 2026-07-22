# Publication Safety

## Purpose

I publish guarded-recovery principles here without exposing physical or logical power topology.

## Allowed

- Synthetic recovery decisions.
- General multi-signal gate design.
- Refusal, cooldown, journal, verification, and rollback concepts.
- Fictional roles with no equipment mapping.
- Explicit limitations.

## Excluded

- Vendors, equipment counts, controller identities, and physical maps.
- Live addresses, accounts, credentials, device identities, or local paths.
- Actual thresholds, timings, measurements, telemetry, or state.
- Protocol captures and commands that can control equipment.
- Claims of unattended recovery readiness.

## Project-specific review

No public artifact may identify which load maps to which control point. A recovery example must remain non-executable and must show that unknown identity or unsafe state causes refusal.

## Gate

The checker validates JSON, required files, Mermaid-only architecture, and common private-data patterns. CI runs the same check. Physical commissioning evidence remains outside this repository.
