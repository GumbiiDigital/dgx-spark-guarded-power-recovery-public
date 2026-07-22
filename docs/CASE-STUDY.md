# Case study: recovery that defaults to refusal

## Actual problem

Power cycling can turn a monitoring mistake into an outage. The private project had to distinguish a failed target from a shared dependency, maintenance, or unsafe electrical/environmental state.

## Source-backed sequence

1. Commissioning established dependency order for network, controller, fan, and compute roles.
2. Physical relationships were corrected only after expected identity was observed after power-up.
3. Triage required three consecutive five-minute checks and independent failure signals.
4. A single isolated fixture became eligible; two simultaneous failures became a shared-outage refusal.
5. The policy journals before transition, verifies OFF and restore, and restores journaled state after interruption.
6. The local AC-ADA8 API remained unresolved; app/cloud state was a limitation.

## Failed hypotheses

- One missed ping means a Spark failed: false.
- A controller acknowledgement proves the intended target: false.
- A successful test justifies unattended recovery: unsupported.

## Bounded tests and gates

Source evidence covers healthy/no-cycle, isolated eligibility, shared-outage refusal, mapping verification, cooldown, maintenance pause, temperature/alarm safeguards, and interrupted-cycle restoration. Public acceptance is document and fixture checks only.

## Result

The strongest recorded result is the fail-closed policy and the commissioning lesson that identity, readback, and physical observation must agree.
