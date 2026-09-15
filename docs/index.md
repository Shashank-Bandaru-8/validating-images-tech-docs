# TechDocs Image Loading Validation

This repo exists to reproduce a customer-reported issue: TechDocs pages that
reference the same SVG many times render partially, then fill in over several
seconds, because every `<img>` is fetched individually and techdocs static
assets are served without cache headers.

## Pages

- [Heavy Page](heavy-page.md) — 31 image references to 8 unique SVGs
  (mirrors the customer HAR: `data.svg` x12, `aws.svg` x10)
- [Light Page](light-page.md) — single reference per image, for comparison
- [Image links](image-links.md) — IDP-10939: valid vs unparseable image-wrapped hrefs

## What to observe

Open the Heavy Page in the IDP Docs tab with the network panel open and check:

1. Are the same SVGs fetched multiple times?
2. Are the fetches sequential or parallel?
3. What `Content-Type` and cache headers do the responses carry?
