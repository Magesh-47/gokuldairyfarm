# Assets

Local asset folder for the Gokul Dairy Farm site.

```
assets/
├── images/   logo, photos, backgrounds, product shots
│   └── testimonials/   customer portraits
└── videos/   hero + story background videos (.mp4)
```

Referenced from `index.html` with relative paths, e.g.
`<img src="assets/images/about-pasture.jpg" alt="...">`.

## Logo

`logo.png` is the original supplied artwork: a 1254×1254 lockup on an opaque
white background. It is kept as the master and is **not referenced by the
page** — the three files below are derived from it.

The white background was removed with a border flood-fill rather than a
"make white transparent" pass, because the cow drawing contains white areas
(forehead tuft, muzzle, front legs, sunglasses highlights) that a naive
threshold would have punched straight through.

| File | Size | Used at |
| --- | --- | --- |
| `logo.png` | 1254×1254 | master artwork, unreferenced |
| `logo-mark.png` | 512×436 | navbar, beside the live text wordmark |
| `logo-full.png` | 720×693 | footer, 200px wide |
| `favicon.png` | 256×256 | `<link rel="icon">` + apple-touch-icon |

`logo-mark.png` is the badge only (cow + arc + hooves, cropped above the
wordmark). The navbar keeps rendering "GOKUL / Dairy Farm" as live text, so
the badge is marked `alt=""` — the adjacent text already names the brand, and
a screen reader would otherwise announce it twice.

**The full lockup only works on light backgrounds.** Its wordmark is dark
green and effectively disappears on `--forest`. The footer is `--cream-deep`,
so it is fine there; do not move it onto a dark panel without a light variant.

## Photo & video map

All media is local — the page makes no external image or video requests.
Original Pexels IDs are kept below for provenance and re-download.
Each file was pulled at the width the page requests, listed as `w`.

### Videos — `assets/videos/`

| File | Used at | w | Pexels source |
| --- | --- | --- | --- |
| `hero-pasture.mp4` | Hero background | 1920 | video-files/855340 |
| `farm-story.mp4` | Farm story frame | 2560 | video-files/35011737 |

### Images — `assets/images/`

| File | Section | w | Pexels ID |
| --- | --- | --- | --- |
| `hero-poster.jpg` | Hero video poster | 1920 | videos/855340 |
| `about-pasture.jpg` | About | 1200 | 254178 |
| `exp-01-cows-grazing.jpg` | Farm Experience 01 | 900 | 34238253 |
| `exp-02-morning-milking.jpg` | Farm Experience 02 | 900 | 8064207 |
| `exp-03-green-pastures.jpg` | Farm Experience 03 | 900 | 5210272 |
| `exp-04-farmers-at-work.jpg` | Farm Experience 04 | 900 | 13981228 |
| `exp-05-milk-collection.jpg` | Farm Experience 05 | 900 | 5947086 |
| `product-milk.jpg` | Product — Fresh Milk | 800 | 5946742 |
| `product-curd.jpg` | Product — Curd | 800 | 12042271 |
| `product-paneer.jpg` | Product — Paneer | 800 | 11281331 |
| `product-ghee.jpg` | Product — Ghee | 800 | 8611766 |
| `farm-story-poster.jpg` | Story video poster | 1600 | videos/35011737 |
| `cta-golden-hour.jpg` | Final CTA | 1920 | 8156811 |

### Testimonial portraits — `assets/images/testimonials/`

| File | Person | w | Pexels ID |
| --- | --- | --- | --- |
| `anjali-menon.jpg` | Anjali Menon | 160 | 34786869 |
| `rakesh-patil.jpg` | Rakesh Patil | 160 | 2324638 |
| `fatima-sheikh.jpg` | Fatima Sheikh | 160 | 26844139 |
| `vikram-nair.jpg` | Vikram Nair | 160 | 4390632 |

## Notes

- **Total weight is ~38.5 MB, and the two videos are 36.6 MB of that.** Pexels
  was absorbing that bandwidth before; now the host does, and the hero video
  blocks nothing but does compete for bandwidth on first paint. Worth
  re-encoding both to a lower bitrate (or a 720p variant) before production,
  and adding a `.webm` source alongside each `.mp4`.
- The portraits are 160px wide because that is what the markup requested from
  Pexels. They will look soft on retina displays — re-pull at 320px and they
  sharpen with no layout change.
- Prefer `.webp` over `.jpg` for the photos where browser support allows — the
  same crops typically land 25–35% smaller.
- Pexels content is free for commercial use without attribution, but confirm
  the license on each photo page before shipping to production.
- `logo.png` (1.27 MB) is the unreferenced master. It can be moved out of
  `assets/` entirely if you keep the source artwork elsewhere.
- `image.png` is an unused pasture photo — nothing in the page references it.
