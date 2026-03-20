# .github

Organization-wide default community health files for **LifeTeachUs**.

This repository provides the default issue templates and pull request template that appear
across all repositories in the organization that do not define their own.
Templates are optimized to support **AI-assisted engineering workflows** using Claude Code,
GitHub Projects, and Codespaces — helping engineers create well-scoped, high-quality tasks
that an AI agent can implement reliably.

---

## Issue Templates

Each template is a GitHub Issue Form that collects structured, explicit information.
Required fields, dropdowns, and checkboxes reduce ambiguity and keep tasks focused.

| Template | Label | Purpose |
|---|---|---|
| **storybook** | `storybook`, `ai-task` | Create or improve Storybook stories for a component. Use when adding visual coverage for a new or existing UI component. |
| **component-test** | `component-test`, `ai-task` | Add or improve isolated unit tests for a single component, hook, or utility. Scope is limited to one module. |
| **integration-test** | `integration-test`, `ai-task` | Add tests that cover a complete feature flow across multiple components or services. Use when unit tests are insufficient. |
| **e2e-test** | `e2e-test`, `ai-task` | Add end-to-end tests for a full user journey through the running application. Targets Playwright, Cypress, or Detox. |
| **refactor** | `refactor`, `ai-task` | Improve code structure, readability, or maintainability without changing runtime behavior. Requires an explicit behavior contract. |
| **tech-migration** | `tech-migration`, `ai-task` | Scope a single incremental step toward a larger technical migration (e.g. monorepo prep, shared package extraction, import harmonization). |
| **tracking** | `tracking`, `ai-task` | Add or improve product analytics event tracking for a feature area. Vendor-neutral; focused on event names, properties, and trigger conditions. |

All templates include a shared `ai-task` label so AI-generated work can be filtered across the organization.

---

## Pull Request Template

The default PR template is designed for AI-generated pull requests.
It prompts the author (human or agent) to document:

- the linked issue
- a summary of changes
- files affected
- validation performed
- assumptions made
- what was intentionally left unchanged
- risks and areas that need human review focus

---

## Workflow

1. An engineer opens an issue using the appropriate template.
2. The filled-out issue becomes the task specification for Claude Code.
3. Claude Code implements the task in a Codespace and opens a pull request.
4. The PR template guides the agent to document its work clearly.
5. A human reviewer reviews the PR, focusing on the highlighted risk areas.

---

## Adding or Updating Templates

Templates live in `.github/ISSUE_TEMPLATE/`.
Each file is a YAML-based [GitHub Issue Form](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/syntax-for-githubs-form-schema).
The `config.yml` file controls whether blank issues are allowed (currently disabled).
