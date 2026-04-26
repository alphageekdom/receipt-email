# Colophon

How this email was built.

## Engineering

- HTML5 doctype, `lang="en"` on `<html>`
- Table-based layout
- Inline + embedded CSS in `<head>`
- MSO conditional comments
- VML `<v:roundrect>` CTA fallback for Outlook
- 600px max-width container
- Liquid templating (`{% for %}`, `{% if %}`, `{{ var }}`)
- No JavaScript

## Accessibility & resilience

- Alt text on every image
- `role="presentation"` on layout-only tables
- Web fonts (Quicksand, Caveat) with Arial / Helvetica fallbacks
- MSO font-family override forces the same stack in Outlook
- Decorative confetti hidden from Outlook via `<!--[if !mso]>`
- Mobile stacking via `@media (max-width: 600px)` and `@media (max-width: 480px)`
- View-online link in the utility strip

## Breakpoints

- 320px &mdash; small mobile
- 375px &mdash; iPhone standard
- 480px &mdash; small mobile (`@media`)
- 600px &mdash; email canonical (`@media`)
- 700px+ &mdash; desktop preview

## Targeted clients

- Gmail (web &middot; iOS &middot; Android)
- Apple Mail (macOS &middot; iOS)
- Outlook 365 (web)
- Outlook desktop 2007&ndash;2019 (Word engine)
- Yahoo Mail
