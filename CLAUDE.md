# Project: Meditations App

## Context

- Requirements and briefs: `local-only/clients/`
- Roadmap: `tracked/docs/roadmap.md`
- Engineering standards: `local-only/PROJECT_STANDARDS.md`
- Quality gates: `local-only/QUALITY_GATES.md`

## Project Start

For new projects or major initiatives, follow the protocol in `local-only/INITIATE_PROJECT.md`.

## Skill System

Workflow skills are available in `local-only/skills/`.
A compact index with descriptions and trigger contexts is in `local-only/skills/INDEX.md`.

### Automatic Skill Selection

Before starting any task, read `local-only/skills/INDEX.md` and check if a skill matches the current task. If yes, read its SKILL.md and follow the workflow.

Common mappings:
- Bug or error → `superpowers:systematic-debugging`
- Complex multi-step task → `planning-with-files`
- Before marking task as done → `superpowers:verification-before-completion`
- Refactoring or improvement → `kaizen`
- Writing tests → `superpowers:test-driven-development` or `testing-patterns`
- Security-relevant changes → `pentest-checklist`
- UI/prototype work → `ui-prototyping-design-system`
- Git commit/push → `git-pushing`

If no skill matches, proceed without one.

## Rules

- Never commit `local-only/` to the project repository
- Update `tracked/docs/roadmap.md` when phase or scope changes materially
- Read existing code before modifying it
- Prefer targeted fixes over broad rewrites
