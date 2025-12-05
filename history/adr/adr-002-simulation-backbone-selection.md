# ADR-002: Simulation Backbone Selection

> **Scope**: Document decision clusters, not individual technology choices. Group related decisions that work together (e.g., "Frontend Stack" not separate ADRs for framework, styling, deployment).

- **Status:** Accepted
- **Date:** 2025-12-04
- **Feature:** 001-physical-ai-robotics-book
- **Context:** The educational book's practical labs and examples rely heavily on a robust and modern robotics simulation environment. Compatibility with NVIDIA Isaac Sim is a critical requirement.

## Decision

Gazebo Harmonic has been chosen as the simulation backbone. This decision is driven by its requirement for integration with the newest NVIDIA Isaac Sim, ensuring access to cutting-edge simulation capabilities.

## Consequences

### Positive

- Seamless integration with the latest NVIDIA Isaac Sim features and improvements.
- Provides students with experience using a modern and actively developed simulation platform.
- Access to advanced simulation capabilities necessary for complex humanoid robotics scenarios.

### Negative

- May have a steeper learning curve for users familiar with older Gazebo Classic versions.
- Requires a system capable of running Gazebo Harmonic and Isaac Sim, potentially higher hardware requirements.

## Alternatives Considered

- **Gazebo Classic**: An older, widely used simulation environment. Rejected due to lack of direct compatibility with the newest NVIDIA Isaac Sim and potentially fewer advanced features.
- **Ignition/Gazebo (other versions)**: Other versions of Gazebo Ignition were considered but Gazebo Harmonic was chosen specifically for its compatibility with the *newest* Isaac Sim.

## References

- Feature Spec: specs/001-physical-ai-robotics-book/spec.md
- Implementation Plan: specs/001-physical-ai-robotics-book/plan.md
- Related ADRs: null
- Evaluator Evidence: null
