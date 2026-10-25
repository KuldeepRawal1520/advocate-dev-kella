# Project Notes

## Structure
- `index.html` contains the static one-page site, CSS, and small vanilla JavaScript interactions.
- `public/images/` contains the supplied portrait, speaking photo, and GHAA graphics.
- Vercel serves the repository root as a static site. No build step or framework is required.

## Decisions
- Keep changes dependency-free and scoped to the single-page source.
- Main navigation labels stay on one line on small screens.
- External profile and contact links use clean text labels without decorative arrow glyphs.
- The three supplied gallery images are shown one at a time in a 3D rotating slideshow with Previous/Next, direct slide indicators, a two-second interval, and a pause/play control.
- Respect `prefers-reduced-motion` by disabling autoplay/animation where possible; pause autoplay while the gallery is hovered or focused.
- WhatsApp remains a click-to-open link with a prefilled message. The visitor must send the message themselves.

## Fragile areas / checks
- All CSS and JavaScript are embedded in `index.html`; inspect script syntax and mobile media queries after edits.
- Verify the WhatsApp URL and social/profile destinations remain intact.
- Check gallery slide visibility, navigation controls, two-second autoplay, pause/resume, and reduced-motion behaviour.
- Review legal profile text and Bar Council of India compliance separately before public promotion.
