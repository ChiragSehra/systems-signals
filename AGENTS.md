# AGENTS.md

## Repository Purpose

This repository contains a personal technical writing site.

The site publishes long-form material about AI systems, distributed systems, agent architectures, LLM infrastructure, software engineering and related technical research.

Treat the repository as both:

- a publishing system
- a technical writing codebase

Changes should preserve the quality of both.

## Stack

Use the following stack unless explicitly instructed otherwise:

- Quarto
- Markdown / Quarto Markdown
- GitHub Pages
- GitHub Actions
- Giscus
- GitHub Discussions

Do not introduce:

- a custom backend
- a database
- a CMS
- React or Next.js
- a client-side application framework

unless the requested feature genuinely requires one and the trade-off is explained first.

## Core Engineering Principles

Prefer:

1. native Quarto functionality
2. configuration
3. CSS / SCSS
4. small, isolated JavaScript enhancements

in that order.

Keep dependencies minimal.

Do not add libraries simply to solve cosmetic problems that CSS can solve.

Do not modify generated output manually.

## Content Structure

Standalone articles should live under:

```text
posts/<slug>/index.qmd
```

Reusable assets should live under an appropriate shared asset directory.

Do not reorganise article content without a reason.

Do not rewrite article prose unless the user explicitly asks for editorial changes.

## Article Frontmatter

Support frontmatter similar to:

```yaml
---
title: "Article title"
description: "Short article description."
date: YYYY-MM-DD
categories:
  - Systems
  - Agents
series: null
series_order: null
---
```

Series metadata should be optional.

## Design Direction

The site should feel like:

- a technical book
- a research publication
- an engineering notebook with publication-quality presentation

It should not feel like:

- a SaaS landing page
- a corporate marketing blog
- a dashboard
- a documentation portal with excessive navigation chrome

Prioritise:

- typography
- line length
- hierarchy
- whitespace
- code readability
- equations
- diagrams
- citations
- figures

Avoid:

- gradients
- glassmorphism
- decorative animations
- oversized cards
- excessive rounded containers
- unnecessary icons
- visual clutter

## Technical Article Requirements

Article pages should support:

- table of contents
- anchored headings
- syntax highlighting
- code-copy affordance
- shell snippets
- equations
- Mermaid
- images and SVG
- captions
- tables
- callouts
- blockquotes
- footnotes
- citations
- bibliography
- previous/next navigation where relevant
- Giscus comments

## Comments

Use Giscus.

Do not hardcode fabricated values for:

- repository ID
- category ID
- Giscus metadata

Use placeholders and document manual setup steps.

Prefer stable discussion mapping such as pathname.

## Styling Rules

Any custom CSS or SCSS should be:

- small
- documented when non-obvious
- responsive
- easy to remove
- based on variables where practical

Do not duplicate large portions of a third-party theme merely to change a few visual details.

## Mobile Behaviour

At narrow viewport widths:

- article text must not overflow
- code blocks should horizontally scroll if required
- equations should remain usable
- figures should fit their container
- tables should remain readable or scroll
- table of contents must not crowd the article
- previous/next navigation should stack cleanly
- headings should scale appropriately

## Verification

After changing configuration, styling, templates, navigation or build logic, run:

```bash
quarto render
```

Fix build errors before reporting completion.

When visual changes are substantial, use available preview or browser tooling if present.

Verify:

- homepage renders
- article pages render
- internal navigation works
- example content renders
- code renders correctly
- equations render
- Mermaid renders
- citations render
- mobile CSS has no obvious overflow
- no secrets are introduced

## Git Behaviour

Do not:

- rewrite git history
- force push
- delete user content
- discard unrelated local changes

unless explicitly instructed.

Keep changes focused on the requested task.

## Documentation

Keep `README.md` current when changing:

- local setup
- project structure
- publishing workflow
- deployment
- Giscus
- GitHub Pages
- authoring conventions

## Decision Rule

If a requested change can be implemented cleanly with Quarto configuration, do that before creating custom templates or JavaScript.
