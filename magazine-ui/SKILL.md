---
description: Recreate the Blue STEAM / Blueprint Zine visual style of
  the Robotics & IoT HCMUS editorial page. Use when an agent needs to
  build or restyle a content-focused webpage with a technical magazine,
  student-club, or educational STEAM identity.
name: blue-steam-magazine-ui
---

# Blue STEAM Magazine UI Style

## Purpose

This skill defines a reusable visual language for reproducing the
supplied **Blue STEAM / Blueprint Zine** webpage style. The reference is
an editorial page for CLB Robotics & IoT HCMUS.

The style should feel like a blend of:

-   an engineering blueprint notebook;
-   a polished student science magazine;
-   a handmade editorial zine with paper, tape, stickers, and
    annotations.

The result should be energetic and tactile, but still readable,
structured, and credible. Avoid turning it into a generic corporate
dashboard, a plain documentation page, or a childish cartoon interface.

## 1. Design principles

1.  **Blueprint as the canvas:** use a very pale blue paper background
    with a subtle, evenly spaced technical grid.
2.  **Editorial paper as the content surface:** place the main reading
    content on a white, rounded, outlined paper sheet.
3.  **Bold, physical edges:** use dark outlines and hard offset shadows
    to create a cut-paper / printed-zine effect.
4.  **Blue is the identity:** cobalt, cerulean, sapphire, and sky blue
    provide hierarchy. Keep most body text dark slate for legibility.
5.  **Highlight meaning, not everything:** use sticker-like treatments
    for dates, acronyms, names, awards, and key concepts. Ordinary prose
    remains calm.
6.  **Human-made details:** add restrained washi-tape strips, wavy
    underlines, small rotations, mono labels, and occasional handwritten
    accents.
7.  **Readable first:** decoration must never compromise line length,
    contrast, spacing, responsive behavior, or text selection.

## 2. Color system

Use these reference tokens as the default palette.

  Token                 Hex         Intended use
  --------------------- ----------- -----------------------------------------------
  `cobalt`              `#1D4ED8`   Primary brand blue, important labels, buttons
  `cerulean`            `#0284C7`   Secondary blue, accents, links, borders
  `sapphire`            `#1E3A8A`   Deep blue emphasis and strong headings
  `signal`              `#7DD3FC`   Bright sticker/highlight background
  `signal-foreground`   `#0F172A`   Text on signal-blue highlights
  `breakout` / `ink`    `#0F172A`   Strong outlines and primary text
  `paper`               `#F4F8FC`   Main page background
  white                 `#FFFFFF`   Editorial paper surface
  slate-800             `#1E293B`   Main body copy
  slate-600             `#475569`   Secondary copy
  sky-50                `#F0F9FF`   Soft blue panels
  sky-100               `#E0F2FE`   Highlight panels
  sky-200               `#BAE6FD`   Fine separators and borders

### Color rules

-   Keep the page predominantly pale, white, and dark-ink, with blue as
    the accent.
-   Use cobalt for primary emphasis and cerulean for secondary emphasis.
-   Use sapphire sparingly for high-contrast emphasis.
-   Signal blue is for sticker-like highlights, not large blocks of body
    copy.
-   Do not introduce unrelated saturated colors unless the content
    genuinely requires them.
-   Maintain strong text/background contrast.

## 3. Typography

Use the following font roles when web fonts are available:

  -----------------------------------------------------------------------
  Role                    Typeface                Usage
  ----------------------- ----------------------- -----------------------
  Main sans               **Be Vietnam Pro**      Body copy and general
                                                  interface

  Display / heading       **Space Grotesk**       Strong headings and
  support                                         compact display text

  Technical mono          **JetBrains Mono**      Metadata, dates,
                                                  acronyms, labels,
                                                  buttons, tags

  Handwritten accent      **Patrick Hand**        Rare expressive phrases
                                                  or annotations
  -----------------------------------------------------------------------

Suggested font loading:

``` html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Be+Vietnam+Pro:ital,wght@0,400;0,500;0,600;0,700;0,800;0,900;1,500&family=JetBrains+Mono:wght@500;700;800&family=Patrick+Hand&family=Space+Grotesk:wght@600;700&display=swap" rel="stylesheet">
```

Fallbacks:

-   sans: `Be Vietnam Pro`, `Space Grotesk`, system sans-serif;
-   mono: `JetBrains Mono`, ui-monospace, monospace;
-   accent: `Patrick Hand`, cursive.

For Vietnamese content, verify that all diacritics render correctly. If
external fonts cannot load, use a robust system sans-serif fallback
rather than a decorative font.

### Type scale and rhythm

-   Body copy: approximately `1.06rem` on small screens and `1.16rem` on
    wider screens.
-   Body line height: approximately `1.9` to `1.95`.
-   Metadata: `0.7rem` to `0.8rem`, usually monospace.
-   Inline technical highlights: around `0.9em` to `0.95em`, often bold
    monospace.
-   Headings should be bold and compact, with clear separation from body
    copy.

Avoid long passages in all caps. Reserve uppercase monospace for short
editorial metadata and identifiers.

## 4. Page background and texture

Use a pale blue background with a subtle blueprint grid.

``` css
.bg-blueprint-grid {
  background-color: #F4F8FC;
  background-image:
    linear-gradient(to right, rgba(29, 78, 216, 0.065) 1px, transparent 1px),
    linear-gradient(to bottom, rgba(29, 78, 216, 0.065) 1px, transparent 1px);
  background-size: 28px 28px;
}
```

Guidelines:

-   Grid spacing should be around `28px`.
-   Grid lines should be low contrast; they are texture, not content.
-   Keep the background fixed or naturally scrolling according to the
    page layout; do not let the grid reduce readability.
-   Avoid heavy noise, gradients, or photographic backgrounds.

## 5. Layout architecture

### Overall structure

For a content-led editorial page, use this hierarchy:

1.  A compact sticky top bar.
2.  A centered main column with a maximum width around `56rem`
    (`max-w-4xl`).
3.  One dominant white editorial article sheet.
4.  A small metadata header inside the article.
5.  The content body, organized into readable paragraphs or sections.
6.  A quiet footer stamp with organization identity and topic tags.

### Header

-   Sticky at the top (`position: sticky; top: 0`).
-   Pale paper background with slight transparency and backdrop blur.
-   Dark 2px bottom border.
-   Centered inner row, maximum width matching the article.
-   Left: compact brand mark in a slightly rotated square with cobalt
    fill, dark outline, and small hard shadow.
-   Beside it: uppercase monospace organization label and a smaller
    muted subtitle.
-   Right: one clear utility action, styled as a tactile button.

Keep the header compact. On narrow screens, allow the text to wrap or
truncate gracefully without hiding the primary action.

### Main article sheet

-   White surface.
-   Rounded corners around `1.5rem`.
-   Dark 2px border.
-   Generous padding: approximately `1.5rem` on mobile, `2.5rem` to
    `3.5rem` on larger screens.
-   Hard cobalt offset shadow, approximately `6px 6px 0`.
-   Position relative so tape decorations can sit partly outside its top
    edge.
-   Keep decorative elements behind or outside the text flow.

Example:

``` css
.article-sheet {
  position: relative;
  background: #fff;
  border: 2px solid #0F172A;
  border-radius: 1.5rem;
  box-shadow: 6px 6px 0 #1D4ED8;
}
```

### Editorial metadata row

Place a compact metadata strip near the top of the sheet:

-   flex row with wrapping;
-   dashed pale-blue bottom separator;
-   uppercase mono issue label on the left;
-   small sky-tinted outlined institutional tag on the right;
-   optional small animated status dot.

Keep metadata visually secondary to the actual article title or content.

### Footer stamp

-   Dashed pale-blue top separator.
-   Small uppercase monospace organization label.
-   Compact topic tags such as `#STEAM`, `#ROBOTICS`, and `#IOT`.
-   Muted slate text and restrained spacing.

## 6. Signature visual components

### A. Hard zine shadows

Use crisp, unblurred, offset shadows rather than soft modern UI shadows.

``` css
.shadow-zine {
  box-shadow: 6px 6px 0 #0F172A;
}
.shadow-zine-sm {
  box-shadow: 3px 3px 0 #0F172A;
}
.shadow-zine-cobalt {
  box-shadow: 6px 6px 0 #1D4ED8;
}
.shadow-zine-cerulean {
  box-shadow: 5px 5px 0 #0284C7;
}
```

Use these on the article sheet, brand badge, key buttons, and selected
sticker highlights. Do not apply a hard shadow to every element.

### B. Washi tape

Use small translucent blue strips attached to the top edge of the
article sheet. Slightly rotate them in opposite directions.

``` css
.tape-blue {
  background: rgba(125, 211, 252, 0.72);
  backdrop-filter: blur(2px);
  border: 1px solid rgba(2, 132, 199, 0.25);
  box-shadow: 0 2px 4px rgba(15, 23, 42, 0.08);
}
```

Tape is decorative only:

-   use `pointer-events: none`;
-   hide or simplify some strips on small screens;
-   never overlap important text or controls.

### C. Sticker highlights

Use inline, compact labels to emphasize selected concepts.

Common forms:

-   Signal-blue sticker: dark text, dark border, slight rotation, hard
    shadow.
-   Cobalt sticker: white text, cobalt fill, compact mono typography.
-   Cerulean sticker: white text, cerulean fill.
-   Pale-blue outlined sticker: cobalt or sapphire text on
    sky-50/sky-100.
-   White date sticker: dark border, cobalt mono text, small hard
    shadow.

Example:

``` html
<span class="inline-block -rotate-1 rounded-lg border-2 border-[#0F172A]
             bg-[#7DD3FC] px-2 py-0.5 font-mono text-[0.9em]
             font-extrabold text-[#0F172A] shadow-[3px_3px_0_#0F172A]">
  JULY 2015
</span>
```

Do not turn every noun into a sticker. Use highlights selectively for:

-   dates and milestones;
-   acronyms and named programs;
-   technical domains;
-   awards and achievements;
-   important organizations;
-   a small number of key phrases.

### D. Wavy underlines

Use wavy cobalt or cerulean underlines for phrases that deserve emphasis
without becoming a badge.

``` css
.wavy-cobalt {
  text-decoration-line: underline;
  text-decoration-style: wavy;
  text-decoration-color: #1D4ED8;
  text-decoration-thickness: 2px;
  text-underline-offset: 4px;
}
```

A cerulean variant uses `#0284C7`. Keep the underline offset and
thickness consistent.

### E. Paragraph treatments

Vary paragraph presentation sparingly to create an editorial rhythm:

1.  **Plain paragraph:** default reading flow.
2.  **Side-rule paragraph:** a 4px cerulean left border with additional
    left padding.
3.  **Soft callout paragraph:** rounded corners, thin sky-200 border,
    and a sky-50 translucent background.
4.  **Achievement panel:** pale blue gradient, dark outline, hard small
    shadow, and one or two key stickers.

Do not put every paragraph in a card. The contrast between plain prose
and occasional featured panels is essential.

### F. Handwritten accent

Use Patrick Hand only for a short expressive phrase or a small
annotation. It should be an occasional human touch, not the primary body
font.

## 7. Interaction and motion

### Hover behavior

Sticker-like elements may use a small springy hover pop:

``` css
.zine-pop {
  display: inline-block;
  transition:
    transform 0.22s cubic-bezier(0.34, 1.56, 0.64, 1),
    box-shadow 0.2s ease,
    background-color 0.2s ease;
}
.zine-pop:hover {
  transform: translateY(-2px) scale(1.04);
}
```

-   Keep motion subtle and quick.
-   Do not make plain body text jump around.
-   Respect `prefers-reduced-motion`.
-   Ensure hover effects do not obscure adjacent text or cause layout
    instability.

### Buttons

Buttons should look like physical zine labels:

-   rounded-xl corners;
-   2px dark outline;
-   compact bold monospace label;
-   hard small shadow;
-   signal-blue background with dark text;
-   hover: move upward slightly and shift to a lighter sky blue;
-   active: return toward the original position.

Provide visible focus states and keyboard accessibility.

### Copy-text action

If the page includes a "copy text" action, it should copy the clean
textual content, not decorative markup:

1.  Select the intended article content container.
2.  Extract paragraph text in document order.
3.  Normalize repeated whitespace within each paragraph.
4.  Join paragraphs with a blank line.
5.  Use the Clipboard API where available, with a suitable fallback if
    required.
6.  Announce success accessibly, such as through a live status message.
7.  Restore the button label after a short confirmation state.

Do not silently copy hidden metadata, decorative labels, or unrelated
page content. Handle clipboard failure gracefully.

### Scrollbar

A custom cobalt scrollbar is optional and should be subtle. Never depend
on a custom scrollbar for navigation or usability.

## 8. Responsive behavior

The page must work well from mobile to desktop.

-   Keep the content column centered and fluid.
-   Use `width: 100%` with a maximum width around `56rem`.
-   Reduce article padding on small screens.
-   Let metadata and footer rows wrap.
-   Hide one or more decorative tape strips on narrow screens.
-   Avoid horizontal overflow from rotated stickers or shadows.
-   Keep inline stickers short enough to wrap naturally.
-   Maintain comfortable body line length and generous line height.
-   Ensure buttons remain large enough to tap.
-   Do not shrink body text excessively to fit a fixed layout.

## 9. Accessibility and content integrity

-   Use semantic landmarks: `header`, `main`, `article`, and `footer`
    where appropriate.
-   Keep text contrast strong.
-   All interactive elements must be keyboard accessible and have
    visible focus states.
-   Decorative tape and visual flourishes should be hidden from
    assistive technology.
-   Do not communicate meaning through color alone.
-   Respect reduced-motion preferences.
-   Preserve the source content accurately when restyling an existing
    page. Do not rewrite, summarize, or omit text unless explicitly
    requested.
-   Maintain correct Vietnamese diacritics and language metadata
    (`lang="vi"` for Vietnamese pages).
-   Ensure text remains selectable and copyable.

## 10. Implementation guidance

The reference implementation uses Tailwind CSS with custom theme tokens.
An agent may use Tailwind, plain CSS, CSS modules, or another framework,
provided the rendered result follows the same visual system.

### Tailwind configuration example

``` js
tailwind.config = {
  theme: {
    extend: {
      colors: {
        cobalt: '#1D4ED8',
        cerulean: '#0284C7',
        sapphire: '#1E3A8A',
        signal: '#7DD3FC',
        'signal-foreground': '#0F172A',
        breakout: '#0F172A',
        paper: '#F4F8FC',
        ink: '#0F172A',
      },
      fontFamily: {
        sans: ['"Be Vietnam Pro"', '"Space Grotesk"', 'sans-serif'],
        mono: ['"JetBrains Mono"', 'monospace'],
        accent: ['"Patrick Hand"', 'cursive'],
      },
      boxShadow: {
        zine: '6px 6px 0px 0px #0F172A',
        'zine-sm': '3px 3px 0px 0px #0F172A',
        'zine-cobalt': '6px 6px 0px 0px #1D4ED8',
        'zine-cerulean': '5px 5px 0px 0px #0284C7',
      },
    },
  },
};
```

### Suggested component map

  -----------------------------------------------------------------------
  Component                           Visual responsibility
  ----------------------------------- -----------------------------------
  `SiteHeader`                        Sticky paper header, club mark,
                                      identity, utility action

  `BrandMark`                         Rotated cobalt square, dark border,
                                      hard shadow

  `EditorialSheet`                    White article surface, dark
                                      outline, cobalt shadow

  `WashiTape`                         Decorative translucent strips on
                                      sheet edge

  `IssueMeta`                         Mono issue label and institutional
                                      tag

  `EditorialBody`                     Readable prose with controlled
                                      paragraph rhythm

  `Sticker`                           Inline highlighted date, acronym,
                                      concept, or achievement

  `WavyEmphasis`                      Wavy-underlined phrase

  `FeatureParagraph`                  Soft callout or achievement
                                      paragraph

  `EditorialFooter`                   Dashed separator, institutional
                                      stamp, topic tags

  `CopyTextButton`                    Copies clean article text and
                                      reports status
  -----------------------------------------------------------------------

Keep content and presentation separate. Prefer reusable components or
utility classes over repeating large inline style strings.

## 11. Do and don't checklist

### Do

-   [ ] Use the pale blueprint grid as the page canvas.
-   [ ] Center one dominant white editorial sheet.
-   [ ] Use dark 2px outlines and hard offset shadows.
-   [ ] Use cobalt and cerulean as the primary accents.
-   [ ] Use mono typography for technical metadata and compact labels.
-   [ ] Add a few rotated sticker highlights and restrained washi tape.
-   [ ] Vary paragraph treatments to create magazine-like pacing.
-   [ ] Preserve generous line height and readable contrast.
-   [ ] Make the layout responsive and accessible.
-   [ ] Preserve source text faithfully when the task is a restyle.

### Don't

-   [ ] Do not turn the page into a generic SaaS dashboard.
-   [ ] Do not use glassmorphism as the dominant visual language.
-   [ ] Do not replace the hard zine shadows with large blurry shadows.
-   [ ] Do not use a rainbow palette or unrelated accent colors.
-   [ ] Do not decorate every word or paragraph.
-   [ ] Do not use handwritten type for long passages.
-   [ ] Do not let tape, stickers, or rotations interfere with reading.
-   [ ] Do not sacrifice accessibility or mobile usability for visual
    fidelity.

## 12. Agent workflow

When asked to create or restyle a page using this skill:

1.  **Inspect the content and purpose.** Identify the page type,
    audience, language, primary content, and key actions.
2.  **Establish the canvas.** Apply the pale blueprint grid and centered
    content width.
3.  **Build the editorial shell.** Add the sticky header, brand mark,
    article sheet, metadata row, and footer.
4.  **Apply typography.** Use Be Vietnam Pro for reading, JetBrains Mono
    for metadata, Space Grotesk for display support, and Patrick Hand
    sparingly.
5.  **Create editorial hierarchy.** Keep most paragraphs plain; select a
    few meaningful phrases for stickers, wavy underlines, side rules, or
    featured panels.
6.  **Add interactions only when useful.** Implement real copy or
    navigation behavior; avoid decorative controls that do nothing.
7.  **Test responsive layouts.** Check narrow mobile, tablet, and
    desktop widths.
8.  **Check accessibility.** Verify contrast, keyboard focus, semantic
    structure, reduced motion, and Vietnamese glyph rendering.
9.  **Compare against the style checklist.** Confirm that the result
    reads as a technical magazine / blueprint zine rather than a generic
    web template.

## 13. Definition of done

A successful implementation should be recognizable through its
combination of:

-   pale blue engineering grid;
-   white, rounded editorial sheet;
-   dark outlines and crisp offset shadows;
-   cobalt / cerulean / signal-blue palette;
-   technical monospace labels;
-   selective sticker-like highlights and wavy underlines;
-   small washi-tape decorations;
-   magazine-like paragraph rhythm;
-   restrained, functional interactions.

The exact content and information architecture may change, but these
signature visual traits should remain consistent.
