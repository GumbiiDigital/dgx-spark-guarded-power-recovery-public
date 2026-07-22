# DGX Spark Guarded Power Recovery Public

I built this repository to explain the safety principles behind guarded power recovery for local AI systems. The design assumes that a restart is a high-risk action, not a generic response to a failed ping.

## What I built

The public design combines:

- multi-signal failure detection;
- identity and role verification;
- protected-role refusal logic;
- maintenance and environmental gates;
- per-target cooldown;
- single-operation locking;
- pre-action journaling;
- restore and verification steps; and
- explicit rollback and unresolved-state reporting.

No physical or logical equipment map is published.

## Why it matters

Power automation can convert a small monitoring error into an outage. A stale status, shared network failure, wrong target, or incomplete restore can all make a simple cycle unsafe.

The system should refuse more often than it acts.

## Engineering approach

A recovery decision is short-lived and bound to one synthetic target, one mapping digest, one evidence snapshot, and one reason set. Dependent infrastructure roles are denied. Unknown identity, shared failure, maintenance state, unsafe environment, cooldown, stale evidence, or replay causes refusal.

If an authorized recovery begins, the journal exists before the first state change. Verification follows every transition, and an interrupted operation prioritizes restoration rather than another cycle.

## Synthetic public-safe architecture

The diagram shows the decision and refusal flow without vendor details, target counts, controller counts, thresholds, or equipment mapping.

See [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md).

## Representative work and artifacts

- [Case study](docs/CASE-STUDY.md) - commissioning lessons and fail-closed recovery.
- [Synthetic recovery decision](examples/synthetic-recovery-decision.json) - multi-signal gates and refusal logic.
- [Publication safety](docs/PUBLICATION-SAFETY.md) - physical and logical privacy boundary.
- [Share copy](docs/SHARE.md) - concise public narrative.
- [Safety checker](scripts/check_publication_safety.py) - local and CI publication gate.

## Evidence and lessons

The public evidence is limited to the safety contract, synthetic decision schema, valid JSON, explicit limitations, and automated privacy checking. It is not proof of a deployed recovery system.

The commissioning lesson is that protocol acknowledgement is not enough. Identity, state readback, physical observation, restore behavior, and failure recovery must agree before unattended action is defensible.

## Repository map

| Path | Purpose |
|---|---|
| README.md | Recovery design and limits |
| docs/CASE-STUDY.md | Guarded commissioning case study |
| docs/ARCHITECTURE.md | Synthetic Mermaid decision flow |
| docs/PUBLICATION-SAFETY.md | Publication rules |
| docs/SHARE.md | Share-ready copy |
| examples/ | Synthetic recovery JSON |
| scripts/check_publication_safety.py | Privacy and structure checker |
| .github/workflows/publication-safety.yml | CI gate |

## Publication boundary

This is a public project interface, not an operational deployment repository. I publish no vendor details, live addresses, hostnames, hardware identities, accounts, local paths, credentials, raw telemetry, thresholds, service inventories, private topology, physical maps, controller identities, or operational commands. Examples are synthetic and do not reproduce a live environment.

## Limitations

This repository does not identify equipment, disclose mappings, state operational thresholds, claim unattended recovery, or report live status. The public decision example is illustrative and cannot control hardware.
