# Content Creation Workflow

This document outlines the workflow for creating and publishing content for the "Physical AI & Humanoid Robotics" educational book.

## 1. SpeckitPlus (Planning & Task Management)

*   **Purpose:** Define feature specifications (`spec.md`), architectural plans (`plan.md`), and detailed implementation tasks (`tasks.md`).
*   **Tools:** SpeckitPlus CLI commands (`/sp.specify`, `/sp.plan`, `/sp.tasks`).
*   **Process:**
    1.  Start with a high-level feature description.
    2.  Use `/sp.specify` to generate or refine `spec.md` with user stories and requirements.
    3.  Use `/sp.plan` to create `plan.md`, detailing the technical architecture, project structure, and key decisions.
    4.  Use `/sp.tasks` to break down the plan into granular, testable tasks in `tasks.md`, including file paths and dependencies.

## 2. Claude Code (Content Drafting & Implementation)

*   **Purpose:** Implement tasks defined in `tasks.md`, including drafting markdown content, configuring Docusaurus, and setting up CI/CD.
*   **Tools:** Claude Code agent (using `Read`, `Write`, `Edit`, `Bash` tools, and various agent types).
*   **Process:**
    1.  The Claude Code agent reads `tasks.md` and `plan.md` to understand the implementation scope.
    2.  For content drafting tasks (e.g., creating `.md` files in `docs/`),
        *   Claude Code drafts the initial content based on the feature specification.
        *   User reviews and refines the drafted content.
    3.  For configuration and infrastructure tasks (e.g., Docusaurus setup, CI/CD),
        *   Claude Code executes `Bash` commands and `Write`/`Edit` operations.
    4.  The agent uses the TodoWrite tool to track progress, marking tasks as `in_progress` and `completed`.

## 3. Docusaurus Local Preview (Content Review)

*   **Purpose:** Locally preview the rendered Docusaurus site to ensure content accuracy, formatting, and navigation.
*   **Tools:** `npm start` (from Docusaurus project root).
*   **Process:**
    1.  After content drafting, run `npm start` in the terminal.
    2.  Open the provided local URL (e.g., `http://localhost:3000`) in a web browser.
    3.  Review the rendered markdown, verify links, check image displays, and ensure correct sidebar navigation.
    4.  Make any necessary adjustments to the markdown files.

## 4. GitHub Pages (Deployment)

*   **Purpose:** Publish the Docusaurus site as static content to GitHub Pages for public access.
*   **Tools:** GitHub Actions (configured in `.github/workflows/ci.yml`), `npm run deploy`.
*   **Process:**
    1.  Push changes to the main branch (or a configured deployment branch).
    2.  The GitHub Actions CI pipeline (configured in T008) will automatically:
        *   Build the Docusaurus site (`npm run build`).
        *   Run dead-link checks (`lycheeverse/lychee-action`).
        *   Potentially run code block validation (e.g., ROS 2 commands in Docker).
    3.  If all checks pass, the workflow will trigger the deployment to GitHub Pages (e.g., using `peaceiris/actions-gh-pages@v3`).
    4.  The book will be accessible via the GitHub Pages URL (e.g., `https://<username>.github.io/<repository-name>/`).
