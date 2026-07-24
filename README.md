# Guarded Power Recovery for DGX Spark

I built this repository to record a conservative recovery policy for local AI equipment. The private source contains commissioning records, policy, verification evidence, an example configuration, and five close-up controller photographs. This public branch keeps the engineering relationship and safety decisions while removing actionable physical and logical maps.

## What I built

1. Read-only triage using independent reachability and identity signals.
2. Refusal for shared outages, partial failures, maintenance, alarms, high temperature, uncertain mapping, or cooldown.
3. A one-time decision bound to evidence, mapping digest, identity, and operation ID.
4. Journal-before-actuation, verify-after-transition, restore-on-interruption, and no-loop behavior.
5. A fan/environment role separated from compute recovery.
6. Example TSV and shell assets that produce decisions without controlling hardware.

## Recorded results

| Observation | Source evidence | Status |
|---|---|---|
| Controller label: 1,800 W at 120 V / 15 A aggregate | source photograph and README | Historical hardware reading |
| Healthy scheduled pass; no outlet changed | source verification | Historical |
| Isolated failure eligible after three consecutive checks | source policy/verification | Fixture result |
| Two simultaneous failures classified shared-outage/no-cycle | source policy/verification | Fixture result |
| Compute relationships checked against expected identity before authority | source implementation record | Commissioning lesson |
| Supported local AC-ADA8 API not established | source limitations | Unresolved boundary |

## Why it matters

A missed ping is not permission to remove power. The system should refuse more often than it acts and must leave shared infrastructure outside recovery authority.

## Engineering approach

The contract preserves multi-signal triage, maintenance pause, temperature/alarm safeguards, cooldown, serialized operations, and readback. Exact controller names, outlets, addresses, rack photographs, and operational thresholds are not reproduced.

## Sanitized architecture boundary

See [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md).

## Repository map

- [docs/CASE-STUDY.md](docs/CASE-STUDY.md)
- [docs/RECOVERY-EVIDENCE.md](docs/RECOVERY-EVIDENCE.md)
- [docs/PUBLICATION-SAFETY.md](docs/PUBLICATION-SAFETY.md)
- [examples/synthetic-recovery-decision.json](examples/synthetic-recovery-decision.json)

## Evidence rules and limits

The readings above are historical source evidence, not current status. This is a public project interface, not a live power-control repository. It publishes no vendor/controller identity, outlet map, address, credential, raw telemetry, or command targeting real equipment.

## Copyright

Copyright (c) 2026 Gumbii Digital. All rights reserved. See
[COPYRIGHT.md](COPYRIGHT.md) for the publication and reuse terms.
