# Apartments Villa Amfora — website

Static, single-page site (`index.html`, vanilla HTML/CSS/JS). Croatian by default, English via the HR/EN switch.
No build step, no backend, no dependencies beyond Google Fonts and an OpenStreetMap embed.

## Run locally

```bash
npx serve .          # then open the printed URL
```

Opening `index.html` directly also works.

## Deploy (Vercel)

Import the folder as a static project (framework preset: "Other", no build command).
`vercel.json` sets cache headers for `assets/img/`. `.vercelignore` keeps `_backup/` out of the deployment.

## Before launch — fill in `CONFIG` in `index.html`

Search for `SITE CONFIG` near the top of the `<script>`. Leave a value `''` while unknown —
the related feature hides or disables itself instead of pointing somewhere wrong.

| Key | What to enter | While empty |
|---|---|---|
| `whatsappNumber` | Owner's WhatsApp number, digits only, international format, no `+`, e.g. `385912345678` | "Send via WhatsApp" is disabled; a demo note and "Preview message" are shown |
| `email` | Owner's inquiry e-mail address | "Send by e-mail" is disabled (unless `formEndpoint` is set) |
| `formEndpoint` | Optional. A form service URL that accepts JSON POST (e.g. Formspree `https://formspree.io/f/xxxx`) | E-mail uses a `mailto:` link that opens the guest's own mail app |
| `bookingUrl` | The **exact** Booking.com listing, e.g. `https://www.booking.com/hotel/hr/<slug>.html` — never a search URL | All Booking.com links stay hidden |
| `unitPhotos` | Owner-confirmed photo per unit, e.g. `{ studio: 18, '1br-balcony': 54 }` (unit keys are in `UNITS`) | Each unit shows an illustrative villa photo labelled "Villa photo — not necessarily this unit" |

Also, once the production domain is known (see the comment in `<head>`):
- add `<link rel="canonical" href="https://DOMAIN/">`
- make `og:image` absolute: `https://DOMAIN/img40.jpg`

## How the inquiry form works

- Guest picks a unit (or arrives pre-selected from a unit's "Request a reservation" button), dates, guests, name and contact.
- Validation: check-in not in the past, check-out after check-in, at least 1 adult, valid e-mail or phone.
- **WhatsApp**: opens `https://wa.me/<number>?text=<prepared message>`. Nothing is sent until the guest presses Send in WhatsApp — the page says so.
- **E-mail**: with `formEndpoint`, POSTs JSON and reports success only after the service answers 2xx; otherwise opens a `mailto:` draft.
- No availability is shown or implied; no payments; no guest data is stored (only the language preference is kept in `localStorage`).
- If a form service is used, the owner should list it in their privacy notice. GDPR compliance of the full setup has **not** been verified.

## Information still needed from the owner

1. WhatsApp number and/or inquiry e-mail (or a form-service account).
2. Exact Booking.com listing URL (if Booking.com should stay as a secondary option).
3. Production domain.
4. Which photos belong to which unit (see `IMAGE-MANIFEST.md`) — and confirmation of the photo-unit guesses noted there.
5. Number of physical units per category (the site says "six types", not "six apartments").
6. Exact address (the map deliberately shows only the wider Novalja area).
7. Confirmation that the Booking.com rating (9.7 / 11 reviews, October 2026) is still current.

## Files

- `index.html` — the site
- `assets/img/` — optimised WebP copies (`imgN.webp` 1024 px, `imgN-640.webp`); originals `imgN.jpg` are untouched in the root
- `IMAGE-MANIFEST.md` — photo review, placements, exclusions
- `_backup/` — previous versions of `index.html`
