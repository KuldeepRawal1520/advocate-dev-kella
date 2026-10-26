# Project Notes

## Structure
- `index.html` contains the homepage, CSS, and small vanilla JavaScript interactions.
- `publications.html` is a standalone responsive Publications & Media page with category filters and links to original third-party sources.
- `public/public/images/` contains the supplied portrait, speaking photo, and GHAA graphics.
- Vercel serves the repository root as a static site. No build step or framework is required.

## Decisions
- Keep changes dependency-free and scoped to the static HTML/CSS/JavaScript site; the dedicated `cyber-law.html` page is the explicit approved exception to the single-page homepage.
- On mobile, the full navigation is available through an accessible menu toggle, keeping Home, About, Practice Areas, Leadership, Publications, and Contact available without squeezing them into the header.
- External profile and contact links use clean text labels without decorative arrow glyphs.
- The homepage navigation links to `publications.html`; the publications page links back to homepage sections and labels its content as a selected reference list, not an exhaustive catalogue.
- The homepage hero uses the new professional barrister portrait from `public/public/images/Professional Barrister Portrait in Law Office.png`, fitted with `object-fit: contain` so the photo itself is not cropped.
- Homepage hero uses three accessible rotating slides with 3-second intervals, manual controls, hover/focus pause, and reduced-motion support.
- The five remaining gallery images display in a responsive mosaic without cropping source images. On small phones the gallery becomes a single-column list, with keyboard-accessible modal lightbox, caption, previous/next controls, Escape close, and focus return. The GHAA election campaign poster and low-quality `dev-kella-speaking.jpg` photo were removed from the gallery at the user's request; the replacement `Formal Namaste at a Conference.png` was reviewed and then removed at the user's request to keep the gallery to five images.
- Practice areas use icon-led cards with details that expand on hover/focus on desktop and remain visible on touch layouts. Desktop uses a 2×2 grid, tablets use two columns, and small phones use a single-column card layout. The footer uses two columns on tablets/desktop and stacks on phones, with a separate disclaimer panel.
- New gallery images use lazy loading and async decoding; the hero image is prioritized for loading.
- Respect `prefers-reduced-motion` by disabling autoplay/animation where possible; pause autoplay while the gallery is hovered or focused.
- WhatsApp remains a click-to-open link with a prefilled message. The visitor must send the message themselves.

## Fragile areas / checks
- All CSS and JavaScript are embedded in `index.html`; inspect script syntax and mobile media queries after edits.
- Verify the WhatsApp URL and social/profile destinations remain intact.
- Publication cards are fully clickable and keyboard accessible; clicks on existing source links retain their direct link behavior. Filter buttons must remain functional.
- Publications page: check external source URLs, filter categories, mobile card layout, navigation links, and third-party/legal-record disclaimer.
- Check hero portrait fit, all three hero slides, manual controls, 3-second autoplay, hover/focus pause, and reduced-motion behaviour.
- The photo gallery is positioned immediately after Practice Areas and before Leadership so visitors encounter the photos earlier in the homepage flow.
- Check photo grid responsiveness, lightbox image/caption, previous/next, Escape close, keyboard opening, and focus return.
- Review legal profile text and Bar Council of India compliance separately before public promotion.


## Mobile overflow and media notes
- Added horizontal overflow safeguards and responsive heading sizes to both the homepage and Publications page.
- Practice areas collapse to one column below 768px. Publications cards also collapse to one column on smaller screens.
- Inspected homepage for Spotify embeds: none are present, so no Spotify iframe or lazy-loading attributes were added; do not add one without a specific user-provided media link.
- The source image directory includes several PNG photos around 1.6–2.0 MB. Converting these to WebP/AVIF should be handled as a separate binary-asset optimization step; current text-file editing workflow does not safely replace those binary files in-place.


## Image and contact form fixes
- Vercel serves files in the repository's `public/` directory from the URL root. All homepage image URLs now use `/public/images/...` instead of `/public/public/images/...`; spaces are percent-encoded in the image URLs.
- Added graceful fallbacks for failed gallery and hero images, including a DK monogram placeholder.
- Added intrinsic responsive sizing rules for images and loading/error handling. Existing hero image remains high-priority; gallery images remain lazy-loaded.
- Removed the contact enquiry form as requested. Keep it removed. The contact section uses a styled WhatsApp contact card with icon, supporting text, and a direct link to the existing contact number.
- Added smooth active-section navigation highlighting using IntersectionObserver.


## Office map and social profile presentation
- The contact map and its explicit Open address in Google Maps link both use the full office address string shown on the page. The address is still only as precise as the supplied address text; if the building pin is wrong, request a verified Google Maps place URL or pin before claiming exact rooftop accuracy.
- Social profile links use inline SVG icons with subtle border/background treatment in the contact area and footer. No icon-font or third-party dependency is added.
- The contact enquiry form remains removed.
