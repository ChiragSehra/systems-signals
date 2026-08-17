# Start Here

This folder contains the documents to give Codex before it starts building the technical writing site.

## Files

### `PROJECT_BRIEF.md`

Defines the product, architecture and desired reader experience.

### `AGENTS.md`

Permanent repository-level instructions for Codex and other coding agents.

Keep this file in the repository root.

### `DESIGN_SPEC.md`

Defines the visual direction and layout expectations.

### `CONTENT_CONVENTIONS.md`

Defines where articles live and how they should be authored.

### `CODEX_BOOTSTRAP_PROMPT.md`

The first prompt to paste into Codex.

## Recommended Setup

Create an empty GitHub repository locally, then copy these files into its root.

Example:

```bash
mkdir technical-writing-site
cd technical-writing-site
git init
```

Copy in:

```text
PROJECT_BRIEF.md
AGENTS.md
DESIGN_SPEC.md
CONTENT_CONVENTIONS.md
CODEX_BOOTSTRAP_PROMPT.md
```

Then start Codex from the same directory:

```bash
codex
```

Open `CODEX_BOOTSTRAP_PROMPT.md` and paste its bootstrap prompt into Codex.

## Suggested First Git Commit

Before Codex changes anything:

```bash
git add .
git commit -m "Add initial site specification"
```

This gives you a clean baseline before the agent begins implementation.

## After the First Codex Pass

Review the generated site and iterate with narrow prompts.

Examples:

```text
The article page still feels too much like documentation.
Improve typography, whitespace, article width and heading hierarchy.
Do not add decorative UI.
Run quarto render afterwards.
```

```text
Improve only the mobile reading experience.
Focus on the TOC, tables, code blocks, figures and previous/next navigation.
Do not redesign the desktop layout.
```

```text
Review the homepage as an editor.
Reduce anything that feels like a SaaS landing page.
Make the writing itself the dominant visual element.
```
