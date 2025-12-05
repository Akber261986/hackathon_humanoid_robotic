# Tasks: Educational Book on Physical AI & Humanoid Robotics

**Input**: Design documents from `/specs/001-physical-ai-robotics-book/`
**Prerequisites**: plan.md (required), spec.md (required for user stories)

**Tests**: Tests are included where applicable for lab verification.

**Organization**: Tasks are grouped by logical phases and user story to enable independent implementation and testing of each component.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Path Conventions

- All paths assume the Docusaurus `docs/` structure as defined in `plan.md`.

## Phase 1: Setup (Shared Infrastructure)

**Purpose**: Project initialization and basic structure for the Docusaurus site.

- [ ] T001 Initialize Docusaurus project in the repository root.
- [ ] T002 Create the `docs/` directory and subdirectories: `intro`, `module-1-ros2`, `module-2-simulation`, `module-3-isaac`, `module-4-vla`, `hardware`, `appendices`.
- [ ] T003 Configure Docusaurus `sidebars.js` to autogenerate from folder order and frontmatter `sidebar_position`.
- [ ] T004 Create `docs/intro/00-welcome.md` with initial welcome content.
- [ ] T005 Create `docs/intro/01-why-physical-ai.md` with an introduction to physical AI.
- [ ] T006 Create `docs/intro/02-learning-outcomes.md` outlining book learning objectives.
- [ ] T007 Configure basic `.gitignore` to exclude Docusaurus build artifacts and temporary files.

---

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: Core infrastructure and validation setup that MUST be complete before content creation for any module can begin.

**⚠️ CRITICAL**: No content creation for modules can begin until this phase is complete.

- [ ] T008 [P] Implement GitHub Actions workflow for CI with `docker-ros` and `nvidia-container-toolkit` for code block validation in `.github/workflows/ci.yml`.
- [ ] T009 [P] Set up a local development environment (Ubuntu 22.04 VM + RTX 4080 instance or equivalent) for content validation.
- [ ] T010 Integrate a dead-link checking tool (e.g., Lychee) into the CI pipeline in `.github/workflows/ci.yml`.
- [ ] T011 Document the content creation workflow (SpeckitPlus → Cloud Code → Docusaurus preview → GitHub Pages) in `specs/001-physical-ai-robotics-book/workflow.md`.

**Checkpoint**: Foundation ready - module content creation can now begin.

---

## Phase 3: User Story 1 - Learning Humanoid Simulation [US1] (P1) 🎯 MVP

**Goal**: A university student or early-career engineer can set up and run a basic humanoid simulation and explain embodied intelligence in robotics.

**Independent Test**: The reader can set up and run a basic humanoid simulation using provided lab examples, and demonstrate understanding of core concepts as outlined in `specs/001-physical-ai-robotics-book/spec.md`.

### Module 1: ROS 2

- [ ] T012 [P] [US1] Create `docs/module-1-ros2/00-overview.md` outlining ROS 2 concepts.
- [ ] T013 [P] [US1] Draft `docs/module-1-ros2/01-installation.md` with ROS 2 Iron installation steps.
- [ ] T014 [P] [US1] Draft `docs/module-1-ros2/02-nodes-topics-services.md` explaining core ROS 2 communication.
- [ ] T015 [P] [US1] Draft `docs/module-1-ros2/03-rclpy-bridge.md` on Python client library.
- [ ] T016 [P] [US1] Draft `docs/module-1-ros2/04-urdf-humanoid.md` on URDF for humanoids.
- [ ] T017 [US1] Create `docs/module-1-ros2/99-lab-ros2-package.md` with a reproducible ROS 2 package setup and verification steps.
- [ ] T018 [US1] Verify the `docs/module-1-ros2/99-lab-ros2-package.md` lab in the CI pipeline.

### Module 2: Simulation

- [ ] T019 [P] [US1] Create `docs/module-2-simulation/00-gazebo-basics.md` introducing Gazebo Harmonic.
- [ ] T020 [P] [US1] Draft `docs/module-2-simulation/01-urdf-to-sdf.md` on model conversion.
- [ ] T021 [P] [US1] Draft `docs/module-2-simulation/02-sensors-simulation.md` on simulating robot sensors.
- [ ] T022 [P] [US1] Draft `docs/module-2-simulation/03-unity-digital-twin.md` on Unity integration concepts.
- [ ] T023 [US1] Create `docs/module-2-simulation/99-lab-digital-twin.md` with a reproducible digital twin simulation setup and verification steps.
- [ ] T024 [US1] Verify the `docs/module-2-simulation/99-lab-digital-twin.md` lab in the CI pipeline (using AWS g5.4xlarge for simulation if necessary).

### Module 3: Isaac

- [ ] T025 [P] [US1] Create `docs/module-3-isaac/00-isaac-sim-setup.md` on NVIDIA Isaac Sim installation.
- [ ] T026 [P] [US1] Draft `docs/module-3-isaac/01-isaac-ros.md` on Isaac ROS integration.
- [ ] T027 [P] [US1] Draft `docs/module-3-isaac/02-vslam-navigation.md` on visual SLAM and navigation.
- [ ] T028 [P] [US1] Draft `docs/module-3-isaac/03-synthetic-data.md` on synthetic data generation.
- [ ] T029 [US1] Create `docs/module-3-isaac/99-lab-perception-pipeline.md` with a reproducible perception pipeline lab and verification steps.
- [ ] T030 [US1] Verify the `docs/module-3-isaac/99-lab-perception-pipeline.md` lab in the CI pipeline (using AWS g5.4xlarge for simulation).

### Module 4: VLA

- [ ] T031 [P] [US1] Create `docs/module-4-vla/00-vision-language-action.md` on VLA fundamentals (GPT-4o API + Ollama `llama3:8b` fallback).
- [ ] T032 [P] [US1] Draft `docs/module-4-vla/01-whisper-voice-commands.md` on voice command integration.
- [ ] T033 [P] [US1] Draft `docs/module-4-vla/02-llm-task-planning.md` on LLM-based task planning.
- [ ] T034 [P] [US1] Draft `docs/module-4-vla/03-capstone-overview.md` with a capstone project overview.
- [ ] T035 [P] [US1] Create `docs/module-4-vla/capstone/01-full-stack.md` with the full-stack capstone implementation.
- [ ] T036 [US1] Create `docs/module-4-vla/capstone/02-deployment-jetson.md` for Jetson deployment details.
- [ ] T037 [US1] Verify all VLA labs and capstone in the CI pipeline.
- [ ] T038 [US1] Ensure the final capstone runs end-to-end on Jetson Orin Nano 8GB + RealSense D435i.

**Checkpoint**: All core modules and labs are drafted, and the reader can set up and run a basic humanoid simulation.

---

## Final Phase: Polish & Cross-Cutting Concerns

**Purpose**: Final review, quality checks, and deployment preparation.

- [ ] T039 [P] Draft `docs/hardware/00-workstation-specs.md` detailing recommended workstation specifications.
- [ ] T040 [P] Draft `docs/hardware/01-jetson-kit.md` detailing Jetson setup and considerations.
- [ ] T041 [P] Draft `docs/hardware/02-robot-options.md` on potential robot platforms and integration notes.
- [ ] T042 [P] Draft `docs/appendices/glossary.md` with key terms and definitions.
- [ ] T043 [P] Draft `docs/appendices/resources.md` with additional learning resources and references.
- [ ] T044 Review all modules for content quality, clarity, and adherence to specified word counts (2000-4000 words per module, 10,000-20,000 total).
- [ ] T045 Run dead-link checker across the entire Docusaurus project after content completion.
- [ ] T046 Conduct reader success test: "Can a student with zero ROS experience run Module 1 Lab in <2 hours?" and document results.
- [ ] T047 Deploy the Docusaurus site to GitHub Pages.
- [ ] T048 Implement PDF export functionality via a Docusaurus PDF plugin.

---

## Dependencies & Execution Order

### Phase Dependencies

- **Phase 1 (Setup)**: No dependencies - can start immediately.
- **Phase 2 (Foundational)**: Depends on Phase 1 completion - BLOCKS all User Story phases.
- **Phase 3 (User Story 1)**: Depends on Phase 2 completion. Modules within this phase can be approached in parallel for drafting, but lab creation and verification depend on the drafting of their respective module sections.
- **Final Phase (Polish & Cross-Cutting Concerns)**: Depends on Phase 3 completion.

### User Story Dependencies

- **User Story 1 (P1)**: Can start after Foundational (Phase 2) - No dependencies on other stories (as there's only one primary story).

### Within Each User Story (Module Development)

- Drafting of module sections (e.g., T012-T016 for ROS 2) can be done in parallel.
- Lab creation (e.g., T017) depends on the completion of the related drafting tasks within that module.
- Lab verification (e.g., T018) depends on the creation of the lab (T017).

### Parallel Opportunities

- All Foundational tasks (T008, T009, T010) marked [P] can run in parallel.
- Drafting tasks within a module (e.g., T012-T016) can be run in parallel.
- Drafting tasks for `hardware/` and `appendices/` sections (T039-T043) can run in parallel.

---

## Parallel Example: Module 1 Content Drafting

```bash
# Launch drafting for Module 1 sections in parallel:
Task: "Create docs/module-1-ros2/00-overview.md outlining ROS 2 concepts"
Task: "Draft docs/module-1-ros2/01-installation.md with ROS 2 Iron installation steps"
Task: "Draft docs/module-1-ros2/02-nodes-topics-services.md explaining core ROS 2 communication"
# ... and so on for other drafting tasks in Module 1
```

---

## Implementation Strategy

### MVP First (Module 1 Focus)

1. Complete Phase 1: Setup.
2. Complete Phase 2: Foundational (CRITICAL - blocks all module content).
3. Focus on completing Module 1 (ROS 2) including drafting, lab creation, and verification.
4. **STOP and VALIDATE**: Ensure the reader can complete Module 1 and run its lab successfully.

### Incremental Delivery

1. Complete Setup + Foundational → Foundation ready.
2. Complete Module 1 → Test independently → Ready for review/demo.
3. Proceed with Module 2, then 3, then 4, ensuring each module is independently testable and integrates correctly.
4. Complete Final Phase for polish and deployment.

### Parallel Team Strategy

With multiple contributors:

1. Team completes Setup + Foundational together.
2. Once Foundational is done:
   - Contributor A: Focus on Module 1 (drafting + labs).
   - Contributor B: Focus on Module 2 (drafting + labs).
   - Contributor C: Focus on Module 3 (drafting + labs).
   - Contributor D: Focus on Module 4 (drafting + labs).
   - Contributor E: Work on Hardware and Appendices concurrently with modules.
3. All module content and labs are developed and verified, integrating during the Final Phase.

---

## Notes

- [P] tasks = different files, no dependencies
- [Story] label maps task to specific user story for traceability
- Each module should be independently completable and testable, contributing to the overall user story.
- Verify labs and code blocks in CI.
- Commit after each task or logical group of tasks.
- Stop at any checkpoint to validate progress independently.
- Avoid: vague tasks, same file conflicts, cross-module dependencies that break independent development.
