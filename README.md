# Additional Skills Repository 

This repository is designed for Learning the EPAV Loop (Evaluate → Plan → Analyze → Validate)

> **Master AI-native, spec-driven development by combining the EPAV feedback loop with OpenCode .**

This repository serves as a list of practical skills more for developers to learn to transition from traditional "vibe coding" (ad-hoc AI prompting) to **AI-Agile Spec-Driven Development** using the **EPAV Loop**.

The included **Documentation Guard** skill included here acts as a protective boundary in AI-assisted development, prohibiting automated tools and AI agents from modifying specification documents, architectural plans, or project governance without explicit team lead approval.


## Frequently Asked Questions about EPAV Loop

### What the Knowledge Rules Are For

This repository has several kinds of guidance. They serve different purposes and should be read in the right order.

## `AGENTS.md`: project-wide working rules

`AGENTS.md` is the shared contract for anyone changing the repository, including AI coding agents. It defines the technology stack, required package manager and runtime, standard commands, and other repository-specific constraints.

It is intentionally small and applies across tools. Rules here take precedence over tool-specific workflow conveniences.

## `.opencode/`: OpenCode workflow and tooling

`.opencode/` contains configuration, commands, agents, skills, plugins, and checkpoints for OpenCode.

- `commands/` defines repeatable workflows such as `/evaluate`, `/plan`, `/apply`, `/validate`, and `/epav`.
- `agents/` contains focused review instructions, such as database, deployment, performance, and code review roles.
- `skills/` contains reusable procedures, including graphify and retrospective workflows.
- `plugins/` integrates OpenCode with repository tooling, such as automatic graph updates.
- `checkpoints/` stores temporary session handoff notes when a task is paused or context is compacted.

These files explain how OpenCode should work in this repository; they are not the application’s runtime behavior.

## `.claude/`: Claude Code workflow and tooling

`.claude/` provides the equivalent command and agent instructions for Claude Code. Its commands largely mirror `.opencode/`, so the same E→P→A→V development workflow can be used from either tool.

Tool-specific files may differ slightly, but they should remain consistent with `AGENTS.md`, the architecture documents, and the repository knowledge base.

## `knowledge/`: durable project knowledge

`knowledge/` is the repository’s durable memory: decisions, patterns, lessons, and rules that should survive individual sessions and tool changes.

- `knowledge/rules/` contains standing engineering rules, currently including coding standards.
- `knowledge/patterns/` records proven implementation patterns and constraints.
- `knowledge/retros/` records process decisions, discoveries, and lessons from completed work.
- `knowledge/prompts/` contains reusable prompts for development tasks.
- Top-level knowledge documents summarize broader project conventions and lessons.

When a workflow discovers a reusable constraint or better practice, it should be documented here rather than left only in an agent command or chat history.

## Which source to use

Use the sources in this order:

1. Read `AGENTS.md` for repository-wide requirements.
2. Read the relevant `.opencode/` or `.claude/` command when invoking a tool workflow.
3. Read the relevant architecture and product documents for system behavior.
4. Read `knowledge/rules/`, `knowledge/patterns/`, and relevant retrospectives for established project lessons.
5. Update `knowledge/` when a new durable rule or pattern is discovered.

In short, `AGENTS.md` says how to work in the repository, `.opencode/` and `.claude/` say how a particular coding tool should work, and `knowledge/` preserves the project’s accumulated understanding.
