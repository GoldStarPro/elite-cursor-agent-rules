# Universal Cursor Rules for Clean Architecture Projects

A curated collection of high-density Cursor AI Agent rules (`.mdc`) tailored for Clean Architecture backends and modern component-driven frontends. Built specifically to minimize token usage, prevent context drifting, and enforce strict enterprise-grade engineering discipline.

## 🚀 How to Install in Cursor

Cursor now supports project-specific rules via `.mdc` files inside the `.cursor/rules/` directory.

1. In the root directory of your project (Backend or Frontend), create a folder named `.cursor`:
   ```bash
   mkdir -p .cursor/rules
   ```

2. Copy the corresponding `.mdc` files from this repository into that folder based on your stack:

   * **For Backend projects:** Copy `01_core_workflow.mdc`, `02_documentation_standards.mdc`, and `03_backend_clean_architecture.mdc`.
   * **For Frontend projects:** Copy `01_core_workflow.mdc`, `02_documentation_standards.mdc`, and `03_frontend_architecture.mdc`.

3. Restart your Cursor IDE or open a new Chat window. Cursor will automatically detect and apply the rules based on the `globs` defined in the frontmatter.

---

## 🛠️ Global vs Project-Specific Rules

* **`01_core_workflow.mdc`**: Controls the AI planning and code execution lifecycle (Always Apply).
* **`02_documentation_standards.mdc`**: Enforces high-density system documentation in the `/docs` folder.
* **`03_*_architecture.mdc`**: Context-aware architecture guardrails triggered automatically by file extensions.