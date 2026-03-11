# CapyBox (capy-box-3d) Project Memory

## File Structure
- Single file: `index.html` (~1250 lines total, ~2.2MB due to base64 images)
- CSS: lines ~10-869
- HTML: lines ~870-1055 (character card image lines 642-674 are 350K-430K chars each - base64 encoded)
- Scripts: particles (~1077), order handler (~1090), Three.js libs (~1150), Three.js app code (~1155), scroll observer (~1237)
- Wave SVG dividers added between all sections

## Known Quirks
- Character card images are inline base64 PNGs - lines are extremely long (350K-430K chars)
- Reading lines 611-690 range will fail with token limit due to base64 images
- Use `awk` with length truncation to read around those lines
- The file has external Three.js (r128) loaded via CDN, not inlined

## CSS Architecture (after 2026-03 redesign)
- Custom properties include color variants: --brown-light, --brown-dark, --cream-dark, --beige, --green-light
- Fluid typography using clamp() throughout
- Breakpoints: 1200px, 992px, 768px, 600px, 480px, 375px, 320px
- Character cards: 5-col grid on desktop, 3-col tablet, 2-col phone, 1-col tiny
- Cards have staggered entrance animation (cardStaggerIn) and 3D tilt hover
- Steps grid has connecting line via ::before pseudo-element
- CTA buttons have pulse animation and shimmer effect
- Modal uses glassmorphism (backdrop-filter blur + semi-transparent bg)
- Wave SVG dividers between all major sections
- Footer has radial gradient pattern overlay
