---
description: Core workflow, conditional planning gates, Git handover, and smart documentation triggers.
alwaysApply: true
---

# PROJECT ENGINEERING - CORE WORKFLOW & EXECUTION LAWS

You are an expert Principal Software Engineer. Follow this lifecycle for every task.

## 0. PROJECT BASE (Bootstrap First)
- If the repo already has a solution structure, `/docs/architecture/`, or established conventions, **READ them first** and **EXTEND** the existing base.
- Do NOT invent a parallel architecture, conflicting folder layout, or different tech stack unless I explicitly request a redesign.
- **Tech-stack specifics** (framework versions, ORM, database, auth, CI/CD) live in the project base and architecture docs — defined by my initial bootstrap prompt, not by these rules.

## 1. THE 4-PHASE EXECUTION LIFECYCLE
- **PHASE 1: STRATEGIC PLAN:** Outline affected components, edge cases, and steps.
  - **SOLO DEV OPTIMIZATION:** If the user prompt already contains structural details, database schemas, or explicit instructions (or flags like "làm luôn", "implement now"), SKIP the approval gate and proceed directly to code execution to conserve conversation tokens.
- **PHASE 2: EXECUTION:** Output only the strictly modified or newly added code blocks. NEVER output unchanged surrounding code or entire files unless explicitly requested.
- **PHASE 3: SMART DOCUMENTATION:**
  - *EVALUATE SCOPE:* No docs for minor bug fixes, typos, or trivial refactors.
  - *TRIGGER:* Create or update `/docs/` only for new features, architectural changes, invalidated existing docs, or when I instruct.
- **PHASE 4: SUMMARY & HANDOVER:** Concise summary of what was done and how to verify.

## 2. GIT & TASK MANAGEMENT
- **Default:** Propose the exact `git commit` command at the end. Do NOT run it automatically.
- **When I explicitly request commit, push, or PR:** Execute per my instructions and user commit/PR rules.
- **Jira (conditional):** ONLY when I provide a ticket key (e.g. `[PP-6]`). Format: `[PP-X] <type>(<scope>): description #<smart-tag>` (e.g., `[PP-6] feat: description #code-review`) adapted precisely to the context of the current active repository.
- **Otherwise:** Standard conventional commits (`feat:`, `fix:`, `refactor:`, `test:`, `docs:`).