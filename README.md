[Arcen README.md](https://github.com/user-attachments/files/34804762/Arcen.README.md)
# Arcen

Brand site for Arcen, a furniture maker. Chairs built to order in solid
hardwood and natural fibres.

Static HTML, CSS and JavaScript. No build step, no dependencies, no framework.
Open `index.html` or serve the folder with any static host.

## Pages

| Page | File |
| --- | --- |
| Home | `index.html` |
| Shop | `shop.html` |
| Product | one page per piece, e.g. `arcen-chair.html` |
| Our Story | `story.html` |
| Support | `support.html` |
| Sign up | `signup.html` |

Product pages:

- `arcen-chair.html` — The Arcen Chair
- `cloud-chair.html` — The Cloud Chair
- `arc-chair.html` — The Arc Chair
- `muse-chair.html` — The Muse Chair
- `wave-lounger.html` — The Wave Lounger
- `halo-chair.html` — The Halo Chair
- `teak-lounger.html` — The Teak Lounger
- `vela-chair.html` — The Vela Chair
- `fern-chair.html` — The Fern Chair
- `aster-chair.html` — The Aster Chair
- `japanese-footstool.html` — Japanese Footstool
- `block-table.html` — The Block Table
- `lisbon-sofa.html` — The Lisbon Sofa

The shop accepts a filter in the query string: `shop.html?filter=new`,
`?filter=best`, or a category (`lounge`, `dining`, `stools`, `sofas`).

## Files

```
assets/site.css    every style, built on design tokens declared in :root
assets/site.js     nav, cart, filters, product options, scroll animation
assets/*.png       product photography, brand marks, social image
sitemap.xml        all 18 pages
robots.txt         open to crawlers
.nojekyll          tells GitHub Pages to serve the files as they are
```

## How it works

Each page is complete HTML — product copy, specifications and reviews are in
the markup, not assembled by script, so the site reads correctly with
JavaScript disabled and to search engines. `site.js` adds the behaviour on top:
the cart, the shop filters, the finish swatches, the gallery and the scroll
animation.

The cart lives in `localStorage` under `arcen-cart-v1`. It is per browser,
never leaves the page, and checkout ends at a front-end confirmation; wiring it
to a real checkout is the one piece of back end this site would need.

## Design

One olive ground (`#556b2f`) with translucent white cards. Syne for headings,
Poppins for text. Spacing comes from a single scale declared as custom
properties at the top of `site.css` — change `--gap`, `--sec` or `--head` there
and the whole site follows.

Motion is scroll-driven: sections reveal as they enter, the chair diagram draws
its callout lines, long statements fill word by word. Everything is disabled
under `prefers-reduced-motion`.

## Accessibility

Keyboard reachable throughout with a visible focus ring, a skip link, labelled
controls and live regions on the cart and filter counts. Tested from 320px to
desktop: no horizontal scroll, and touch targets at 36px or more.

## Editing the catalogue

Products are defined once, in the `CATALOGUE` array in `assets/site.js`. Each
entry carries its name, price, category, image, description, specifications and
reviews. The shop grid and the product pages are generated from it.

## Deploying

Any static host. Upload the contents of this folder — not the folder itself.

- **GitHub Pages** — push to a repository, then Settings, Pages, Deploy from a
  branch, `main`, `/ (root)`.
- **Netlify or Vercel** — drag the folder onto the drop zone, or connect the
  repository.
- **Your own server** — copy the files into the web root over FTP.
