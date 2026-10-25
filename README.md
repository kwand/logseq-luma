# Luma Refined for Logseq DB

Luma Refined implements the Calm design on the `refined` branch. It builds on
Luma's Logseq DB 2.0.2 compatibility, editor text-size fix and journal spacing.
The original Luma remains on `main`; the earlier Focus experiment remains on
`focus`.

- A cool neutral palette, white reading surface in light mode and a blue-gray
  surface in dark mode.
- A comfortable 680px reading width, 14px body text and open line spacing.
- Embedded Newsreader titles: 34px for notes and 26px for journal dates, both in
  the feed and on standalone journal pages. Long titles wrap when necessary.
- Quiet properties, simple linked-reference dividers and a lightly tinted
  right sidebar.
- A familiar full left sidebar with a 184px default width. Logseq's toggle,
  saved sidebar width and resizing remain available.
- Refined Pages, flashcard and graph controls using their existing native UI.

Title typography applies only to title text, its editor and its caret mirror.
Add icon, Set property, tags, menus and other interface controls retain Inter.
The title actions appear above the title, with space reserved inside each
journal row. Ordinary block editors use the same size and line height as their
rendered text.

## Installation

This branch is a separate variant, not a marketplace release. For Logseq DB,
replace the contents of the custom CSS editor in Settings with:

```css
@import url("https://cdn.jsdelivr.net/gh/kwand/logseq-luma@refined/custom.css");
```

For file graphs, put the same line in `logseq/custom.css`. You can also copy the
entire stylesheet. Remove previous theme imports and temporary CSS overrides
when switching, so they do not override Refined.

The CDN caches branch URLs. To request a particular update, append a new version
query to the URL, for example `custom.css?v=0.3.0-refined.1`, or use the commit
SHA in place of `refined` for a fixed version.

## Native Logseq behavior

The design is CSS only and does not change graph data or add application
features. Native structure determines a few details:

- The DB Pages list is a virtualized Shui table. Its 33px row height is retained
  to preserve scrolling, selection and column behavior; typography, rules and
  surrounding spacing carry the Calm style.
- Flashcards open in Logseq's review dialog. Questions use Newsreader; answers
  and review buttons retain their normal interface typography and behavior.
- Graph rendering and node positions remain native. The theme styles the graph
  background and existing controls, rather than replacing its canvas renderer.
- Journal rows retain inline heights cached by Logseq's virtualizer. Empty days
  do not acquire a new fixed minimum from the theme.

## Customization

The Refined section near the end of `custom.css` exposes:

```css
--luma-refined-reading-width: 680px;
--luma-refined-body-size: 14px;
--luma-refined-body-line-height: 1.76;
--luma-refined-journal-space: 40px;
```

Newsreader's Latin webfont is embedded, with its copyright notice and SIL Open
Font License 1.1 in the stylesheet. It works without a font download. Inter uses
the existing import and falls back to the system sans-serif font.

## Compatibility checks

Reviewed against Logseq tag `2.0.2`
(`533ac4382a7b69baa98de3a973bff90305b212dc`). Browser checks use source-derived
DOM and the installed application's compiled CSS in light and dark mode, on
desktop, narrow panes and touch-sized screens. They cover title/editor/caret
metrics, above-title actions, journal spacing, cached virtual row heights,
sidebar sizing, Pages row geometry, properties and flashcards.

These isolated checks do not run Logseq's application logic. Search, property
editing, review scheduling and graph interaction still use Logseq's native
implementation.
