# Landing Page Templates

Professional, conversion-focused landing page templates for client campaigns. Built with HTML + Tailwind CSS (CDN) — no build step, open directly in a browser.

---

## Templates

| Template | Location | Use Case |
|---|---|---|
| Simple Opt-in | `lead-gen/simple-optin/` | Email list building, lead magnets, free guides |
| Webinar Signup | `lead-gen/webinar-signup/` | Live or evergreen webinar registrations |
| Long-Form Sales | `sales/long-form-sales/` | Courses, coaching, digital products |
| VSL Page | `sales/vsl-page/` | Video sales letters with delayed CTA reveal |

---

## Quick Start

1. Open any `index.html` directly in a browser — no server needed.
2. Search for `[` in the file to find every placeholder. Replace with real content.
3. Swap the form `action="#"` with your form provider's endpoint (Mailchimp, ConvertKit, GoHighLevel, etc.).
4. Done.

---

## Customization Guide

### Colors
Each template has a `tailwind.config` block at the top of the file:
```js
tailwind.config = {
  theme: {
    extend: {
      colors: {
        brand: { ... },  // Primary color scale (50–900)
        accent: '#f59e0b',  // CTA / highlight color
      }
    }
  }
}
```
Change `brand` and `accent` hex values to match the client's brand. The rest of the page updates automatically.

### Fonts
Templates load Google Fonts at the top of each file via `<link>`. To change fonts:
1. Visit [fonts.google.com](https://fonts.google.com) and pick a display + body font.
2. Replace the `<link>` tag and update the CSS `font-family` declarations.

### Forms
All forms use `action="#" method="post"`. To connect a real form provider:
- **Mailchimp**: Replace `action="#"` with your Mailchimp embed URL.
- **ConvertKit**: Use their form embed code.
- **GoHighLevel / ClickFunnels**: Use their embedded form or redirect.

---

## Template-Specific Notes

### Webinar Signup — Countdown Timer
Edit this line in the `<script>` block at the bottom of the file:
```js
const webinarDate = new Date(2026, 3, 25, 19, 0, 0);
// Format: (YEAR, MONTH-1, DAY, HOUR-24hr, MIN, SEC)
// Month is 0-indexed: January=0, April=3, December=11
```

### VSL Page — CTA Reveal Delay
Edit this line in the `<script>` block:
```js
const CTA_DELAY_MS = 30000; // milliseconds (30000 = 30 seconds)
```
Set to `0` to show immediately. Match to your video length or a key moment in the pitch.

### Long-Form Sales — FAQ Accordion
The FAQ accordion is pure vanilla JS — no dependencies. Add more FAQ items by duplicating the `.faq-item` div block.

---

## Stack
- **CSS**: Tailwind CSS via CDN (`https://cdn.tailwindcss.com`)
- **Fonts**: Google Fonts (Inter + Sora)
- **Icons**: Heroicons SVG (inline)
- **JS**: Vanilla only (countdown timer, FAQ accordion, CTA reveal)
- **Forms**: Static HTML — swap `action="#"` for your provider

---

## File Structure
```
landing-page-templates/
├── README.md
├── lead-gen/
│   ├── simple-optin/index.html
│   └── webinar-signup/index.html
└── sales/
    ├── long-form-sales/index.html
    └── vsl-page/index.html
```
