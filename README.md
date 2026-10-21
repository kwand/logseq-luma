# Logseq Luma Theme
A minimal and detail oriented light and dark theme for Logseq. *Presented as is — there may be some inconsistencies that I will be slowly fixing as I have time.*

<img width="1796" alt="preview-light" src="https://user-images.githubusercontent.com/59900904/181398409-7c98856d-fb3b-4ca5-9fef-8d975056d86c.png">
<img width="1840" alt="preview-dark" src="https://user-images.githubusercontent.com/59900904/181398414-62f8b5d0-87e6-445b-8ae8-e4dc5761cfee.png">

## Installation

**Marketplace**

Find Luma in the Logseq theme marketplace within the app.

**Manual installation**

Copy `custom.css` into `logseq/custom.css` or paste this line into `logseq/custom.css`

```css
@import url('https://cdn.jsdelivr.net/gh/kwand/logseq-luma@main/custom.css');
```

## Logseq DB 2.0.2

Version 0.2.2 supports Logseq DB 2.0.2, including its Shui menus, dialogs,
property views and color tokens in light and dark mode. Navigation controls
and scrollbars remain visible, and the right sidebar uses the available height.

For DB graphs, paste `custom.css` into the custom CSS editor in Logseq settings.
Replace the existing contents, including any earlier journal typography overrides.
The `logseq/custom.css` installation above applies to file graphs. The marketplace
installs whichever version is published there.

Ordinary block editors inherit the surrounding text size and line height,
so entering edit mode does not enlarge the text. Heading and journal title
styles retain their own sizes.

### Journal titles

Journal dates use Newsreader at 26px in both the journal feed and standalone
journal pages. Hover controls, tags, properties and ordinary page titles keep
their interface typography. To change the date size, edit
`--luma-journal-title-size` in `custom.css`.

The Latin Newsreader webfont is embedded in the stylesheet, with its copyright
notice and SIL Open Font License 1.1. Displaying journal dates does not require
an external font request. The theme's existing Inter import is retained.

### Compatibility checks

Reviewed against Logseq tag `2.0.2`
(`533ac4382a7b69baa98de3a973bff90305b212dc`). Browser checks with source-derived
DOM fixtures and relevant Logseq styles cover:

- Menu colors and header visibility in light/dark modes with logseq, none, blue
  and tomato accents.
- Journal feed and standalone title typography, including title editors and
  their hidden caret mirrors, in light/dark modes with logseq and blue accents.
- Unchanged typography for hover controls, tags, properties, ordinary pages,
  body headings and editor popups.
- Actual Newsreader glyph rendering with external requests disabled.

A live desktop integration check remains necessary for search, slash commands,
property editing, table scrolling, and opening/resizing the right sidebar.
