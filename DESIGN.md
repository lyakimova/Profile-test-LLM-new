# Design System Specification: Editorial Organicism

## 1. Overview & Creative North Star: "The Botanical Atelier"
This design system rejects the clinical sterility of modern SaaS in favor of a "Botanical Atelier" aesthetic. Our Creative North Star is defined by the intersection of high-end editorial print and organic tranquility. We achieve a premium, custom feel by moving away from rigid, boxed-in grids and embracing **Intentional Asymmetry**.

Layouts should feel like a curated gallery—generous white space (using our `16` and `24` spacing tokens), overlapping elements that break the container, and a sophisticated tension between the authoritative, high-contrast serif of the display type and the grounded, deep forest greens of our palette. We are not building a dashboard; we are composing a digital experience that breathes.

---

## 2. Colors & Tonal Depth
Our palette is rooted in nature but executed with the precision of a luxury brand.

### The Palette
- **Primary (`#144227`) & Primary Container (`#2D5A3D`):** These are our "Forest" tones. Use them for high-impact moments and primary actions.
- **Surface & Background (`#FCF9F3`):** Never use pure white for large areas. This "Alabaster" base provides a warm, paper-like quality that reduces eye strain and feels more premium.
- **Secondary (`#436745`):** Used for supporting elements and botanical accents.

### The "No-Line" Rule
**Explicit Instruction:** Do not use 1px solid borders to define sections. Traditional dividers are strictly prohibited. Boundaries must be defined solely through:
1. **Background Color Shifts:** Use `surface-container-low` sections against the standard `surface` background.
2. **Generous Negative Space:** Use our `spacing-12` or `spacing-16` to denote a change in context.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers of fine paper. 
- **Base:** `surface` (#FCF9F3)
- **Secondary Level:** `surface-container-low` (#F6F3ED)
- **Raised Elements:** `surface-container-lowest` (#FFFFFF)
By nesting a `lowest` (pure white) card inside a `low` (off-white) section, you create a soft, natural lift that feels tactile rather than digital.

### Signature Textures (Glass & Gradient)
To provide "soul," use a subtle linear gradient on main CTAs: transitioning from `primary` (#144227) to `primary-container` (#2D5A3D) at a 135-degree angle. For floating navigation or overlays, apply **Glassmorphism**: use `surface` at 80% opacity with a `20px` backdrop-blur.

---

## 3. Typography: The Editorial Voice
We use a high-contrast typographic scale to establish authority and elegance.

- **Display & Headlines (Noto Serif / Playfair Influence):** 
  - `display-lg` (3.5rem) and `headline-lg` (2rem). 
  - These are our "Hero" fonts. Use them to command attention. They should often be set with slightly tighter letter-spacing (-0.02em) to mimic high-end magazine mastheads.
- **Titles & Body (Plus Jakarta Sans / Montserrat Influence):**
  - `body-lg` (1rem) and `title-md` (1.125rem).
  - This is our "Workhorse" type. It provides a clean, modern counterpoint to the serif headers. Ensure a line height of at least 1.6 for body text to maintain the "breathable" feel.
- **Labels:** 
  - `label-md` (0.75rem).
  - Use these for all-caps metadata or small captions, often with increased letter-spacing (+0.05em) for a sophisticated, architectural look.

---

## 4. Elevation & Depth: Atmospheric Layering
We do not use shadows to create "pop"; we use them to create "atmosphere."

- **The Layering Principle:** Use the Tonal Scale. A card should be `surface-container-lowest` sitting on a `surface-container` background. This is "Tonal Layering."
- **Ambient Shadows:** If an element must float (e.g., a Modal), use a shadow that mimics natural light: `box-shadow: 0 20px 40px rgba(28, 28, 24, 0.06);`. The shadow color must be a tinted version of `on-surface`, never pure black.
- **The "Ghost Border" Fallback:** If a border is required for accessibility, use the `outline-variant` token at **15% opacity**. A 100% opaque border is a failure of the design system's philosophy.

---

## 5. Components

### Buttons
- **Primary:** Gradient fill (`primary` to `primary-container`), white text, `rounded-md` (0.375rem). Use `spacing-5` for horizontal padding.
- **Secondary:** `surface-container-highest` background with `on-surface` text. No border.
- **Tertiary:** Text-only in `primary` color with a `label-md` weight.

### Cards
- **Construction:** No borders. No heavy shadows. 
- **Style:** Use `surface-container-lowest` background. Use `spacing-8` for internal padding. If the card contains an image, the image should have a slightly different corner radius (`rounded-sm`) than the card itself (`rounded-lg`) to create a custom, nested look.

### Input Fields
- **Background:** `surface-container-high`.
- **Border:** Use the "Ghost Border" (15% opacity `outline-variant`) only on the bottom edge to mimic a premium stationery feel.
- **Focus State:** Transition the bottom border to `primary` (2px) and subtly shift the background to `surface-container-highest`.

### Selection (Chips & Radio)
- **Chips:** Use `rounded-full`. Unselected: `surface-container-high`. Selected: `primary` with `on-primary` text.
- **Dividers:** Forbid the use of horizontal lines. Use a `spacing-10` vertical gap instead.

---

## 6. Do's and Don'ts

### Do:
- **Asymmetry:** Let images bleed off the edge of the grid or overlap with text blocks.
- **White Space:** Use more than you think you need. If a section feels crowded, double the spacing token (e.g., move from `8` to `16`).
- **Tonal Contrast:** Rely on the difference between `#FCF9F3` (Surface) and `#F0EEE8` (Container) to define areas.

### Don't:
- **Don't use 1px Borders:** This is the quickest way to make the design feel "templated."
- **Don't use Pure Black:** Use `on-surface` (#1C1C18) for text; it preserves the organic warmth of the Alabaster background.
- **Don't Center Everything:** Editorial design thrives on "The Rule of Thirds." Align headlines to the left and allow body text to occupy specific columns for a more dynamic flow.