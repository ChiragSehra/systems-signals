# Content Conventions

## Goal

Keep authoring predictable so articles remain portable, readable and easy to maintain.

## Article Location

Create each article at:

```text
posts/<slug>/index.qmd
```

Example:

```text
posts/reversible-agent-systems/index.qmd
```

## Frontmatter

Start with:

```yaml
---
title: "Reversible Agent Systems"
description: "Rollback, memory and guarantees in self-modifying agent runtimes."
date: 2026-08-17
categories:
  - Agents
  - Systems
series: null
series_order: null
---
```

Use concise descriptions.

Use stable lowercase URL slugs.

## Headings

Use one page title through frontmatter.

Inside the article:

```markdown
## Major section

### Subsection
```

Avoid manually adding another H1 unless necessary.

## Code

Use fenced code blocks and always provide the language when known.

Example:

```python
def rollback(effect):
    return effect.inverse()
```

For terminal commands:

```bash
quarto preview
```

## Equations

Use standard Quarto math syntax.

Inline:

```markdown
The communication cost is proportional to $O(n^2)$.
```

Display:

```markdown
$$
T = T_{\text{compute}} + T_{\text{communication}}
$$
```

## Mermaid

Prefer Mermaid for simple architecture and sequence diagrams.

Example:

````markdown
```{mermaid}
flowchart LR
    A[Markdown] --> B[Quarto]
    B --> C[Static HTML]
    C --> D[GitHub Pages]
```
````

For complex diagrams, use SVG.

## Images

Keep article-specific images near the article when appropriate.

Example:

```text
posts/reversible-agent-systems/
├── index.qmd
└── images/
    └── rollback-model.svg
```

Use descriptive filenames.

Always include meaningful alt text.

## Tables

Use Markdown tables for simple cases.

Use raw HTML only when Markdown/Quarto cannot express the requirement cleanly.

## Citations

Use bibliography files rather than manually formatted reference lists when practical.

Keep citation keys understandable.

Example:

```markdown
This idea follows prior work on distributed rollback [@example2026].
```

## Footnotes

Use footnotes for supporting detail that would interrupt the main argument.

Do not hide essential reasoning in footnotes.

## Series

For a series:

```yaml
series: "Agent Systems"
series_order: 1
```

Series pages should eventually support previous and next navigation.

## Comments

Do not manually embed comments inside each article.

Configure Giscus globally where possible.

Article-specific disabling may be supported through frontmatter if useful.

## Drafts

Prefer a simple draft convention.

For example:

```yaml
draft: true
```

or a dedicated drafts directory if Quarto configuration makes that cleaner.

Document whichever approach is implemented.

## Generated Output

Never edit generated HTML directly.

Edit source `.qmd`, configuration, templates, CSS or assets instead.
