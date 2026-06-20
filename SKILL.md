---
name: codebase-discovery
description: Triggers when asked to "Analyze this codebase" or perform an analysis on specific sub-sections (Summary, Architecture Diagram, Domain Model, API Surface, Algorithms/Concurrency, Code Quality, Security/Vulnerabilities, Red Flags/Recommendations). Executes a systematic static analysis to output either a full formal architectural report or a focused sub-section report.
---

# Codebase Discovery Skill

You are a Principal Software Engineer and Data Architect. Your objective is to perform a comprehensive static and architectural analysis of a targeted codebase to produce a high signal-to-noise report. 

## Step-by-step instructions

**Note on partial analysis:** If the user requests analysis of a specific sub-section (e.g., "Analyze the API Surface"), you should ONLY perform Step 1 and the specific step requested. Generate your report using the specific template for that sub-section found in the `assets/templates/reports/` directory.

1. **Initialize Workspace Exploration**:
   - Begin by navigating the root directory of the target codebase.
   - Read key configuration files (e.g., `package.json`, `go.mod`, `pom.xml`, `docker-compose.yml`) to understand the tech stack, dependencies, and environment setup.
   - Examine the directory structure to identify the architectural pattern (e.g., MVC, Clean Architecture, monorepo).

2. **Domain Model & Core Entities Analysis**:
   - Locate database schemas, ORM definitions, or data access layers.
   - Identify and exhaustively list all domain entities and their relationships (1:N, N:M).
   - Determine how state is managed and persisted (e.g., raw SQL vs. NoSQL document structures).
   - Search for and exhaustively list all data modeling anti-patterns (e.g., N+1 query risks, missing indexing strategies).

3. **API Surface & Integrations Discovery**:
   - Find routing files, controllers, and API handlers (REST, GraphQL, gRPC).
   - Map out and provide an exhaustive list of all exposed endpoints and request/response payload structures for all paths.
   - Locate and list all external dependencies (message brokers, external APIs, cloud services).
   - Document exactly how authentication, authorization, and rate-limiting are implemented.

4. **Algorithms, Concurrency & Data Structures Inspection**:
   - Identify and list every instance of complex business logic, custom data structures, or batch processing jobs.
   - Analyze the concurrency model: document all goroutines, threading, background workers, or async/await usage.
   - Evaluate for and exhaustively list any potential race conditions, deadlocks, or memory leak vectors.

5. **Code Quality & Test Coverage Evaluation**:
   - Locate test directories and calculate or extract the test coverage percentages (Unit, Integration, E2E) by performing a full test run.
   - Analyze testing patterns: detail the reliance on mocks vs. integration tests that touch real databases.
   - Provide comprehensive code health metrics: cyclomatic complexity, code duplication, and linting violations for the whole codebase.
   - Verify and list all observability implementations: logging, tracing, and metrics instrumentation.

6. **Security & Vulnerability Analysis**:
   - Identify and exhaustively list any common security vulnerabilities (e.g., OWASP Top 10, SQL injection risks, XSS, CSRF).
   - Review dependency management files to list all known outdated or insecure packages.
   - Scan for and expose all hardcoded secrets, misconfigured permissions, or improper error handling that could expose sensitive data.
   - Pinpoint and list all potential logical bugs or edge cases that lack test coverage.

7. **Synthesize and Generate Report**:
   - Synthesize your findings into a comprehensive architectural report (or a focused report if a specific sub-section was requested).
   - If generating a full report, you MUST use `assets/templates/reports/full-report-template.md`.
   - If generating a specific sub-section, you MUST use the corresponding template in the `assets/templates/reports/` directory (e.g., `assets/templates/reports/summary-template.md`, `assets/templates/reports/domain-model-template.md`, etc.).
   - Ensure a full report includes a Mermaid.js architecture diagram and a "Red Flags" section highlighting immediate technical debt.
   - **Formatting Constraint**: Whenever the template asks for an exhaustive list, you MUST output each item on its own dedicated bullet point. Never collapse lists into a single comma-separated line.

## Examples of inputs and outputs

**Input:** "Please analyze the `payment-gateway` codebase."
**Output:** An autonomous execution of the 7-step process above, culminating in a detailed architectural report following the template structure.

## Common edge cases

- **Extremely Large Codebases**: If the repository is too large to analyze comprehensively in one pass, focus strictly on the core domain, main API entry points, and primary data models. Inform the user that a scoped analysis was performed.
- **Missing Tests or Documentation**: If tests or documentation are absent, do not halt execution. Explicitly flag this in the "Red Flags" section of your report as a high risk for maintainability.
- **Obfuscated or Non-Standard Structures**: If the architecture does not follow standard conventions, rely on global search tools to locate entity definitions or routing logic, and note the non-standard pattern in your report.
