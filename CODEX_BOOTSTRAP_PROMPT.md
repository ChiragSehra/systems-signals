# Codex Bootstrap Prompt

Copy the prompt below into Codex from the root of the repository.

---

You are setting up a new personal technical writing site.

Before making changes, read these files completely:

- `PROJECT_BRIEF.md`
- `AGENTS.md`
- `DESIGN_SPEC.md`
- `CONTENT_CONVENTIONS.md`

Treat them as the source of truth for this task.

## Objective

Build the first working version of the site described in those documents.

The site should be a technical-publication-style blog / online book for long-form engineering writing.

Use:

- Quarto
- Markdown / QMD
- GitHub Pages
- GitHub Actions
- Giscus
- GitHub Discussions

Do not add a custom backend or database.

Do not use React or Next.js unless a requirement cannot reasonably be achieved with Quarto.

## Work in this order

### 1. Inspect the repository

First inspect the current directory and existing files.

Do not overwrite useful existing work.

Briefly state what exists and what you plan to add.

### 2. Scaffold the Quarto project

Create a clean Quarto site structure.

At minimum include:

- `_quarto.yml`
- `index.qmd`
- `about.qmd`
- a writing/posts landing page
- a series landing page if practical
- `posts/`
- shared assets/styles
- bibliography support
- `.gitignore`
- `README.md`

Use sensible file names and paths.

### 3. Implement the publication design

Create a restrained technical-publication aesthetic inspired by the reading experience of:

https://jax-ml.github.io/scaling-book/

Do not copy that site's CSS or implementation.

Focus on:

- readable article width
- typography
- whitespace
- heading hierarchy
- table of contents
- code blocks
- equations
- figures
- tables
- footnotes
- citations
- mobile behaviour
- light/dark mode

Avoid:

- gradients
- oversized cards
- unnecessary animations
- marketing-style hero layouts
- decorative UI that does not help reading

Prefer Quarto configuration before custom CSS.

Prefer CSS/SCSS before JavaScript.

### 4. Build the content structure

Support standalone articles under:

`posts/<slug>/index.qmd`

Support optional series metadata such as:

```yaml
series: "Agent Systems"
series_order: 1
```

Create two useful example articles.

Do not use lorem ipsum.

The examples should demonstrate real technical-content features such as:

- table of contents
- Python
- shell commands
- YAML or JSON
- equations
- Mermaid
- image/figure handling
- table
- callout
- blockquote
- footnote
- citation

Keep example prose concise. The goal is to exercise the publishing system, not create long fake articles.

### 5. Add Giscus support

Add a discussion section at the bottom of article pages.

Use Giscus.

Requirements:

- one GitHub Discussion per article/page
- use a stable mapping such as pathname
- reactions enabled
- input at the bottom
- support site light/dark theme where practical

IMPORTANT:

Do not fabricate Giscus repository IDs or category IDs.

Use explicit placeholders.

Document exactly what I must do manually:

1. enable GitHub Discussions
2. install/authorise the Giscus GitHub App
3. choose the discussion category
4. obtain the repository/category identifiers
5. replace the placeholders

If native Quarto Giscus configuration can satisfy the requirements, use it rather than custom embedding.

### 6. Add GitHub Pages deployment

Create a GitHub Actions workflow using the current recommended static GitHub Pages deployment approach.

It should:

- check out the repository
- set up Quarto
- render the site
- upload the rendered output
- deploy to GitHub Pages

Do not commit secrets.

Do not hardcode a custom domain.

Document any GitHub repository settings I must enable manually.

### 7. Write the README

The README should explain:

- project purpose
- prerequisites
- local setup
- `quarto preview`
- `quarto render`
- repository structure
- how to create a new post
- frontmatter conventions
- how series work
- how citations work
- how Giscus is configured
- manual Giscus setup
- GitHub Pages setup
- deployment workflow
- how to add a custom domain later

Keep it useful to an engineer who did not create the project.

### 8. Verify everything

Before finishing:

- run `quarto render`
- fix build errors
- inspect warnings
- verify internal navigation
- verify example articles
- verify equations render
- verify Mermaid renders
- verify citations/footnotes work
- verify code blocks render
- check for obvious mobile overflow in CSS
- ensure no secrets or local absolute paths are committed

If Quarto is not installed in the environment, do not pretend that the build succeeded.

Instead:

- inspect what can be validated statically
- document the exact missing dependency
- provide the exact command I should run once Quarto is installed

### 9. Keep scope controlled

Do not overengineer.

Do not add:

- search infrastructure unless Quarto provides it trivially
- databases
- analytics
- newsletter systems
- authentication beyond Giscus/GitHub
- CMS integrations
- complex JavaScript

These can be added later.

## Completion report

When finished, tell me:

1. what you created
2. repository structure
3. important design decisions
4. commands to run locally
5. manual GitHub/Giscus steps remaining
6. files I should edit first to customise the site
7. any build or validation issue that remains

Do not stop after scaffolding.

Implement as much of the working site as possible and validate it.
