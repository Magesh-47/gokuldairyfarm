# Assets

Local asset folder for the Gokul Dairy Farm site.

```
assets/
├── images/   photos, backgrounds, product shots, portraits
├── videos/   hero + story background videos (.mp4/.webm)
├── icons/    favicon, logo marks, standalone SVGs
├── fonts/    self-hosted webfonts (.woff2)
├── css/      stylesheets, if the inline <style> is ever split out
└── js/       scripts, if the inline <script> is ever split out
```

Reference from `index.html` with relative paths, e.g.
`<img src="assets/images/about-pasture.jpg" alt="...">`.

## Remote assets currently in use

Every image and video in the page is still hot-linked from Pexels. To go
fully local, download each into `assets/` under the suggested name and swap
the `src`/`poster` attribute. Suggested names below.

### Videos — `assets/videos/`

| Line | Suggested name | Source |
| --- | --- | --- |
| 734 | `hero-pasture.mp4` | videos.pexels.com/video-files/855340/855340-hd_1920_1080_25fps.mp4 |
| 922 | `farm-story.mp4` | videos.pexels.com/video-files/35011737/14832019_2560_1440_30fps.mp4 |

### Video posters — `assets/images/`

| Line | Suggested name | Pexels ID |
| --- | --- | --- |
| 733 | `hero-poster.jpg` | videos/855340 |
| 921 | `farm-story-poster.jpg` | videos/35011737 |

### Section images — `assets/images/`

| Line | Section | Suggested name | Pexels ID |
| --- | --- | --- | --- |
| 763 | About | `about-pasture.jpg` | 254178 |
| 807 | Farm Experience 01 | `exp-01-cows-grazing.jpg` | 34238253 |
| 811 | Farm Experience 02 | `exp-02-morning-milking.jpg` | 8064207 |
| 815 | Farm Experience 03 | `exp-03-green-pastures.jpg` | 5210272 |
| 819 | Farm Experience 04 | `exp-04-farmers-at-work.jpg` | 13981228 |
| 823 | Farm Experience 05 | `exp-05-milk-collection.jpg` | 5947086 |
| 842 | Product — Fresh Milk | `product-milk.jpg` | 5946742 |
| 847 | Product — Curd | `product-curd.jpg` | 12042271 |
| 852 | Product — Paneer | `product-paneer.jpg` | 11281331 |
| 857 | Product — Ghee | `product-ghee.jpg` | 8611766 |
| 982 | Final CTA | `cta-golden-hour.jpg` | 8156811 |

### Testimonial portraits — `assets/images/testimonials/`

| Line | Person | Suggested name | Pexels ID |
| --- | --- | --- | --- |
| 945 | Anjali Menon | `anjali-menon.jpg` | 34786869 |
| 953 | Rakesh Patil | `rakesh-patil.jpg` | 2324638 |
| 961 | Fatima Sheikh | `fatima-sheikh.jpg` | 26844139 |
| 969 | Vikram Nair | `vikram-nair.jpg` | 4390632 |

## Notes

- Pexels URLs carry `?auto=compress&cs=tinysrgb&w=…`. Local copies lose that
  resizing, so export at the width the page requests (1920 hero/CTA, 1600
  story poster, 1200 about, 900 experience cards, 800 products, 160 portraits)
  and keep a `@2x` variant if you want retina sharpness.
- Prefer `.webp` over `.jpg` for photos where browser support allows — the
  same crops typically land 25–35% smaller.
- Pexels content is free for commercial use without attribution, but confirm
  the license on each photo page before shipping to production.
