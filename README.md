# Luma Focus for Logseq DB

Focus is an alternative Luma design on the `focus` branch. The original Luma
style remains on `main`. It builds on the Logseq DB 2.0.2 compatibility,
editor text-size fix and journal-spacing changes.

- A cool blue-gray palette in light and dark mode, with a flat reading surface.
- A 730px reading width, tighter journal spacing and no large empty-day minimum.
- A sans-serif date gutter beside journal notes on wider panes; dates stack
  above notes when space is limited. Standalone journal dates use the same font.
- A 62px desktop icon rail when the native left sidebar is closed. Use Logseq's
  sidebar button to open the full sidebar, including graph names, favorites,
  recents and its normal resizing. Mobile keeps the native drawer.

The complete localized date stays clickable. Logseq does not
expose separate day/month elements to CSS, so the gutter uses the full date
rather than the split day/month shown in the concept preview. Navigation names
remain available to screen readers when the rail is compact.

Journal dates use Instrument Sans, falling back to Inter and the system sans
font if remote fonts are unavailable. Hover actions and property popups keep
their own interface typography. No JavaScript or graph-data changes are needed.

## Installation

**Marketplace**

This branch is not a separate marketplace release. The marketplace listing
continues to install its published Luma version.

**Manual installation**

Copy `custom.css` into `logseq/custom.css` or paste this line into `logseq/custom.css`

```css
@import url('https://cdn.jsdelivr.net/gh/kwand/logseq-luma@focus/custom.css');
```

## Logseq DB 2.0.2

This variant supports Logseq DB 2.0.2, including its Shui menus, dialogs,
property views and color tokens in light and dark mode. Navigation controls
and scrollbars remain visible, and the right sidebar uses the available height.

For DB graphs, paste the import line above into the custom CSS editor in Logseq
settings, or paste the complete `custom.css` file.
Replace the existing contents, including any earlier journal typography overrides.
The `logseq/custom.css` installation above applies to file graphs. The marketplace
installs whichever version is published there.

Ordinary block editors inherit the surrounding text size and line height,
so entering edit mode does not enlarge the text. Heading and journal title
styles retain their own sizes.

### Journal titles

Journal dates use Instrument Sans at 18px in the desktop gutter and 22px on
stacked and standalone journal pages. Hover controls, properties and ordinary
page titles keep their interface typography. The compact gutter uses 11px tags.

Adjust `--luma-focus-reading-width`, `--luma-focus-date-width`,
`--luma-focus-journal-space` and `--luma-focus-rail-width` near the Focus section
at the end of `custom.css` to tune the layout. The font import includes Inter
and Instrument Sans. The base stylesheet's embedded Newsreader and its license
are retained for compatibility with any custom overrides.

### Compatibility checks

Reviewed against Logseq tag `2.0.2`
(`533ac4382a7b69baa98de3a973bff90305b212dc`). Browser checks with source-derived
DOM fixtures and relevant Logseq styles cover six light/dark layout cases at
1440px, 1024px and 390px:

- Desktop date gutters, standalone date typography and narrow-pane stacking,
  including a 440px main pane representing an open right sidebar.
- Native icon-rail/full-sidebar states, saved sidebar width and the closing
  transition completing normally.
- Matching body read/editor sizes and line heights, plus matching title editor
  and caret-mirror typography. Native journal dates themselves remain read-only.
- Separate hover-control typography, visible menu colors, no horizontal page
  overflow and preservation of inline cached journal heights.
- Journal font fallback with external requests disabled.

A live desktop integration check remains necessary for search, slash commands,
property editing, table scrolling, and opening/resizing the right sidebar.
