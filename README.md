# Additional Skills Repository 

This repository is designed for Learning the EPAV Loop (Evaluate → Plan → Analyze → Validate)

> **Master AI-native, spec-driven development by combining the EPAV feedback loop with OpenCode .**

This repository serves as a list of practical skills more for developers to learn to transition from traditional "vibe coding" (ad-hoc AI prompting) to **AI-Agile Spec-Driven Development** using the **EPAV Loop**.

The included **Documentation Guard** skill included here acts as a protective boundary in AI-assisted development, prohibiting automated tools and AI agents from modifying specification documents, architectural plans, or project governance without explicit team lead approval.


## Frequently Asked Questions about EPAV Loop

### What the Knowledge Rules Are For

This repository has several kinds of guidance. They serve different purposes and should be read in the right order.

## `AGENTS.md`: project-wide working rules

`AGENTS.md` is created to be a shared contract for anyone changing the repository, including AI coding agents. It defines the technology stack, required package manager and runtime, standard commands, and other repository-specific constraints.

It is intentionally small and applies across tools. Rules here take precedence over tool-specific workflow conveniences.

How does it differ from a `README.md` file? 

Unlike human-facing READMEs, `AGENTS.md` provides AI coding agents with project-specific instructions, conventions, and operational guidelines it is read continuously by AI tools to enforce consistency. It may contain the following notes:

 - Development Setup: Commands for installing, building, and environment setup.
 - Coding Conventions: Rules for code style, naming, and file structures.
 - Testing & CI/CD: Instructions for running tests and verifying code changes.
 - Commit Guidelines: Formatting rules for commit messages and linting.
 - Project Guardrails: Custom boundaries, security constraints, and performance rules.

## Which source to use

Use the sources in this order:

1. Read `AGENTS.md` for repository-wide requirements.
2. Read the relevant `.opencode/` or `.claude/` command when invoking a tool workflow.
3. Read the relevant architecture and product documents for system behavior.
4. Read `knowledge/rules/`, `knowledge/patterns/`, and relevant retrospectives for established project lessons.
5. Update `knowledge/` when a new durable rule or pattern is discovered.

In short, `AGENTS.md` says how to work in the repository, `.opencode/` and `.claude/` say how a particular coding tool should work, and `knowledge/` preserves the project’s accumulated understanding.

#### Regarding `docs/`

Documentation forms the foundation of AI-assisted development, but allowing developers or AI agents to modify specifications without proper approval creates severe downstream drift. To prevent this, spec files should remain locked down. When ambiguous specs stall progress, developers should surface issues directly—via a call or message—to clarify requirements rather than making unapproved edits.

As developers transition into AI orchestrators, balancing strict spec control with core Agile values—like prioritizing direct collaboration over rigid documentation updates—is critical. In multi-stakeholder projects, maintaining alignment means keeping communication open while ensuring all specification changes go through team lead approval.
