# Media Production Website - Capstone Project

## 1. Overview
This website serves as a professional portfolio and contact portal for a media production company. It highlights services like Video Production, Audio Recording, and Photography, designed to attract new clients and visually present past work.

## 2. Issues Found
A thorough analysis of the starter code revealed approximately 58 missing or poorly implemented features. Some of the major issues included a lack of HTML5 document structure metadata (`<meta viewport>`, charset), use of generic `<div>` elements instead of semantic tags like `<header>`, `<main>`, `<section>`, and `<footer>`, and images using basic `<img>` tags without `<figure>`/`<figcaption>`. There were incomplete media elements (videos missing fallback and controls), missing forms, missing validation, and a complete lack of CSS Flexbox and Grid. The original issues are extensively documented in `design/issues-identified.txt`.

## 3. Fixes and Implementations
To bring the site to Level 3 requirements, I replaced generic wrappers with proper semantic tags and fixed metadata validation errors. I completed the media elements by adding `controls` to videos, creating a second video element, embedding audio, and creating a map `iframe`. I also heavily upgraded the functional contact form to feature 8 different input types fully labeled and validated.

## 4. CSS Flexbox Layouts
Flexbox was heavily used to implement adaptive, responsive flows. It was utilized in the `.top` header using `justify-content: space-between` to split the logo and navigation. It was also used in `.services-grid` and `.contact-area` allowing content to gracefully wrap around using `flex-wrap: wrap`.

## 5. CSS Grid Layout
A CSS Grid layout was implemented in the "Featured Media" section (`.media-boxes`). Using `grid-template-columns: repeat(auto-fit, minmax(150px, 1fr))` alongside `grid-template-rows: auto` and `grid-gap: 15px`, the media item blocks fluidly resize and wrap independently without media queries while maintaining structural rigidity.

## 6. Selectors and Pseudo-classes
I heavily expanded CSS selectors in the codebase. Types used include Universal `*`, Element `body`, Class `.nav`, Descendant `.nav a`, and Child combinators `.services-grid > .service-card`. Furthermore, multiple pseudo-classes were implemented for interactivity and targeting, including `:hover`, `:focus`, `:first-child`, `:last-child`, `:nth-child(even)`, and `:not()`.

## 7. Animations, Effects, Transforms, and Transitions
I applied visual flair without Javascript:
- **Text Effect:** Applied `text-shadow` to the hero header to improve legibility.
- **Transforms & Transitions:** Utilized smooth `transform: translateY()`, `scale()`, and `rotate()` combined with `transition` to give a tactile feel to buttons, service cards, and grid items when hovered.
- **Keyframe Animation:** A custom `@keyframes fadeInSlide` animation smoothly reveals the hero title upon loading.

## 8. Accessibility Improvements
To ensure Web Content Accessibility Guidelines (WCAG) compliance, I corrected several critical failures:
1. Associated logical `<label for="id">` attributes to every single input, and added semantic fieldsets.
2. Verified all `<img>` elements received descriptive `alt` tags.
3. Provided `<iframe>`, `<audio>`, and `<video>` with fallback texts and accessible controls.

## 9. Cross-Browser Compatibility
The site was tested in modern Google Chrome, Mozilla Firefox, and Microsoft Edge. Due to the reliance on standards-compliant CSS features (Flexbox / Grid) instead of experimental hacks, rendering was mostly identical across browsers. I added browser-specific CSS logic (`-webkit-animation` and `-webkit-transform`) to guarantee that the hero banner 2D animation renders smoothly on Apple Safari and older WebKit engine versions. Standard CSS resets (`box-sizing: border-box`, zero margins) successfully neutralized other browser-specific user-agent styling quirks.

## 10. How to View Locally
1. Download or clone this repository.
2. Navigate to the top-level directory (`media-production-website`).
3. Open `index.html` directly into any modern web browser (Edge, Chrome, Safari, Firefox).
4. No build step or local server (like Node/NPM) is required, but an extension like VSCode Live Server is recommended.

## 11. Known Issues or Limitations
Images provided are primarily placeholders mapped to `images/hero-image.jpg` or similar missing files, restricting the visual layout. The embedded map `iframe` currently points to a basic OpenStreetMap coordinate bounding box instead of a branded API map like Google Maps, though it is fully functional.
