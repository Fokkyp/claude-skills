# Repository Guidelines

## Project Structure & Module Organization
This repository stores reusable Claude Skills. Each skill lives in its own top-level directory, and the entry file must be `SKILL.md`. Current examples include `prd-generator/` and `competitive-analysis/`. If a skill needs supporting material, keep it in the same directory, for example under `references/`, so the skill remains self-contained and portable.

## Build, Test, and Development Commands
This repository has no build pipeline; work is primarily Markdown authoring and review. Useful commands:

- `rg --files` to inspect repository contents
- `sed -n '1,220p' path/to/SKILL.md` to review a skill quickly
- `git diff` to inspect wording and structure changes
- `git status --short --branch` to confirm branch and workspace state

Installation and usage instructions for public users should be documented in `README.md`, not only inside individual skills.

## Coding Style & Naming Conventions
Use `kebab-case` for skill directory names, such as `competitive-analysis`. Every `SKILL.md` should start with YAML frontmatter:

```yaml
---
name: skill-name
description: One-line summary of what the skill does.
---
```

Skill content should clearly explain when to use the skill, what it does, how to invoke it, and what output it should produce. Prefer Markdown headings, fenced code blocks, and copy-pastable examples over vague descriptive text.

## Testing Guidelines
No automated tests are configured, so validation is manual. Before committing, confirm that:

- frontmatter fields are present and accurate
- heading hierarchy is clear
- examples match the skill’s actual behavior
- file paths, file names, and commands are correct
- any `references/` content mentioned in the skill actually exists

Read the updated `SKILL.md` end to end before merge.

## Commit & Pull Request Guidelines
Use short, imperative commit messages such as `Update SKILL.md` or `Add competitive-analysis skill`. Keep each commit focused on one type of change.

Pull requests should state which skills were changed, what behavior was added or revised, and how the changes were manually validated. If `README.md` is updated, make sure its feature descriptions, installation steps, and usage examples stay consistent with the actual skills.
