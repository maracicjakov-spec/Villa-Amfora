# Image manifest — Apartments Villa Amfora

All 75 supplied photographs (`img1.jpg`–`img75.jpg`, Booking.com exports, max 1024 px) were reviewed visually.
Originals are untouched in the project root. Optimised copies live in `assets/img/`:
`imgN.webp` (1024 px) and `imgN-640.webp` (640 px). The gallery data in `index.html` (`PHOTOS`) mirrors this file.

## Homepage placements

| Role | File | Notes |
|---|---|---|
| Hero | img40 | Pool, white pergola villa, olive tree, loungers — tells "villa with a pool" in one frame |
| Intro / architecture | img50 | White planes, pergola, exterior stair |
| Pool — main | img62 | Pool, garden, sculpted fountain, masonry grill |
| Pool — details | img44, img53, img36 | Pool from a terrace through an egg chair; loungers under olive; covered dining by pool |
| Terraces — main | img19 | Pergola terrace, striped shadows |
| Terraces — pair | img14, img59 | Mosaic + egg chair with sea glimpse; terrace overlooking the pool |
| Accommodation showcase | see below | One illustrative photo per category |
| Interiors strip | img2, img17, img55, img61 | Design language shared across units (labelled "photos show different units") |
| Location | img42 | Owner's aerial with marker showing the villa (town beach, harbour, Velebit) |
| Inquiry section | img46 | Pool with the sculpted fountain |
| og:image | img40.jpg | Needs absolute URL once a domain exists |

## Accommodation showcase — illustrative, not confirmed

Each category shows a villa photo of its *defining feature*, always labelled
"Fotografija vile — ne nužno ove jedinice / Villa photo — not necessarily this unit".
Once the owner confirms real unit photos, add them to `CONFIG.unitPhotos` and the label switches to "Photo of this unit".

| Unit key | Category | Illustrative photo | Why |
|---|---|---|---|
| `2br-terrace` | Two-bedroom with terrace | img37 | Terrace with mosaic table outside a living room |
| `2br-sea` | Two-bedroom with sea view | img10 | Terrace with sea view over the rooftops |
| `studio` | Studio | img18 | Open-plan room with kitchen, dining and bed behind a slat panel (possibly the studio itself — unconfirmed) |
| `1br-terrace` | One-bedroom with terrace | img51 | Kitchen opening onto a pergola terrace |
| `2br-first` | Two-bedroom, first floor | img35 | Façade showing the villa's upper floors |
| `1br-balcony` | One-bedroom with balcony | img54 | The only balcony photo (low-res video still; possibly this unit — unconfirmed) |

## Gallery categories (66 photos)

- **Vila i vrt / Villa & garden:** 35, 50, 49, 38, 36
- **Bazen / Pool:** 40, 62, 53, 44, 46
- **Terase / Terraces:** 10, 14, 19, 7, 59, 63, 37, 74
- **Boravak i kuhinja / Living & kitchen:** 17, 51, 33, 18, 39, 65, 1, 11, 60, 70, 8, 3, 48, 12, 43, 56, 58, 61, 64, 66, 4
- **Spavaće sobe / Bedrooms:** 2, 15, 9, 13, 68, 27, 34, 16, 21, 26, 31, 29, 30, 20, 32, 45, 22, 28, 52, 69
- **Kupaonice / Bathrooms:** 55, 5, 41, 67, 71
- **Okolica / Surroundings:** 42, 47 (aerials with the owner's location marker)

## Excluded

| File | Reason |
|---|---|
| img57 | Byte-identical duplicate of img56 |
| img73 | Near-duplicate of img62 (same pool/statue view, mostly foliage) |
| img6, img23, img24, img25 | Empty corridors / doorway peeks — weak on their own |
| img72 | Low-quality phone shot of a narrow balcony (img54, the better of the two, is used only as the balcony unit's illustration) |
| img75 | Low-quality phone shot of the street façade (wires, parked car) |

## Unit grouping — deliberately not applied

Interiors share one design language (marble-look floors, timber slat headboards, wire pendants, ochre curtains),
so units cannot be told apart reliably. Observed clusters, **unconfirmed**:

- Rust-orange sofa living rooms: 8, 11, 12, 17, 48, 56, 64 (likely several units)
- Honey/mustard sofa, open plan with bed behind slat panel: 18, 34, 39, 65 (possibly the studio, ground floor by the pool)
- Mustard sofa bed by pergola terrace (upper floor): 3, 33, 60, 51, 70
- Balcony: 54, 72

Because of this, no photo is presented as a specific unit. Ask the owner to map photos to units, then fill
`CONFIG.unitPhotos` in `index.html`.
