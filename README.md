
# Development Principles & Standards 

## Overview
The  **Development Principles** document serves as a unified standard for code style, and development processes primarilly
targetted at Python.

**This standard is designed to be dual-purpose:**
1.  **For Human Developers:** A strict guide for code reviews, architectural decisions, and maintaining high-quality, maintainable 
codebases.
2.  **For AI Assistants:** A highly specific "system prompt" or context document for LLMs (like Gemini, GPT-4, Claude) to ensure 
generated code matches project standards immediately, minimizing rework.

## Core Philosophy
The principles prioritize **pragmatism over dogmatism**, **explicit configuration over implicit magic**, and **robustness through 
validation**. It is deliberately opinionated and should be modified to match a team's preferences.

## Key Pillars

### 1. Architecture & Design
*   **Layered Architecture:** Strict separation between Orchestration, Business Logic, and Data Access.
*   **Declarative Configuration:** Business logic and thresholds belong in schema-validated files, not hardcoded.
*   **Fail Fast:** Systems must validate configuration and data integrity immediately upon startup or ingestion.
*   **Dependency Injection:** Components receive their dependencies; they do not fetch them.

### 2. Python Code Quality
*   **Modern Python:** Logic targets **Python 3.10+**.
*   **Strict Typing:** Explicit type hints are mandatory for all function signatures.
*   **Documentation:** Google-style docstrings are required, optimized for Sphinx/MyST parsing.

### 3. AI Co-Coding Standards and Processes
Specific rules are enforced to prevent common AI generation pitfalls:
*   **No Placeholders:** AI must generate complete, functional snippets (no `// ... code here`).
*   **JSON Safety:** Strict prohibition of comments within JSON output.
*   **Truthful Presentation:** AI must explicitly flag whether a code block is a partial update or a complete file.
*   **Data-Driven Debugging:** A formalized method for fixing defects (Hypothesis $\to$ Data Collection $\to$ Analysis).
*   **Environment and Version Reconciliation:** A process to detect and handle cases where the AI model is using a different library
than the user's environment.

## Usage
* Fork and modify sections to match your style and environment.
* Modify sections rather than removing.
* Section and item numbering must be kept persistent!  This allows the user and the AI to refer to a principle number.
* When starting a new session with an AI coding assistant, paste the contents of `development_principles.md` into the context
window to prime the agent.


