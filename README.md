# Arch PR Authoring for Claude Code

A Claude Code plugin that helps authors write PR descriptions with enough grounded product context for Arch to turn the description into useful goals later.

It activates when Claude prepares, creates, or edits a PR description. It does not run QA, simulations, MCP tools, or any Arch workflow.

## Install

From inside Claude Code:

```text
/plugin marketplace add the-simulation-company/arch-cc-plugin
/plugin install pr-qa-authoring@arch-pr-authoring
/reload-plugins
```

## What it adds

The `pr-qa-description` skill asks Claude to ground the PR description in the diff, relevant tests, and repository template, then capture:

- the user-visible change;
- affected pages and components;
- how to reach the behavior;
- required setup or state; and
- evidenced behavioral variants.

Human-authored and template sections are preserved. Missing facts are marked for the author instead of invented.

## Local development

```bash
claude --plugin-dir ./plugins/pr-qa-authoring
```

Ask Claude to create or edit a PR description without naming the skill. Confirm that product context is added, the repository template is preserved, and no external QA action occurs.

Use [`fixtures/pr-description-cases.md`](fixtures/pr-description-cases.md) for the shared information-level behavior checks.
