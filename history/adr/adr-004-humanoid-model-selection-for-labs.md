# ADR-004: Humanoid Model Selection for Labs

> **Scope**: Document decision clusters, not individual technology choices. Group related decisions that work together (e.g., "Frontend Stack" not separate ADRs for framework, styling, deployment).

- **Status:** Accepted
- **Date:** 2025-12-04
- **Feature:** 001-physical-ai-robotics-book
- **Context:** The educational book requires open and accessible humanoid robot models for simulation and practical labs to ensure all readers can reproduce the examples without proprietary hardware or licensing.

## Decision

Open-source assets will be utilized for humanoid models, specifically Unitree G1/G1-EDU USD assets and NASA Valkyrie URDF. This ensures broad accessibility and reproducibility of all simulation labs.

## Consequences

### Positive

- Maximizes accessibility for all readers, as no special licenses or proprietary hardware are required.
- Promotes a focus on the AI and robotics concepts rather than specific commercial hardware.
- Leverages well-documented and community-supported open-source models.

### Negative

- May not perfectly replicate the most advanced commercial humanoid robot capabilities, potentially limiting some highly specialized examples.
- The visual fidelity of open-source models might be lower than highly-detailed commercial counterparts.

## Alternatives Considered

- **Tesla Bot (closed)**: Rejected due to proprietary nature, lack of public access to models, and inability for readers to reproduce labs.
- **Figure 01 (closed)**: Rejected for the same reasons as Tesla Bot.
- **Other proprietary humanoid models**: Generally rejected to maintain open access and reproducibility.

## References

- Feature Spec: specs/001-physical-ai-robotics-book/spec.md
- Implementation Plan: specs/001-physical-ai-robotics-book/plan.md
- Related ADRs: null
- Evaluator Evidence: null
