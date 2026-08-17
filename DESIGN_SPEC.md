# Design Specification

## Design Objective

Create a calm, high-signal environment for reading long technical articles.

The design should support concentration rather than compete for attention.

## Reference

Use the reading experience of:

https://jax-ml.github.io/scaling-book/

as inspiration.

Do not reproduce its implementation or styling exactly.

## Visual Character

Target:

- academic
- technical
- restrained
- precise
- contemporary
- readable

Avoid:

- startup landing-page aesthetics
- generic documentation styling
- excessive borders
- card-heavy interfaces
- gradients
- large decorative hero sections
- animation-heavy transitions

## Typography

Body copy should be comfortable for long reading sessions.

Requirements:

- moderate line length
- generous line-height
- strong hierarchy
- clear distinction between H1/H2/H3
- readable inline code
- visibly distinct links without excessive decoration
- sensible paragraph spacing

Desktop article content should not expand to the full browser width.

## Article Layout

Preferred desktop composition:

```text
┌──────────────────────────────────────────────────────────────┐
│ Site navigation                                              │
├──────────────────────────────────────────────────────────────┤
│                                                              │
│               Article title                                  │
│               Description                                    │
│               Date · categories                              │
│                                                              │
│      Main article body              Table of contents        │
│      Main article body              Table of contents        │
│      Main article body                                       │
│                                                              │
│      References                                              │
│                                                              │
│      Previous / Next                                         │
│                                                              │
│      Discussion                                              │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

The table of contents may become inline/collapsible on smaller screens.

## Code

Code blocks should:

- use excellent syntax highlighting
- support copy-to-clipboard
- distinguish shell, Python, JSON, YAML and other languages
- have comfortable padding
- avoid unnecessarily large chrome
- scroll horizontally rather than break layout

Inline code should remain subtle but visible.

## Equations

Mathematical notation should feel native to the article.

Display equations should have enough vertical breathing room.

Long equations should not destroy mobile layout.

## Figures

Figures should support:

- responsive sizing
- captions
- SVG
- PNG/JPEG
- wide diagrams where appropriate

Technical diagrams should be allowed more width than ordinary prose when the layout supports it.

## Tables

Tables should be clean and readable.

Avoid heavy grid borders.

On narrow screens, prefer horizontal scrolling over shrinking text until it becomes unreadable.

## Callouts

Callouts should be used sparingly.

Good use cases:

- note
- warning
- important distinction
- implementation detail
- open question

Avoid turning every paragraph into a boxed element.

## Homepage

The homepage should emphasise writing, not branding.

Suggested order:

1. name / site title
2. one- or two-sentence description
3. recent writing
4. series
5. topics
6. about link

Recent writing should display:

- title
- date
- short description
- optional categories

## Navigation

Primary navigation should remain small.

Suggested items:

- Writing
- Series
- About
- GitHub

Do not create nested mega-menus.

## Dark Mode

Support light and dark themes.

Dark mode must preserve:

- readable contrast
- code readability
- equations
- tables
- callouts
- Giscus compatibility

## Comments

Comments should be visually separated from the article body.

Use a small heading such as:

```text
Discussion
```

Giscus appears underneath.

The comment area should feel like part of the publication, not an embedded social widget.

## Footer

Keep the footer minimal.

Possible items:

- copyright
- GitHub
- RSS
- optional email/contact link

## Responsive Behaviour

Test at approximately:

- 1440px
- 1024px
- 768px
- 390px

At mobile widths:

- collapse secondary navigation
- move/hide sticky TOC
- stack previous/next navigation
- maintain readable text size
- keep figures within viewport
- allow code and table scrolling
