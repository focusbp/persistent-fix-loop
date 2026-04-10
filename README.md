# Persistent Fix Loop (PFL)

A practical standard for self-healing systems that never “finish”, but continuously stabilize in production.



## Overview

Persistent Fix Loop (PFL) is a design model that does not try to “complete” fixes.

Instead, it assumes:

→ Systems should continuously stabilize through observation.

Rather than:

- Design → Implement → Test → Complete

PFL uses:

- Observe → Fix → Release → Observe → …

This is a loop-based model.



## Background

In real systems:

- Requirements change
- Environments change
- Data changes
- Perfect fixes cannot be defined

Therefore:

→ Defining “completion” internally becomes a source of instability

PFL embraces this reality.



## Core Model

Detect → Plan → Fix → Release → Monitor → (Loop)

### Steps

- Detect  
  Detect errors or anomalies

- Plan  
  Decide a fix strategy (hypothesis)

- Fix  
  Apply localized fixes

- Release  
  Deploy to production

- Monitor  
  Observe recurrence and impact



## Principles

### 1. Do not internally define “completion”

- Fix success ≠ problem solved
- Completion is determined externally



### 2. Keep fixes small and frequent

- Large fixes increase risk
- Small fixes + short loops are optimal



### 3. Use real-world signals for decisions

- Logs
- Production behavior
- Recurrence rate

External observation > internal logic



## State Model

open
→ analyzing
→ patch_ready
→ patched
→ released
→ monitoring
→ resolved (external condition)
↘ reopened (recurrence)

### Notes

- “monitoring” is a primary state
- “resolved” is time/condition-based
- “reopened” is a normal path



## Resolution Conditions (example)

- No recurrence for a defined period (e.g., 72 hours)
- Alerts below threshold
- Core functions healthy
- Optional human validation

Completion is condition-based, not declarative.



## Architecture

### Roles

- Supervisor  
  State management, planning, evaluation

- Worker  
  Fix implementation

- Gate  
  Testing and safety validation



### Loop

1. Detect
2. Supervisor: Plan
3. Worker: Fix
4. Gate: Validate
5. Release
6. Monitor
→ Loop



## Why it works

- Reduces context complexity
- Avoids infinite optimization
- Enables learning in production
- Accepts recurrence as normal



## Anti-patterns

- Trying to achieve perfect fixes
- Declaring completion internally
- Large, risky changes
- Treating recurrence as failure



## Use Cases

- Production systems
- Continuous delivery environments
- Self-healing systems
- AI agent-based development



## Summary

Not about fixing once,

but about:

“Building systems that remain stable even as they continue to break.”



## Status

PFL is an evolving practical model.

Contributions and real-world cases are welcome.



## License

MIT



## Notes

This model is not suitable for:

- Fully static systems
- Problems requiring strict completion

It is designed for:

→ Dynamic, uncertain, real-world systems



