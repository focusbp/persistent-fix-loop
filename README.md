# Persistent Fix Loop (PFL)
## A Stabilization Model for Hierarchical AI Systems



## Abstract

Hierarchical AI systems are commonly modeled as a linear pipeline: Plan → Execute → Evaluate → Complete.  
However, in real-world environments, this model frequently breaks down due to uncertainty, drift, and external dependencies.

This paper introduces the Persistent Fix Loop (PFL), a practical design model that replaces completion-oriented pipelines with a continuous stabilization loop.

Rather than attempting to achieve perfect planning, execution, and evaluation, PFL assumes imperfection and builds systems that remain stable through continuous observation and incremental repair.



## 1. Introduction

Hierarchical AI systems decompose complex tasks into structured workflows consisting of planning, execution, and evaluation.

While theoretically sound, these systems often fail in production due to the inability to maintain alignment between plan, execution, and outcome.

This paper proposes a shift from completion-based thinking to stabilization-based system design.



## 2. Problem Statement

Hierarchical AI is often represented as:

Plan → Execute → Evaluate → Complete

This assumes:

- Plans remain valid during execution  
- Execution behaves as expected  
- Evaluation criteria are stable  
- Completion can be determined internally  

In practice, these assumptions do not hold.

### 2.1 Failure Modes

- Plan Drift: Plans degrade in real environments  
- Execution Uncertainty: Unexpected constraints emerge  
- Evaluation Instability: Success depends on external context  
- Completion Ambiguity: Systems cannot determine when a task is truly finished  



## 3. Key Insight

The core issue is not hierarchical structure itself, but treating it as a linear pipeline.

Instead, real-world systems require:

**Observation-driven iterative stabilization**



## 4. Persistent Fix Loop (PFL)

### 4.1 Core Model

Detect → Plan → Fix → Release → Monitor → Loop

### 4.2 Conceptual Shift

| Traditional              | PFL                    |
|:-------------------------|:----------------------|
| Plan = decision          | Plan = hypothesis      |
| Execute = completion     | Fix = intervention     |
| Evaluate = judgment      | Monitor = observation  |
| Complete                 | Continuous             |



## 5. Design Principles

### 5.1 Planning is Provisional
Plans are hypotheses, not commitments.

### 5.2 Execution is Local
Fixes should be small, scoped, and reversible.

### 5.3 Evaluation is Observational
Resolution is determined by real-world behavior, not internal declaration.



## 6. Hierarchical AI Integration

PFL naturally integrates with hierarchical AI systems.

### 6.1 Roles

- Supervisor  
  - Planning  
  - Evaluation  
  - State management  

- Worker  
  - Implementation  
  - Local fixes  

- System  
  - Production environment  

### 6.2 Loop

1. Detect issue  
2. Supervisor plans  
3. Worker applies fix  
4. System reflects change  
5. Supervisor monitors  
6. Repeat  



## 7. State Model

open  
- analyzing  
  → patch_ready  
  → patched  
  → released  
  → monitoring  
  → resolved (external condition)  
  → reopened (recurrence)



## 8. Resolution Strategy

A problem is not considered resolved when a fix is applied.

Instead, resolution is determined by:

- No recurrence over time (e.g., 72 hours)  
- Stable system behavior  
- External validation  



## 9. Advantages

- Handles uncertainty naturally  
- Avoids infinite optimization  
- Improves production stability  
- Enables continuous learning  



## 10. Discussion

PFL represents a shift:

From:
- Completion-based systems

To:
- Stability-based systems

The key question changes from:

“Is the problem solved?”

To:

“Is the system stable under observation?”



## 11. Conclusion

Hierarchical AI does not fail because of its structure.

It fails because it assumes perfect completion.

PFL removes this assumption and replaces it with a continuous stabilization loop, enabling reliable operation in real-world systems.



## 12. Future Work

- Empirical validation  
- Benchmarking stability vs completion models  
- Integration with production systems  



## License

MIT
