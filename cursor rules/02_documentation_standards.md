---
description: Documentation organization, hybrid language policy, adaptive structural standards, and visual formatting.
globs: "**/docs/**/*,**/testing/**/*"
---

# PROJECT ENGINEERING - DOCUMENTATION & TESTING STANDARDS

## 0. SOURCE OF TRUTH
- Stack, layer layout are defined in the project bootstrap.
- Each major topic should be self-contained: a reader can understand theory, context, and practice from that file alone without jumping across many scattered files.

## 1. HYBRID LANGUAGE POLICY
- **Vietnamese:** Used for deep-dive docs, business workflows, structural rationales, and architectural "WHY". Keep technical engineering terms in English.
- **English:** Used for lightweight READMEs, API specs/contracts, config/deployment checklists, and brief component descriptions.

## 2. DIRECTORY STRUCTURE & INTOLERANCE FOR DISORDER
- Strictly categorize all documentation under the `/docs/` root (e.g., `/docs/api`, `/docs/features`, `/docs/architecture`, `/docs/database`, etc).
- **README Rule:** Every subfolder inside `/docs/` MUST contain a `README.md` acting as a clean, compact index — summarizing what each consolidated file covers and its purpose. It must NOT become a confusing maze of micro-links.
- **No Loose Files:** Loose `.md` files are strictly forbidden in the project root or source code directories (except for the main repository `README.md`).
- **API Collections:** Store `.json` Postman or HTTP collections inside `/testing/postman/`, completely isolated from markdown conceptual documentation.

## 3. STRUCTURAL DOCUMENTATION STANDARDS

Documentation must serve as an authoritative, high-density production reference that prevents knowledge fragmentation.

### A. CONSOLIDATED OVER FRAGMENTED (Anti-Scattering)
- **One authoritative file per major topic.** Example: Clean Architecture belongs to ONE single file (`clean-architecture.md`) covering all layers and concepts — DO NOT split into multiple micro-files like `domain-layer.md` or `application-layer.md`.
- **Minimize Link-Hopping:** Group deeply related concepts under clear headings within the same document rather than forcing the reader to jump through chains of external files.

### B. ADAPTIVE FILE SIZE & INTERNAL DENSITY
- **No Forced Limits:** Let the structural complexity of the feature dictate the length. Avoid artificial padding or forced truncation.
- **Organize Within:** Rely strictly on a clean hierarchy of Markdown headings (`##`, `###`) to separate sub-topics within the authoritative file. Keep it dense, structured, and technically accurate.

### C. CONCEPTUAL STRUCTURAL BLUEPRINT (Beginner-Friendly Guide)
The components below serve as a reference framework to ensure documents maintain academic depth while remaining accessible to a beginner. The exact layout can adapt flexibly based on the topic, but the content must aim to cover these core analytical layers when building deep-dive files:
- **Context & Intent:** Why does this project implement this feature/pattern? What problem does it solve?
- **Core Concepts:** Clear conceptual definitions (in Vietnamese, keeping English tech keywords).
- **Project Application:** Real folder paths, class boundaries, or specific implementations in this codebase.
- **Step-by-Step Practice/Verification:** Clear walkthrough or testing flow to independently verify the setup.
- **Trade-offs & Quick Recap:** Clear takeaways, pros/cons, or mental models for long-term retention.

### D. ADAPTIVE VISUAL FORMATTING (Tables, Mermaid & ASCII)
- **Markdown Tables:** Highly encouraged for architectural comparisons, trade-off analyses, database field mappings, and HTTP status code specifications.
- **Pragmatic Diagramming (ASCII vs. Mermaid):**
  - **Clean ASCII Text:** Perfectly acceptable and preferred for simple hierarchical structures, folder trees, or straightforward linear processes where instant readability without rendering dependencies is needed.
  - **Mermaid.js Diagrams:** Reserved for complex multi-layered architectures, relational ERD mappings, or intricate sequential API flows where ASCII would become messy or distorted.
  - **Mermaid Guardrail:** When using Mermaid, strictly adhere to valid syntax and quote labels containing spaces/special characters (e.g., `Id["User Name"]`). Always initiate with `%%{init: {'theme': 'neutral'}}%%` to guarantee cross-theme visual compatibility.