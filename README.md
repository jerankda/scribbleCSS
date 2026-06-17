# scribble.css

A hand-drawn CSS framework that looks like it came straight out of a kid's sketchbook. No smooth curves, no perfect grids — just wobbly lines, crayon colors, and sticky-note charm.

## Quick Start

```html
<!-- 1. Add handwriting fonts (optional but recommended) -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Patrick+Hand&family=Pangolin&family=Permanent+Marker&family=Comic+Neue:wght@400;700&family=Courier+Prime&display=swap" rel="stylesheet">

<!-- 2. Include scribble.css -->
<link rel="stylesheet" href="scribble.css">

<!-- 3. Add SVG filters for rough edges (drop this at the top of <body>) -->
<svg style="display:none;position:absolute;width:0;height:0" aria-hidden="true">
  <filter id="scribble-rough" x="-5%" y="-5%" width="110%" height="110%">
    <feTurbulence type="turbulence" baseFrequency="0.04" numOctaves="3" result="noise" />
    <feDisplacementMap in="SourceGraphic" in2="noise" scale="2.5" xChannelSelector="R" yChannelSelector="G" />
  </filter>
  <filter id="scribble-rough-heavy" x="-8%" y="-8%" width="116%" height="116%">
    <feTurbulence type="turbulence" baseFrequency="0.06" numOctaves="4" result="noise" />
    <feDisplacementMap in="SourceGraphic" in2="noise" scale="4" xChannelSelector="R" yChannelSelector="G" />
  </filter>
  <filter id="scribble-crayon" x="-2%" y="-2%" width="104%" height="104%">
    <feTurbulence type="fractalNoise" baseFrequency="0.5" numOctaves="3" result="noise" />
    <feColorMatrix type="matrix" in="noise" values="0 0 0 0 0   0 0 0 0 0   0 0 0 0 0   0 0 0 0.08 0" />
    <feComposite in="SourceGraphic" in2="noise" operator="in" />
  </filter>
  <filter id="scribble-tear" x="-2%" y="-2%" width="104%" height="104%">
    <feTurbulence type="turbulence" baseFrequency="0.08" numOctaves="5" result="noise" />
    <feDisplacementMap in="SourceGraphic" in2="noise" scale="6" xChannelSelector="R" yChannelSelector="G" />
  </filter>
</svg>
```

## Components

### Typography
- **Headings** (h1–h6) with wavy hand-drawn SVG underlines
- **`<mark>`** styled as a real highlighter
- **`<del>`** with wavy hand-drawn strikethrough
- **`<ins>`** with sketchy underline
- **`<blockquote>`** as a torn sticky note with tape
- **`<code>` / `<pre>`** notebook-paper code blocks

### Buttons
`.scroll-btn` with 10 variants: primary, ink, crayon, highlight, ghost, torn, success, danger, warning. Sizes: sm, default, lg, xl. Modifiers: pill, block, disabled. Button groups included.

### Cards
`.scroll-card` with notebook paper, sticky note (4 colors), torn edge, doodle border, and dog-ear corner variants. Sections: header, footer, image, title.

### Forms
Text inputs, textareas, selects (custom hand-drawn arrow), checkboxes, radios, toggle switch, fieldset/legend. Validation states, help text, inline forms.

### Alerts
`.scroll-alert` with sticky note, info, success, warning, error, and speech bubble variants. Icon and close button slots.

### Badges
`.scroll-badge` with 8 colors, pill shape, circle (for numbers), arrow tag. Sizes: sm, default, lg.

### Navigation
Nav bar (horizontal/vertical), folder-style tabs, breadcrumbs with hand-drawn arrow separators, pagination.

### Tables
Striped, hoverable, compact, and sketchy (dashed borders) variants. Scrollable container.

### Modals
`.scroll-overlay` + `.scroll-modal` with pure CSS open states (`.is-open` or `:target`). Sticky note variant, close button with spin.

### Tooltips
Pure CSS via `data-tip` attribute. Sticky-note style with hand-drawn border. Positions: top, bottom, left.

### Progress
Progress bar with crayon texture overlay, indeterminate scribble animation, 4 color variants. Spinner, skeleton loader.

### Lists
`.scroll-list` with circle, square, dash, arrow, star, check, and numbered circle markers. Ruled list variant.

### Dividers
`.scroll-hr` with wavy, zigzag, scribble, dots, double, and torn edge variants. Color variants.

### Layout
12-column grid (`.scroll-grid` / `.scroll-col-*`), flexbox utilities, stack, containers, spacing helpers.

### Animations
Wobble, draw, shake, drop-in, fade-in, pop. Infinite variants and delay utilities. Respects `prefers-reduced-motion`.

### Utilities
8 tilt/rotation classes, text alignment, transforms, truncation, screen-reader only.

## Browser Support

Modern browsers: Chrome 90+, Firefox 90+, Safari 15+. SVG filters require modern rendering engines.

## License

MIT
