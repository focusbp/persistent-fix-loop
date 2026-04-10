# Persistent Fix Loop (PFL)
## A Stabilization Model for Hierarchical AI Under Imperfect Planning, Execution, and Evaluation



## Abstract

Hierarchical AI systems are commonly modeled as a linear pipeline: Plan → Execute → Evaluate → Complete.
However, in real-world production environments, this model frequently breaks down due to drift, uncertainty, and external dependencies.

This paper introduces the Persistent Fix Loop (PFL), a practical design model that replaces completion-oriented pipelines with a continuous stabilization loop.

Rather than attempting to achieve perfect planning, execution, and evaluation, PFL assumes imperfection and builds systems that remain stable through continuous observation and incremental repair.



## 1. Introduction

Hierarchical AI systems are widely used to decompose complex tasks into structured workflows.

Typical architecture:
- Planner (high-level reasoning)
- Executor (task execution)
- Evaluator (validation)

In theory, this enables reliable task completion.

In practice, however, this structure is fragile.



## 2. Problem Statement

Hierarchical AI is often described as:

Plan → Execute → Evaluate → Complete

This assumes:
- Plans remain valid during execution
- Execution follows expected paths
- Evaluation criteria are stable
- Completion can be determined internally

These assumptions rarely hold in production systems.

### 2.1 Failure Modes

1. Plan Drift  
   Plans degrade when exposed to real environments.

2. Execution Uncertainty  
   Unexpected constraints emerge during execution.

3. Evaluation Instability  
   Success criteria depend on external context.

4. Completion Ambiguity  
   Systems cannot reliably determine when a problem is “solved”.



## 3. Key Insight

The core issue is not hierarchical structure itself, but treating it as a **linear completion pipeline**.

Instead of:

Plan → Execute → Evaluate → Complete

We propose:

**Observation-driven iterative stabilization**



## 4. Persistent Fix Loop (PFL)

### 4.1 Core Model

Detect → Plan → Fix → Release → Monitor → Loop

### 4.2 Conceptual Shift

| Traditional | PFL |
||--|
| Plan = decision | Plan = hypothesis |
| Execute = completion | Fix = intervention |
| Evaluate = judgment | Monitor = observation |
| Complete | Continuous |



## 5. Design Principles

### 5.1 Planning is Provisional
Plans are hypotheses, not commitments.

### 5.2 Execution is Local
Fixes should be small, scoped, and reversible.

### 5.3 Evaluation is Observational
Resolution is determined by real-world behavior, not internal declaration.



## 6. Hierarchical AI Integration

PFL naturally integrates with hierarchical AI.

### 6.1 Roles

- Supervisor
  - Planning
  - Evaluation
  - State management

- Worker
  - Implementation
  - Local fixes

- System
  - Real-world environment

### 6.2 Loop

1. Detect issue  
2. Supervisor plans  
3. Worker applies fix  
4. System reflects change  
5. Supervisor monitors  
6. Repeat  



## 7. State Model

open  
→ analyzing  
→ patch_ready  
→ patched  
→ released  
→ monitoring  
→ resolved (external condition)  
↘ reopened (recurrence)

### Key Feature
“monitoring” is a first-class state.



## 8. Resolution Strategy

Resolution is not declared internally.

Instead, it is determined by:
- No recurrence over time
- Stable system behavior
- External validation



## 9. Advantages

- Handles uncertainty naturally
- Avoids infinite optimization
- Improves stability in production
- Enables continuous learning



## 10. Discussion

PFL represents a shift from completion-based thinking to stability-based thinking.

Rather than asking:
“Is the problem solved?”

It asks:
“Is the system stable under observation?”



## 11. Conclusion

Hierarchical AI does not fail because of its structure.

It fails because it assumes perfect completion.

PFL removes this assumption and replaces it with a continuous stabilization model.

This enables hierarchical AI to operate effectively in real-world environments.



## 12. Future Work

- Empirical validation
- Benchmarking stability vs completion models
- Integration with production systems



## License

MIT
