# AERØ — Feel the Fizz

A single-page, scroll-driven 3D beverage website. Serve this folder over HTTP or HTTPS and open `index.html`.

**Sections:** hero, flavors, the story (can rises out of the water), collection, ingredients, *find-your-flavor quiz*, shop, *build-your-own 12-pack*, *FAQ*, footer with newsletter.

## What's in this folder
| File | Purpose |
|---|---|
| `index.html` | Site markup and references to its stylesheets and scripts |
| `css/style.css` | Site styles |
| `css/no-script.css` | Styles for the no-JavaScript fallback |
| `js/main.js` | Site interactions, 3D scene and can artwork |
| `vendor/` | three.js (r128) and GSAP + ScrollTrigger, so no outside servers are needed |
| `vendor/LICENSES.txt` | Licences for those libraries |
| `robots.txt` | Allows search engines to index the site |

## Motion
Loading screen with a filling wordmark, inertial smooth scrolling, a follower cursor, word-by-word heading reveals, a scroll-lit statement, a velocity-reactive marquee, a liquid colour wipe when you switch flavors, and a hero headline whose letter weight reacts to your pointer. Everything respects the "reduce motion" setting; touch devices keep native scrolling.

**Signature interactions:** the hero starts like a fogged cold glass that you wipe clear with the pointer (it slowly re-fogs, and clears itself if you don't touch it); the floating bubbles pop when touched; a pour gauge on the right edge fills with the flavor's liquid as you scroll. All are switched off for visitors who prefer reduced motion.

## Sound design
The "Sound" button (bottom of the screen) turns on procedural audio, generated live with the Web Audio API, so no audio files are needed. It is off by default and browsers require a click before any sound can play. Covered: hover ticks, button clicks, flavor bloops (pitch per flavor), add-to-cart chime, menu/cart/detail whooshes, quantity ticks, bubble pops, glass-wipe squeak, a soft fizz that rises as you scroll fast, and the story's water ambience, drop plop, can-launch splash and settle.

## Publish it (no build step)
The site is static. Upload the **contents of this folder** to any static host:
- **Netlify:** drag the folder onto app.netlify.com/drop
- **Cloudflare Pages / Vercel / GitHub Pages:** create a project and upload or push this folder as the site root
- **Any web host:** copy `index.html`, `robots.txt`, `css/`, `js/` and `vendor/` into the public folder

It must be served over `https://` or `http://`, not opened as a `file://` link on other people's computers.

## Before you go live
1. **Branding:** the cans' artwork says "ZYNK" (taken from your reference image) while the site says AERØ. Rename the label text in `function label` and the `F` array, or confirm you have the rights to the ZYNK mock-up.
2. **Shop:** the cart is a demo. Prices are sample values and no payment is processed. Connect a real checkout (Shopify, Stripe, etc.) before selling.
3. **Social links** in the footer are placeholders.
   **FAQ answers** (shipping, returns, contact) are sample text. Replace them with your real policies.
4. **Domain / sharing image:** add your URL and an `og:image` in the `<head>` for nicer link previews.

## Customising
- **Flavors** (names, colors, descriptions, ingredients): the `F` array near the top of `js/main.js`.
- **Prices and pack sizes:** the `Z` array right after it.
- **Colors:** the CSS variables at the top of `css/style.css`.
- **Scroll length:** `#journey{height:1200vh}` in `css/style.css`.

## Notes
- Needs a browser with WebGL (any current Chrome, Safari, Firefox, Edge). Without WebGL the text and shop still work, but the 3D scene is hidden.
- Respects the "reduce motion" setting. The sound button is off by default.
- The Google Font (Bricolage Grotesque) loads from Google; if it is blocked, a system font is used instead.
