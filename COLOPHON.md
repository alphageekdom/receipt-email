# Colophon

Notes on how this email was made &mdash; type, palette, tools, and references.

## Type

- **Caveat** (400, 700) &mdash; script-style display face for the "Sugar & Sprinkle" wordmark, section headings, and the pickup card title. Loaded from Google Fonts.
- **Quicksand** (400, 500, 600, 700) &mdash; body and UI face for everything else: greeting, order metadata, item names, totals, footer copy. Loaded from Google Fonts.
- **Arial / Helvetica** &mdash; system fallback for clients that block external font loads (most desktop Outlook versions).

An `<!--[if (gte mso 9)|(IE)]>` block forces Outlook into the Quicksand &rarr; Arial &rarr; Helvetica &rarr; sans-serif stack so the email doesn't drop back to Times New Roman.

## Palette

| Hex | Role |
| --- | --- |
| `#4a2c3a` | Plum &mdash; primary text and headings |
| `#d6336c` | Berry pink &mdash; CTA button, brand wordmark, accent links |
| `#ff7eb3` | Bright pink &mdash; section kickers and secondary accents |
| `#ffe4ec` | Cotton candy &mdash; brand block and pickup card backgrounds |
| `#f4ede4` | Cream &mdash; page background and summary card |
| `#2a8a5f` | Mint &mdash; discount value |
| `#f7d774` | Honey &mdash; confetti accent |
| `#a8e6cf` | Sage &mdash; confetti accent |
| `#c7b4f5` | Lilac &mdash; confetti accent |

## Layout

- 600 px outer email card on a cream page background
- Table-based layout with `role="presentation"` on every layout-only table
- Two responsive breakpoints: 600 px (tablet &rarr; mobile transition) and 480 px (small mobile fine-tune)
- Outlook 2007 &ndash; 2019 supported via VML (`<v:roundrect>` for the CTA pill) and `mso-*` properties throughout

## Tools

- **HTML / CSS** &mdash; hand-written, no framework
- **Liquid** &mdash; Shopify-style templating syntax for the dynamic source ([`template.html`](template.html))
- **VS Code** + Prettier + `@shopify/prettier-plugin-liquid`
- **macOS `sips`** for JPEG resizing and re-encoding
- **Chrome / Safari DevTools** Device Toolbar for responsive testing and screenshot capture
- **Netlify** for static hosting of the rendered preview

## Imagery

- Cupcake photography &mdash; _attribution to be added_
- Social icons (Instagram, TikTok, Pinterest, Facebook) &mdash; custom white-on-transparent PNGs in [`img/`](img/)
- Favicon set &mdash; 16&times;16, 32&times;32, `.ico`, and 180&times;180 Apple touch icon in [`img/`](img/)

## License

[MIT](LICENSE) &mdash; free to fork, learn from, and adapt.

---

Designed and built by [AlphaGeekdom](https://github.com/alphageekdom), April 2026.
