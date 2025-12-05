# ADR-001: ROS 2 Distro Selection

> **Scope**: Document decision clusters, not individual technology choices. Group related decisions that work together (e.g., "Frontend Stack" not separate ADRs for framework, styling, deployment).

- **Status:** Accepted
- **Date:** 2025-12-04
- **Feature:** 001-physical-ai-robotics-book
- **Context:** The educational book requires a stable ROS 2 distribution that ensures compatibility and long-term support, particularly with NVIDIA Isaac ROS, which is a core component of the book's practical labs.

## Decision

ROS 2 Iron has been chosen as the primary distribution due to its optimal long-term support overlap with NVIDIA Isaac ROS (2024–2025 releases). This ensures the reproducibility and relevance of the book's content and labs.

## Consequences

### Positive

- Ensures maximum compatibility with NVIDIA Isaac ROS versions expected to be prevalent during the book's lifecycle.
- Provides a stable development environment for students with access to up-to-date features and bug fixes.
- Simplifies environment setup and reduces potential compatibility issues for readers.

### Negative

- May require readers to use a specific operating system (e.g., Ubuntu 22.04 LTS) to match Iron's primary target.
- Potential for future migration if newer Isaac ROS versions shift focus to a different ROS 2 distribution.

## Alternatives Considered

- **ROS 2 Humble**: An older LTS release. Rejected because its support window might not align as well with the target Isaac ROS versions for 2024-2025, potentially leading to outdated examples faster.
- **ROS 2 Jazzy**: A newer, non-LTS release. Rejected due to potentially less stability and shorter support window, which could lead to more frequent updates and broken examples for readers.

## References

- Feature Spec: specs/001-physical-ai-robotics-book/spec.md
- Implementation Plan: specs/001-physical-ai-robotics-book/plan.md
- Related ADRs: null
- Evaluator Evidence: null
