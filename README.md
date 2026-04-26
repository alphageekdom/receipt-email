# Sugar & Sprinkle — Order Receipt Email

A responsive transactional HTML email for a fictional cupcake bakery. Built as a portfolio piece to demonstrate email development fundamentals: table-based layout, inline-friendly CSS, mobile stacking, bulletproof CTA, and Liquid-style dynamic order data.

**Live preview:** [sugar-sprinkle-receipt.netlify.app](https://sugar-sprinkle-receipt.netlify.app/)

---

## Disclaimer

Fictional bakery receipt email created as an HTML email development project. All customer, order, pricing, and business details are sample data.

## Technical build note

Responsive transactional HTML email built with table-based layout, inline CSS, email-safe spacing, mobile fallbacks, accessible alt text, and Liquid-style dynamic order data.

## Email-safe features

- Table-based layout with `role="presentation"` on every layout table so screen readers skip them
- Email-safe spacing via `cellpadding` / `cellspacing` and nested tables, not CSS box-model
- No JavaScript dependency
- Mobile stacking via `@media (max-width: 600px)` and `@media (max-width: 480px)` &mdash; the order-meta 2&times;2 grid collapses, item cards reflow vertically, and padding tightens at the smallest breakpoint
- **Outlook (MSO) hardening:** VML `<v:roundrect>` fallback for the Track CTA so the button renders as a real pink pill in Outlook 2007&ndash;2019 instead of a blue underlined link; `mso-line-height-rule: exactly` on every script-font heading to defeat Outlook's leading bug; `mso-hide: all` preheader so Outlook strips the inbox-preview snippet from the visible body
- Liquid-style variables, a `{% for %}` item loop, and `{% if %}` blocks for a conditional discount row and a delivery-fee row that auto-hides for Pickup orders
- Accessible alt text on every content image, decorative confetti hidden from Outlook (where `position: absolute` is unsupported)
- `<style>` block in `<head>` for development; in production it would be pushed inline with juice / premailer to survive clients that strip head styles
- Transactional footer with explicit privacy and unsubscribe links

## Files

| File | Purpose |
| --- | --- |
| [`index.html`](index.html) | Rendered preview with realistic sample data — what the live demo serves. |
| [`template.html`](template.html) | Liquid source with `{{ }}` variables and `{% %}` control tags. Drop into a transactional email service (Shopify, Klaviyo, Postmark) and bind to real order data. |
| [`img/`](img/) | Cupcake photography, social icons, and favicon set. |

## Sample data

The values rendered in [`index.html`](index.html) correspond to this template payload:

```json
{
  "customer": {
    "first_name": "Maya"
  },
  "company": {
    "company_name": "Sugar & Sprinkle",
    "phone_number": "(626) 555-0148",
    "street": "124 Frosting Lane",
    "city": "Pasadena",
    "state": "CA",
    "zipcode": "91101"
  },
  "order": {
    "number": "1048",
    "placed_at": "April 25, 2026",
    "fulfillment_method": "Pickup",
    "payment_method": "Visa ending in 4242",
    "subtotal": "42.00",
    "discount": {
      "code": "SWEET5",
      "amount": "5.00"
    },
    "tax": "3.12",
    "total": "40.12",
    "modification_deadline": "1:30 PM",
    "pickup": {
      "date": "Today",
      "window": "3:00 PM – 4:00 PM"
    },
    "items": [
      {
        "name": "Strawberry Shortcake Dream",
        "flavor": "Vanilla bean cake, strawberry buttercream",
        "quantity": 4,
        "price": "16.00",
        "unit_price": "4.00",
        "image_url": "img/strawberry-shortcake-dream.jpg"
      },
      {
        "name": "Lemon Lavender Bliss",
        "flavor": "Lemon sponge, honey-lavender frosting",
        "quantity": 3,
        "price": "13.50",
        "unit_price": "4.50",
        "image_url": "img/lemon-lavender-bliss.jpg"
      },
      {
        "name": "Cookies & Cream Cloud",
        "flavor": "Chocolate cake, cookies-and-cream mousse",
        "quantity": 3,
        "price": "12.50",
        "unit_price": "4.17",
        "image_url": "img/cookies-and-cream-cloud.jpg"
      }
    ]
  }
}
```

## Tested preview widths

- 320 px — small mobile
- 375 px — standard mobile (iPhone 14/15)
- 414 px — large mobile
- 600 px — email container width
- 700 px+ — desktop preview

## Screenshots

### Desktop

![Desktop view — header, greeting, status ribbon, and order metadata](screenshots/desktop-hero.jpeg)

![Desktop view — item loop and totals summary](screenshots/desktop-summary.jpeg)

### Mobile (iPhone 12 Pro, 390 px)

| Header & order metadata | Item loop & totals | Pickup details & support |
| --- | --- | --- |
| ![Mobile — brand header, greeting, status ribbon, and order metadata stacked](screenshots/mobile-header.jpeg) | ![Mobile — three cupcake items with thumbnails and order summary](screenshots/mobile-items.jpeg) | ![Mobile — pickup card with When/Where, Track my order CTA, and support callout](screenshots/mobile-pickup.jpeg) |

## Local preview

```bash
# Open the rendered version directly
open index.html

# Or serve locally
npx serve .
```

To preview the Liquid source, run it through a Liquid renderer (e.g. the [Shopify Liquid CLI](https://shopify.github.io/liquid/)) bound to the sample data above.

## Credits

Designed and built by [AlphaGeekdom](https://github.com/alphageekdom).
