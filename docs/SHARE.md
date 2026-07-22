# Share Copy

## Short post

I built a public-safe design for guarded power recovery around a simple idea: the system should refuse more often than it acts. Recovery needs independent signals, identity proof, cooldown, journaling, verification, and rollback.

## Thread-style post

**Opening**

A power cycle is easy to automate and hard to make safe.

**The failure mode**

A missed probe can be a network event, maintenance, stale state, or the wrong target. Single-signal recovery turns uncertainty into risk.

**The design**

The decision binds identity, evidence, role, cooldown, maintenance, environment, rollback, and verification. Unknown or unsafe means refuse.

**Commissioning lesson**

A protocol acknowledgement is not enough. Readback, physical observation, restore behavior, and interruption recovery must agree.

**Publication boundary**

There are no vendors, mappings, thresholds, measurements, photos, or control instructions in the public repository.
