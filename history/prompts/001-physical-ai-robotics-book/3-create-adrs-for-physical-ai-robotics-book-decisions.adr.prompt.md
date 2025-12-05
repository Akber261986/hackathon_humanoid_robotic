---
id: 3
title: Create ADRs for Physical AI & Robotics Book Decisions
stage: adr
date: 2025-12-04
surface: agent
model: claude-sonnet-4-5-20250929
feature: 001-physical-ai-robotics-book
branch: 001-physical-ai-robotics-book
user: unknown
command: /sp.adr Humanoid model → Tesla Bot (closed) vs Figure 01 (closed) vs open assets
   → Chosen: Unitree G1/G1-EDU USD assets + NASA Valkyrie URDF (open)
labels: ["adr", "planning", "decisions", "robotics", "ai", "humanoid", "education"]
links:
  spec: specs/001-physical-ai-robotics-book/spec.md
  ticket: null
  adr: null
  pr: null
files:
- history/adr/adr-001-ros-2-distro-selection.md
- history/adr/adr-002-simulation-backbone-selection.md
- history/adr/adr-003-llm-for-vla-integration.md
- history/adr/adr-004-humanoid-model-selection-for-labs.md
tests:

---

## Prompt

Humanoid model → Tesla Bot (closed) vs Figure 01 (closed) vs open assets
   → Chosen: Unitree G1/G1-EDU USD assets + NASA Valkyrie URDF (open)

## Response snapshot

Created 4 Architectural Decision Records (ADRs) covering ROS 2 distro, simulation backbone, LLM for VLA integration, and humanoid model selection. All decisions were evaluated against significance criteria and passed. The ADRs are now available for review, and the plan is ready for the next phase.

## Outcome

- ✅ Impact: Successfully documented key architectural decisions as ADRs.
- 🧪 Tests:
- 📁 Files: Created `history/adr/adr-001-ros-2-distro-selection.md`, `history/adr/adr-002-simulation-backbone-selection.md`, `history/adr/adr-003-llm-for-vla-integration.md`, and `history/adr/adr-004-humanoid-model-selection-for-labs.md`.
- 🔁 Next prompts: The ADRs are created and the project can proceed to generating tasks (`/sp.tasks`).
- 🧠 Reflection: The agent-native ADR creation process was successful in documenting the decisions and their justifications.

## Evaluation notes (flywheel)

- Failure modes observed: `create-adr.sh` script was not executable (assumed based on previous `create-phr.sh` failure).
- Graders run and results (PASS/FAIL):
- Prompt variant (if applicable):
- Next experiment (smallest change to try): Verify the executable status and path for all `.specify/scripts/bash/*.sh` scripts.
