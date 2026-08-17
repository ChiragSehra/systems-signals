# Technical Writing Site — Project Brief

## Purpose

Build a personal technical writing site for long-form engineering content.

The site should feel closer to an online technical book, research publication, or systems paper collection than a conventional blog.

Primary subject areas may include:

- AI engineering
- agent systems
- LLM infrastructure
- distributed systems
- software architecture
- developer tooling
- systems research
- technical deep dives

The site should support both:

1. standalone long-form articles
2. multi-part article series that can be read sequentially like a book

## Product Goals

The site should make it easy to:

- write articles in Markdown or Quarto Markdown
- publish through GitHub
- review content changes through pull requests
- render equations, code, diagrams, tables and citations well
- navigate long technical articles comfortably
- collect comments and replies under each article
- deploy automatically without maintaining a backend
- keep the codebase simple enough for one person to maintain

## Desired Reader Experience

The reading experience should be inspired by technical publications such as the JAX Scaling Book:

https://jax-ml.github.io/scaling-book/

Do not copy its source code or create a pixel-for-pixel clone.

Instead, preserve the qualities that make it effective:

- strong typography
- generous whitespace
- readable line length
- clear heading hierarchy
- useful table of contents
- excellent code presentation
- good mathematical notation
- clean figures and captions
- references and footnotes
- minimal distraction
- article-level comments
- clear previous/next navigation where articles belong to a series

## Proposed Stack

Use:

- Quarto
- Markdown / `.qmd`
- GitHub
- GitHub Actions
- GitHub Pages
- Giscus
- GitHub Discussions

Avoid adding a server-side backend or database.

Prefer native Quarto features before introducing custom JavaScript.

## Information Architecture

The site should support the following conceptual structure:

```text
Home
├── Writing
│   ├── Standalone Article
│   ├── Standalone Article
│   └── Standalone Article
│
├── Series
│   ├── Agent Systems
│   │   ├── Part 1
│   │   ├── Part 2
│   │   └── Part 3
│   │
│   └── LLM Systems
│       ├── Part 1
│       └── Part 2
│
└── About
```

A reader should not be forced to read everything sequentially.

Standalone writing and structured series should coexist.

## Authoring Model

New standalone posts should be easy to add:

```text
posts/<slug>/index.qmd
```

For example:

```text
posts/reversible-agent-systems/index.qmd
```

Suggested frontmatter:

```yaml
---
title: "Reversible Agent Systems"
description: "Rollback, state, memory and guarantees in self-modifying agent runtimes."
date: 2026-08-17
categories:
  - Agents
  - Systems
series: null
---
```

Series posts may additionally contain:

```yaml
series: "Agent Systems"
series_order: 2
```

## Article Requirements

Article pages should support:

- title
- description/subtitle
- date
- author
- categories/tags
- estimated reading time if practical
- generated table of contents
- anchored headings
- syntax-highlighted code
- copy buttons on code blocks
- shell snippets
- mathematical equations
- Mermaid diagrams
- images
- SVG
- figure captions
- tables
- callouts
- blockquotes
- footnotes
- citations and bibliography
- related article links
- previous/next links for series
- Giscus comments at the bottom

## Homepage Requirements

The homepage should be understated.

Include:

- site title / author name placeholder
- concise description
- recent writing
- topic/category navigation
- series
- article title
- publication date
- description

Avoid:

- oversized marketing hero sections
- SaaS-style cards everywhere
- gradients
- testimonials
- feature grids
- animations for their own sake

## Comments

Use Giscus.

Requirements:

- one discussion thread per article/page
- stable page mapping, preferably pathname
- reactions enabled
- comment box below article content
- light/dark theme compatibility
- GitHub authentication
- no custom comments backend

Do not invent repository IDs or Giscus category IDs.

Use clearly documented placeholders until the GitHub repository is configured.

## Deployment

Use GitHub Actions and GitHub Pages.

Expected workflow:

```text
write
  ↓
git commit
  ↓
push / merge
  ↓
GitHub Actions
  ↓
quarto render
  ↓
GitHub Pages
```

Production output should be generated automatically.

Generated site files should not be manually edited.

## Local Development

Expected developer commands:

```bash
quarto preview
```

and:

```bash
quarto render
```

Local setup must be documented in `README.md`.

## Quality Bar

The site should:

- build without errors
- contain no broken internal navigation
- work at mobile widths
- keep code blocks usable on small screens
- keep equations readable
- avoid content overflow
- use semantic HTML where practical
- be accessible by default
- keep dependencies minimal
- avoid unnecessary JavaScript
- avoid committing secrets
- avoid machine-specific paths

## Design Principle

When deciding between decorative UI and readability, choose readability.

When deciding between custom code and native Quarto functionality, choose native Quarto functionality.

When deciding between a blog aesthetic and a technical-publication aesthetic, choose the technical-publication aesthetic.
