# Project Notes

## Structure
- `index.html` contains the homepage, CSS, and small vanilla JavaScript interactions.
- `publications.html` is a standalone responsive Publications & Media page with category filters and links to original third-party sources.
- `public/images/` contains the supplied portrait, speaking photo, and GHAA graphics.
- Vercel serves the repository root as a static site. No build step or framework is required.

## Decisions
- Keep changes dependency-free and scoped to the single-page source.
- Main navigation labels stay on one line on small screens.
- External profile and contact links use clean text labels without decorative arrow glyphs.
- The homepage navigation links to `publications.html`; the publications page links back to homepage sections and labels its content as a selected reference list, not an exhaustive catalogue.
- The homepage hero uses the new professional barrister portrait from `public/images/Professional Barrister Portrait in Law Office.png`, fitted with `object-fit: contain` so the photo itself is not cropped.
- The gallery contains seven slides: three new speaking/event photographs, a new chambers portrait, the existing speaking photograph, and the two existing GHAA graphics. The slideshow uses a soft fade/short slide transition with Previous/Next and direct slide indicators, a 3.5-second interval, and no visible pause button. Autoplay pauses while hovered or focused.
- New gallery images use lazy loading and async decoding; the hero image is prioritized for loading.
- Respect `prefers-reduced-motion` by disabling autoplay/animation where possible; pause autoplay while the gallery is hovered or focused.
- WhatsApp remains a click-to-open link with a prefilled message. The visitor must send the message themselves.

## Fragile areas / checks
- All CSS and JavaScript are embedded in `index.html`; inspect script syntax and mobile media queries after edits.
- Verify the WhatsApp URL and social/profile destinations remain intact.
- Publications page: check external source URLs, filter categories, mobile card layout, navigation links, and third-party/legal-record disclaimer.
- Check hero portrait fit, gallery slide visibility and fade transition, Previous/Next and direct indicators, 3.5-second autoplay, hover/focus pause, and reduced-motion behaviour.
- Review legal profile text and Bar Council of India compliance separately before public promotion.
