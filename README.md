# Codebase Discovery Skill

An advanced agent skill that performs a comprehensive static and architectural analysis of any given codebase.

## Overview
This skill instructs autonomous AI agents on how to systematically analyze a repository. It covers everything from discovering core domain models and API surfaces to identifying complex algorithms, testing strategies, and potential security vulnerabilities. The result is a high signal-to-noise architectural report including Mermaid.js diagrams and technical debt analysis.

## Directory Structure
- `SKILL.md`: The primary agent instructions, execution steps, and metadata.
- `assets/templates/reports/full-report-template.md`: The strict markdown schema the agent uses to format its final architectural report.

## How to Trigger
You can invoke this skill by asking your AI assistant to perform a full analysis or focus on a specific sub-section:
- "Analyze this codebase"
- "Generate a Summary for this codebase"
- "Generate an Architecture Diagram for this codebase"
- "Analyze the Domain Model & Core Entities of this codebase"
- "Analyze the API Surface & Integrations of this codebase"
- "Analyze Algorithms, Concurrency & Data Structures of this codebase"
- "Evaluate Code Quality & Test Coverage for this codebase"
- "Analyze Security & Vulnerabilities of this codebase"
- "Identify Red Flags and provide Recommendations for this codebase"
