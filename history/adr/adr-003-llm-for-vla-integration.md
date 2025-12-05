# ADR-003: LLM for Vision-Language-Action (VLA) Integration

> **Scope**: Document decision clusters, not individual technology choices. Group related decisions that work together (e.g., "Frontend Stack" not separate ADRs for framework, styling, deployment).

- **Status:** Accepted
- **Date:** 2025-12-04
- **Feature:** 001-physical-ai-robotics-book
- **Context:** The Vision-Language-Action (VLA) module requires an effective Large Language Model (LLM) for task planning and voice command interpretation. A balance between reliability for demonstrations and accessibility for offline labs is necessary.

## Decision

OpenAI GPT-4o API will be used for core VLA demonstrations and examples, offering high reliability and performance. For offline or resource-constrained labs, a fallback to Ollama `llama3:8b` will be provided, allowing local execution.

## Consequences

### Positive

- Provides robust and high-quality LLM capabilities for key VLA concepts using GPT-4o.
- Ensures accessibility for all readers, regardless of internet connectivity or API access, through the Ollama fallback.
- Exposes students to both cloud-based and local LLM deployment strategies.

### Negative

- Reliance on a commercial API (GPT-4o) may incur costs for readers.
- The local fallback (Ollama `llama3:8b`) might have lower performance or quality compared to GPT-4o.
- Managing two LLM approaches adds a slight layer of complexity to the book's examples.

## Alternatives Considered

- **Exclusively OpenAI GPT-4o API**: Rejected due to potential cost barriers and lack of offline accessibility for all readers.
- **Exclusively local LLaMA-3–8B (or other open-source models)**: Rejected because it might compromise the reliability and performance of some key VLA demonstrations, especially for complex tasks, and requires local setup which might be challenging for some users.
- **Groq/LM Studio**: Considered as local options, but Ollama `llama3:8b` was chosen for its ease of use and broader community support for local LLM deployment.

## References

- Feature Spec: specs/001-physical-ai-robotics-book/spec.md
- Implementation Plan: specs/001-physical-ai-robotics-book/plan.md
- Related ADRs: null
- Evaluator Evidence: null
