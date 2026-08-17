# Systems / Signals

A Quarto-based personal technical writing site by Chirag Sehra for long-form notes on AI systems, agent architectures, LLM infrastructure, distributed systems, software architecture, and developer tooling.

The site is intentionally static and publication-oriented. Articles are Markdown/Quarto source files, the rendered site is deployed to GitHub Pages, and discussion happens through Giscus and GitHub Discussions.

## Prerequisites

- [Quarto](https://quarto.org/docs/get-started/)
- Git
- A GitHub repository with Pages enabled

Check the local installation with:

```bash
quarto --version
```

## Local development

From the repository root:

```bash
quarto preview
```

The preview server reloads as source files change. Build the static output with:

```bash
quarto render
```

The generated site is written to `_site/`. It is ignored by Git and should never be edited directly.

## Repository structure

```text
.
├── _quarto.yml                    # Site, HTML, comments, and rendering config
├── index.qmd                      # Homepage
├── writing.qmd                    # Date-sorted article listing and RSS feed
├── series.qmd                     # Series index
├── about.qmd                      # About page
├── posts/<slug>/index.qmd         # Individual articles
├── posts/<series>/<part>/index.qmd # Series chapters
├── assets/                        # Shared assets such as the favicon
├── styles.css                     # Small site-specific styling layer
├── references.bib                 # Bibliography database
└── .github/workflows/publish.yml  # GitHub Pages deployment
```

## Adding a post

Create a directory and source file using a stable lowercase slug:

```text
posts/my-new-article/index.qmd
```

Start with frontmatter like this:

```yaml
---
title: "My New Article"
description: "A concise description for listings and metadata."
date: 2026-08-18
author: "Chirag Sehra"
categories:
  - Systems
series: null
series_order: null
draft: false
---
```

The homepage and Writing page use Quarto listings, so published articles appear automatically after rendering. Keep work-in-progress articles local with `draft: true`; set `draft: false` only when the article is ready to be included in the site.

Use one page title from frontmatter, then begin the body with `##` sections. Use fenced code blocks with a language, standard Quarto math syntax, Mermaid for simple diagrams, meaningful image alt text, Markdown tables, callouts, footnotes, and citations where they help the reader inspect the argument.

Set `draft: true` while developing an article. The safest publication check is to run `quarto render` and inspect the listing before pushing.

## Series

Add these fields to each chapter:

```yaml
series: "Agent Systems"
series_order: 1
```

The Series page provides the reading order, and each chapter includes previous/next navigation where applicable. The current example series is `Spatiotemporal Composability`.

## Theme

The site uses a warm neutral light theme and a charcoal dark theme. The global theme toggle lives in the navbar and remembers the reader's choice locally. Code syntax colors are customized for both modes so tokens remain readable without relying on green accents.

## Citations

Add reusable references to `references.bib` and cite them in an article:

```markdown
Distributed systems make ordering explicit [@lamport1978].
```

Quarto renders the citation and bibliography when the referenced key exists in `references.bib`.

## Giscus comments setup

The site is configured for Giscus in `_quarto.yml`. Before publishing comments:

1. Enable GitHub Discussions for the repository.
2. Install and authorise the [Giscus GitHub App](https://github.com/apps/giscus).
3. Create or choose the discussion category to use for article comments.
4. Use [giscus.app](https://giscus.app/) to obtain the repository ID and category ID.
5. Confirm the repository and category IDs in `_quarto.yml` match the values generated for this repository.
6. Render locally and confirm the Discussion section appears at the bottom of an article.

The mapping is `pathname`, which gives each article a stable discussion thread based on its URL path. Do not commit fabricated IDs.

## GitHub Pages deployment

The workflow in `.github/workflows/publish.yml` renders the site with Quarto, uploads `_site/` as a Pages artifact, and deploys it with the current GitHub Pages actions.

One-time repository setup:

1. Push this project to a GitHub repository with the default branch named `main`.
2. In **Settings → Pages**, set the source to **GitHub Actions**.
3. Push to `main` or run the workflow manually from the Actions tab.
4. Confirm the `site-url` and GitHub links in `_quarto.yml` match the live repository URL.

No custom domain or secrets are required by the workflow. A custom domain can be added later through GitHub Pages settings and a `CNAME` file if needed.

## Verification checklist

Before publishing, run:

```bash
quarto render
```

Then inspect the homepage, writing listing, series page, all series chapters, previous/next navigation, code blocks in both themes, equation, Mermaid diagram, citation, footnote, mobile layout, and Giscus configuration.
