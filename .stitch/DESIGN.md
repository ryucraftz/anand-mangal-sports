# Design System Document: Kinetic Precision

## 1. Overview & Creative North Star
**Creative North Star: "The High-Performance Lens"**

This design system is engineered to feel like elite sports equipment: technical, high-tension, and unapologetically premium. We move beyond the "template" look by treating the interface as a high-contrast tactical HUD. Instead of rigid grids and boxes, we utilize **intentional asymmetry**, **glassmorphism**, and **tonal depth** to create a sense of forward motion. 

The aesthetic is "Editorial Tech"—combining the bold, aggressive typography of a sports magazine with the sophisticated layering of modern aerospace interfaces. We don't just show data; we frame it as a performance metric.

---

## 2. Colors: Depth & Energy
The palette is built on a "Deep Sea" foundation with "Ignition" accents.

### The Foundation (Neutrals)
*   **Surface / Background (`#060e20`):** The absolute base. Use this for the primary canvas to ensure maximum contrast for neon-adjacent accents.
*   **Surface Containers:** Use `surface_container_low` (`#091328`) for large section blocks and `surface_container_highest` (`#192540`) for interactive elements like cards.

### The Ignition (Accents)
*   **Primary (`#ff9153`):** Reserved for high-priority actions and "Pulse" states.
*   **Secondary (`#f8a010`):** Used for highlighting technical specs or achievement tiers.

### The "No-Line" Rule
**Prohibit 1px solid borders for sectioning.** Boundaries must be defined solely through background color shifts. For example, a `surface_container_low` section sitting on a `surface` background creates a natural, sophisticated break. If a boundary feels "lost," increase the tonal step rather than adding a stroke.

### The "Glass & Gradient" Rule
To achieve a "Liquid Performance" feel, use Glassmorphism for floating overlays (Navbars, Modals).
*   **Glass Recipe:** `surface_variant` at 40% opacity + `backdrop-filter: blur(24px)`.
*   **Signature Textures:** Apply a linear gradient from `primary` to `primary_container` on hero buttons to provide a "forged" metallic look.

---

## 3. Typography: Tactical Impact
We use two distinct typefaces to balance aggressive energy with technical readability.

*   **Display & Headlines (Space Grotesk):** This is our "Engine." It is wide, mechanical, and high-impact. Use `display-lg` (3.5rem) for hero statements with tight letter-spacing (-0.04em) to mimic the speed of a sprinter.
*   **Body & Labels (Plus Jakarta Sans):** Our "Navigation." It provides a clean, breathable contrast to the heavy headlines. 

**Hierarchy Strategy:**
*   **Hero:** `display-lg` / `primary` color / All Caps for maximum "Sports Editorial" impact.
*   **Stats:** `headline-lg` / `secondary` color to pull the eye toward performance data.
*   **Meta-data:** `label-md` / `on_surface_variant` for a technical, "blueprint" feel.

---

## 4. Elevation & Depth
In this system, depth is a functional tool, not a decoration.

*   **The Layering Principle:** Stack tiers to create a "Nested Engine" look. Place a `surface_container_highest` card inside a `surface_container_low` section. This creates a soft, structural lift.
*   **Ambient Shadows:** For floating elements, use a "Deep Void" shadow: `box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4)`. The shadow should feel like a natural occlusion of the navy background, not a grey smudge.
*   **The "Ghost Border" Fallback:** If accessibility requires a stroke, use `outline_variant` at **15% opacity**. This creates a "hairline" shimmer that suggests a glass edge rather than a plastic box.
*   **Glassmorphism:** Use `surface_tint` at low opacities (5%) on top of glass layers to give them a subtle "anodized" color cast.

---

## 5. Components: Precision Engineered

### Buttons
*   **Primary:** `primary` background with `on_primary` text. Use `xl` roundedness (3rem) for a pill shape that feels aerodynamic.
*   **Glass Action:** Transparent background, `backdrop-blur(12px)`, and a "Ghost Border" of `outline_variant`.

### Cards & Lists
*   **The Divider Prohibition:** Forbid the use of divider lines. Separate list items using `spacing-4` (1.4rem) and subtle background shifts (e.g., alternating between `surface_container_low` and `surface_container`).
*   **Product Cards:** Use `lg` roundedness (2rem). Images should "bleed" to the edges, with text overlays using the Glassmorphism recipe at the bottom.

### Inputs & Fields
*   **Default State:** `surface_container_high` with a `none` border.
*   **Focus State:** A 2px glow using `secondary` but only on the bottom edge—mimicking a high-tech measurement scale.

### Performance Chips
*   Used for equipment categories (e.g., "Pro-Grade," "Carbon Fiber"). Use `secondary_container` with `on_secondary` text. Apply `full` roundedness.

---

## 6. Do’s and Don’ts

### Do:
*   **Use Intentional Asymmetry:** Align text to the left but allow high-action imagery to break the grid or overlap container edges.
*   **Embrace Negative Space:** Use `spacing-16` (5.5rem) between major sections to let the high-contrast elements "breathe."
*   **Color as Feedback:** Use `tertiary` (#47c4ff) only for data-driven "Success" states or technical specifications to keep the focus on the Orange/Amber brand energy.

### Don't:
*   **Don't use 100% white (#FFFFFF):** It is too jarring against the Navy base. Always use `on_surface` (#dee5ff) or `on_background` for a premium, slightly tinted "cool white" look.
*   **Don't use small corners:** Any radius below `sm` (0.5rem) breaks the "Modern/Glass" aesthetic. Stick to `DEFAULT` (1rem) and above.
*   **Don't use flat drop shadows:** If it doesn't have a blur radius of at least 20px, it doesn't belong in this system.

---

## 7. Spacing Scale: The Rhythm of Speed
All spacing must follow the geometric progression defined in the scale.
*   **Micro-spacing (1.5 / 0.5rem):** For internal component padding (e.g., inside a Chip).
*   **Macro-spacing (12 / 4rem):** For vertical rhythm between content blocks.
*   **Gutter (6 / 2rem):** Standard horizontal padding for mobile and desktop containers.
