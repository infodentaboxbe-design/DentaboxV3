# Design System Strategy: The Curated Atelier

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Clinical Sanctuary."** 

This is not a typical medical or e-commerce interface; it is the *Haute Horlogerie* of oral hygiene. We are moving away from the "template" look by embracing the **Bento Grid**—a layout philosophy that treats information as a curated collection of high-end artifacts. 

To achieve a premium, custom feel, we break rigid symmetry through intentional whitespace, overlapping lifestyle imagery, and a typography scale that feels like a high-fashion editorial. The goal is a digital experience that feels as intentional and calibrated as a precision-engineered timepiece, balancing the sterility of science with the warmth of natural luxury.

---

## 2. Colors: Tonal Depth & The "No-Line" Rule
Our palette is rooted in nature and clinical precision. We avoid harsh blacks and stark whites in favor of a sophisticated, organic spectrum.

### The "No-Line" Rule
**Explicit Instruction:** Do not use 1px solid borders to section content. Structural boundaries must be defined solely through background color shifts or tonal transitions.
- Use `surface-container-low` (#f4f4f2) sections sitting on a `background` (#f9f9f7) to denote change in context.
- Use whitespace as a functional divider.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. Hierarchy is achieved by "stacking" tones:
- **Level 0 (Base):** `surface` (#f9f9f7) for the main canvas.
- **Level 1 (Sections):** `surface-container-low` (#f4f4f2) for large content blocks.
- **Level 2 (Cards):** `surface-container-lowest` (#ffffff) for elevated Bento items to create a soft "pop."

### Signature Textures & Glass
- **The Metallic Finish:** Main CTAs should not be flat. Apply a subtle linear gradient (from `primary` #154212 to `primary-container` #2D5A27) at a 45-degree angle to mimic the sheen of brushed forest-green metal.
- **Glassmorphism:** For floating navigation or over-image labels, use `surface` at 70% opacity with a `24px` backdrop-blur.

---

## 3. Typography: Editorial Authority
We utilize **Inter** not as a standard sans-serif, but as a tool for architectural layout.

| Level | Token | Role | Styling Notes |
| :--- | :--- | :--- | :--- |
| **Display** | `display-lg` | Hero Headlines | Tight leading (0.9), slight tracking (-2%). Bold and authoritative. |
| **Headline** | `headline-md` | Section Titles | Generous letter spacing (+5%) to evoke "Haute" luxury brands. |
| **Title** | `title-md` | Bento Labels | All-caps for a "Label" aesthetic when used in smaller sizes. |
| **Body** | `body-lg` | Product Copy | High line-height (1.6) for maximum breathability. |
| **Label** | `label-md` | Captions | Use `secondary` (#526351) to keep metadata subtle. |

**The Brand Voice:** Headlines should use a mix of `on-surface` and `primary` (Sage Green) to draw the eye to key emotional benefits (e.g., "A *Smarter* Smile").

---

## 4. Elevation & Depth: Tonal Layering
Traditional shadows are a last resort. Depth is a product of light and material layering.

- **The Layering Principle:** To lift a card, place a `#ffffff` card on a `#f4f4f2` background. This creates a natural, soft contrast that feels high-end.
- **Ambient Shadows:** If a floating element (like a modal or 'Buy' button) requires a shadow, use: `box-shadow: 0 20px 40px rgba(21, 66, 18, 0.06)`. Note the use of a tinted shadow (using the `primary` hue) rather than grey.
- **The "Ghost Border" Fallback:** For accessibility in form fields, use `outline-variant` (#c2c9bb) at **15% opacity**. It should be felt, not seen.

---

## 5. Components: The Bento Collection

### Buttons: High-Quality Finish
- **Primary:** Forest Green (`primary`) with a subtle top-to-bottom metallic gradient. Roundedness: `full`.
- **Secondary:** `surface-container-highest` background with `on-surface` text. No border.
- **Interaction:** On hover, the gradient should shift slightly, mimicking light reflecting off a satin-finish surface.

### Bento Cards
- **Corners:** Use `xl` (1.5rem) for main containers and `lg` (1rem) for nested items.
- **Content:** Every card must have a "Safe Zone" of at least `32px` padding. Content should never feel crowded.
- **Imagery:** Product images should use `soft-light` blending or be shot on marble/wood backgrounds that match the `surface` tokens.

### Input Fields & Controls
- **Text Inputs:** Use `surface-container-highest` backgrounds. No borders. Active state is indicated by a 1px `primary` underline only.
- **Checkboxes/Radios:** Use `primary` for selected states. Ensure the "unchecked" state is a subtle `outline-variant` circle to maintain the clinical aesthetic.

### Lists & Dividers
- **Strict Forbiddance:** No horizontal divider lines. 
- **The Alternative:** Use `24px` of vertical spacing or alternate the background color of list items between `surface` and `surface-container-low`.

---

## 6. Do's and Don'ts

### Do:
- **Do** use "Breathing Room." If you think a section has enough margin, add 16px more.
- **Do** overlap elements. Let a high-end product image break the bounds of its Bento container slightly to create 3D depth.
- **Do** use `primary` (#154212) for emphasis in typography within a sentence to guide the reader's eye.

### Don't:
- **Don't** use pure black (#000000). Use `on-surface` (#1a1c1b) for all "black" text.
- **Don't** use standard 4px or 8px corners. Only use the `lg` (16px) or `xl` (24px) tokens to maintain the "soft bento" feel.
- **Don't** use high-contrast shadows. If the shadow is clearly visible as a "dark smudge," it is too heavy.
- **Don't** use stock-looking icons. Use thin-stroke (1px or 1.5px) custom SVG icons that match the Inter typeface weight.