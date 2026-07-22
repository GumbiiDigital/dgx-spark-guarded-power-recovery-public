# Case Study: Recovery That Defaults to Refusal

## Context

A power cycle is easy to describe and hard to make safe. The difficult part is proving that the selected target is correct, isolated, recoverable, and actually failed.

## Problem

Single-signal recovery is brittle. A missed probe may represent a network event, a monitoring fault, maintenance, or a shared dependency. Acting on that signal can restart healthy equipment or remove the very infrastructure needed for recovery.

## What I built

The public contract requires independent evidence groups:

- target identity and role;
- failure isolation;
- peer and dependency health;
- maintenance state;
- environmental safety;
- cooldown and concurrency state; and
- controller state and verification capability.

The decision engine returns either a bounded recovery plan or a refusal with reasons. A plan expires and cannot be replayed.

## Engineering decisions

- Protected roles are denied by policy.
- Unknown is not treated as healthy.
- The target mapping is bound to the decision.
- The system journals before changing state.
- Every transition requires readback.
- Interrupted work restores the journaled target before considering another action.
- Commissioning remains separate from unattended operation.

## Representative artifact

The synthetic recovery decision shows a fictional target, evidence gates, refusal reasons, cooldown state, verification, and rollback fields. It contains no equipment identity, mapping, threshold, or live result.

## Evidence available here

- The example is valid JSON.
- The decision is explicitly synthetic and non-executable.
- Refusal logic and restoration intent are visible.
- The repository checker blocks common private-data patterns.
- CI repeats the publication gate.

## Lessons

A successful test does not automatically justify unattended recovery. The strongest result can be a correct refusal when identity, state, or restoration evidence is incomplete.

## Limitations

This case study omits vendors, equipment counts, mappings, protocol details, thresholds, photos, and measurements. It documents a safety method, not an operational controller.
