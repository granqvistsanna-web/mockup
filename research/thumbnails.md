# Framer Marketplace thumbnails — what works

Researched 2026-10-29 in the live Marketplace grid (framer.com/marketplace/templates): the **Trending** tab (~20) and **Best** (~44, "Last Month"), about 50 unique templates. The Marketplace no longer has a separate Featured / Staff Picks shelf. `/marketplace/` redirects to the templates grid, so Trending and Best are the curated views. Thumbnails show at about 279×209 px in a 4-column grid on a near-black (#111) page.

## Confirmed size

- **Ratio: 4:3, every time.** I measured the original upload of 28 thumbnails from the Best tab and all 28 were exactly 4:3:
  - 1600×1200: 18
  - 3200×2400: 6
  - 2800×2100, 2400×1800, 2000×1500: 1 each
  - one video (TITARVL, also 4:3)
- The listing page shows 4 gallery images, all 4:3 (Consulta, for example: 2800×2100). The first image is also the page's `og:image`.
- **Recommended export: 1600×1200** (the de-facto minimum), or **3200×2400** for 2× sharpness.
- **Source:** Framer doesn't publish a pixel spec. Its [Template best practices](https://www.framer.com/help/articles/template-best-practices/) page only says preview images must "accurately represent the template" and be web-optimized. The Academy lesson and the community guideline post (which now redirects) give no numbers either. So the size above is measured, not documented. Video thumbnails are also accepted (served by Mux).
- The tool's existing `"4:3"` size fits, so **no new `size` value is needed**. If presets should export the exact pixels, add a canvas size of 1600×1200 (or 3200×2400) for `"4:3"`.

## Patterns, ranked by how often they appear (~50 thumbnails)

| # | Pattern | Share | Tool can do it? |
|---|---|---|---|
| 1 | **Hero only.** The thumbnail shows the first viewport, never a long scroll | ~95% | yes (`scroll: 0`) |
| 2 | **Floating browser window on a background**, padded 6–12%, soft shadow, rounded corners | ~40% | yes |
| 3 | **Bare full-bleed hero.** No frame, the site *is* the thumbnail, usually a huge wordmark or photo (Arpeggio, Jett, Rec, Monolit, Bungee) | ~24% | partly: browser with `pad 0` still draws chrome. **Needs a "none" frame** |
| 4 | **Desktop monitor on a stand** (Pro Display / iMac style) on a grey studio backdrop (Powder, Nouva, Lateral, Asher Vale, Kai Marlow, Miles, Perspectiva, VSLPro) | ~22% | **no.** Laptop is the nearest. **Biggest missing layout** |
| 5 | **Text or badge on the thumbnail itself**: category pill ("Designer Portfolio"), tagline, product name, "LaunchNow" corner badge (Canvasfolio, Jett, Fantom, Platform, WaitlistKit, Sanjaya, Kora) | ~14% | **no.** Needs a text/label overlay |
| 6 | **3D tilt / perspective**, a window or monitor turned 10–25° (CreatorCut, Sanjaya, Spartan's, Metzger, Nolan Barret) | ~12% | yes (`tilt`) |
| 7 | **Collage of several pages or sections**, overlapping or stacked, often tilted (Nudge, Platform, Framewell, Sift, Titarvl) | ~10% | partly: `spread` does 3 flat screens. **Overlapping/stacked collage missing** |
| 8 | **Window bleeding off an edge.** It is bigger than the canvas and cropped at the bottom or right (Neiden, Tabfolio, Spartan's) | ~8% | **no.** Needs offset/scale beyond the canvas |
| 9 | **Video thumbnail** (RUSHES., Titarvl, Canvasfolio) | ~6% | no (out of scope) |
| 10 | **Laptop** (All Natural) | ~2% | yes |
| 11 | **Phone or desktop + phone pair** as the main thumbnail | ~0% (phones appear *inside* hero designs, not as frames) | yes, but better for gallery images 2–4 |

**Backgrounds** (for thumbnails that have one):
- neutral grey/off-white solid or soft gradient: ~35% (almost all monitor shots)
- colour gradient: ~25% (purple→pink, blue, teal, warm orange)
- blurred photo or the site's own hero, blurred: ~25% (Kora, Consulting, Firma, Amber)
- solid brand colour: ~15%

## Colour relationship

- The background **reuses the site's own accent or hero image**, so it reads as part of the brand: Kora's blurred flower, ProLab's orange, Firma's green, Amber's blue. It does not fight the site.
- Dark sites go on dark or blurred backgrounds. Light sites go on light grey or pastel gradients. High contrast between frame and background is rare. **The contrast that matters is against the near-black Marketplace page**, so light, warm or saturated backgrounds pop the most in the grid.

## What stands out at 279 px

1. **One giant word.** Wordmarks set at 20–40% of the thumbnail width (Arpeggio, Neiden, Jett, Rushes, Mugen, Monolit, Kai Marlow) are the most legible cards in the grid. Body copy is unreadable at this size.
2. **One strong colour field** (orange, saturated blue, purple gradient) beats a busy collage.
3. **A face or a big photo** in the hero.
4. **Less padding than you'd think.** Windows fill 75–90% of the width. Generous 20%+ padding makes the site too small to read.

## 8 examples worth copying

- [Arpeggio](https://www.framer.com/marketplace/templates/arpeggio/): bare hero, huge orange wordmark over a blue photo. Readable from across the room.
- [Consulta](https://www.framer.com/marketplace/templates/consulta/): light browser window on a soft purple→pink gradient, ~8% padding, gentle shadow. The cleanest "floating window" example.
- [Kora](https://www.framer.com/marketplace/templates/kora/): window over a blurred version of its own flower hero, so background and site feel like one piece. Small corner badge.
- [Lateral](https://www.framer.com/marketplace/templates/lateral/): dark site on a monitor-on-stand, grey studio photo. Premium "product shot" feel, matching its $129 price.
- [CreatorCut](https://www.framer.com/marketplace/templates/creatorcut/): dark window tilted in 3D on a near-black red-tinted background. Depth stands out in a flat grid.
- [Canvasfolio](https://www.framer.com/marketplace/templates/canvasfolio/): window on a violet gradient with a floating "Designer Portfolio" pill. The text label tells you the category at a glance.
- [Neiden](https://www.framer.com/marketplace/templates/neiden/): dark browser window filling the frame edge to edge, giant ñeiden wordmark. Almost bare, with just enough chrome to say "website".
- [Nudge](https://www.framer.com/marketplace/templates/nudge/): tilted collage of several colourful pages. Shows range, but harder to read small.
- Also: [ProLab](https://www.framer.com/marketplace/templates/prolab/) (solid orange brand backdrop), [Nouva](https://www.framer.com/marketplace/templates/nouva/) (monitor on a deep blue gradient).

## Missing from the tool, ranked by frequency

1. **Desktop monitor/display on a stand** layout (~22%)
2. **No-frame / bare** layout: just the screenshot with a radius, no chrome (~24%, but trivially close to existing)
3. **Text or label overlay**: pill tag, title, corner badge (~14%)
4. **Overlapping/stacked collage** of 3–5 pages, tilted (~10%)
5. **Offset/bleed**: let the frame run off an edge (~8%)
6. **Background from the screenshot itself** (blurred hero), if `blur` doesn't already do this (~25% of backgrounds)
7. Video export (~6%), probably out of scope
