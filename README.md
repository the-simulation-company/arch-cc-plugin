# Arch PR Authoring for Claude Code

A Claude Code plugin that helps authors write PR descriptions with enough grounded product context for Arch to turn the description into useful goals later.

Built by [Foothill Labs](https://foothill.sh).

It activates when Claude prepares, creates, or edits a PR description.

## Install

From inside Claude Code:

```text
/plugin marketplace add https://github.com/the-simulation-company/arch-cc-plugin.git
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

Human-authored and template sections are preserved. The skill traces relevant repository evidence before asking the author for context that is genuinely unavailable.
