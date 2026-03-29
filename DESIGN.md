# Design System Specification: Editorial Gamification

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Prestigious Playground."** 

We are moving away from the "cheap" look of typical gamified apps. Instead, we are blending the high-end editorial feel of a premium financial magazine with the tactile, rewarding feedback of a modern RPG. The system breaks the "template" look through **intentional asymmetry**, where progress bars might overlap container edges, and **high-contrast typography scales** that treat data like a headline. We don't just show numbers; we celebrate financial milestones as heroic achievements.

---

## 2. Colors & Surface Philosophy
The palette balances the gravitas of "Midnight" with the kinetic energy of "Quest" and "Growth."

### Surface Hierarchy & Nesting
To achieve a premium feel, we strictly follow the **"No-Line" Rule**: 1px solid borders are prohibited for sectioning. Boundaries are defined solely through background shifts or tonal transitions.

*   **Layer 0 (The Void):** Use `surface` (#080e1d) for the primary app background.
*   **Layer 1 (The Stage):** Use `surface_container_low` (#0c1324) for large structural areas.
*   **Layer 2 (The Card):** Use `surface_container` (#12192b) or `surface_container_high` (#171f33) for interactive elements.
*   **The "Glass & Gradient" Rule:** Floating action elements or high-tier rewards must use `surface_variant` (#1d253b) at 60% opacity with a `20px` backdrop-blur. This "frosted glass" effect allows the vibrant `primary_dim` (#7e51ff) and `secondary` (#ffd709) accents to bleed through, creating a sense of depth and "soul."

### Signature Textures
Main CTAs and Hero sections should never be flat. Use a linear gradient:
*   **Primary Action:** `primary` (#b6a0ff) to `primary_dim` (#7e51ff) at a 135° angle.
*   **Success/Growth:** `tertiary` (#b5ffc2) to `tertiary_dim` (#24f07e) for "Level Up" moments.

---

## 3. Typography: The Editorial Voice
We use a high-contrast pairing to balance "Friendly" with "Financial Authority."

*   **Display & Headlines (Plus Jakarta Sans):** These are our "Hero" fonts. Use `display-lg` (3.5rem) for balance totals and `headline-md` (1.75rem) for quest titles. The rounded nature of Jakarta Sans provides the "friendly" accessibility requested, while its geometric precision maintains "trust."
*   **Body & Titles (Manrope):** Manrope is our workhorse. It is clean, modern, and highly legible at small scales. Use `body-md` (0.875rem) for all instructional text.
*   **The Power Scale:** Always pair a `headline-lg` with a `label-md` in `on_surface_variant` (#a5aabf). This contrast—big and bold vs. small and muted—is the hallmark of high-end editorial design.

---

## 4. Elevation & Depth
We eschew traditional "Material" shadows in favor of **Tonal Layering** and **Ambient Glows.**

*   **The Layering Principle:** Depth is achieved by "stacking." A `surface_container_highest` (#1d253b) card sitting on a `surface` background provides enough natural lift.
*   **Ambient Shadows:** For "floating" quest badges or modals, use a shadow with a `48px` blur and `6%` opacity. The shadow color should be `on_background` (#e0e5fb) to mimic soft, reflected light from the deep blue base.
*   **The Ghost Border Fallback:** If a container sits on a background of similar value, use a `1px` border using `outline_variant` (#424859) at **15% opacity**. It should be felt, not seen.

---

## 5. Components & Gamified Patterns

### Cards (The Quest Module)
*   **Design:** Large radius (`lg`: 2rem). No dividers.
*   **Spacing:** Use `spacing-6` (1.5rem) internal padding.
*   **Visual Logic:** Separate content types (e.g., Quest Description vs. Reward) using a background shift to `surface_bright` (#222c43) for the footer of the card rather than a line.

### Buttons (The Interaction Points)
*   **Primary:** Gradient of `primary` to `primary_dim`. Rounded `full` (9999px).
*   **Secondary/Quest:** Solid `secondary` (#ffd709) with `on_secondary` (#5b4b00) text. These are for high-priority gamified actions (e.g., "Claim Reward").
*   **State:** On press, reduce scale to `95%` to provide tactile, "springy" feedback.

### Progress Bars (Growth Tracking)
*   **Track:** `surface_variant` (#1d253b).
*   **Indicator:** `tertiary_fixed` (#3fff8b). 
*   **Style:** Height `12` (3rem) for major milestones, height `2` (0.5rem) for minor tasks. Always use `full` rounding.

### Inputs & Fields
*   **Surface:** Use `surface_container_lowest` (#000000) for the input well to create a "recessed" feel.
*   **Focus:** A subtle glow using `surface_tint` (#b6a0ff) at 20% opacity.

---

## 6. Do’s and Don’ts

### Do:
*   **Do** use `xl` (3rem) corner radius for hero cards to emphasize the "approachable" brand personality.
*   **Do** overlap elements. Let a badge (using `secondary`) sit 25% outside the bounds of its parent card to break the grid.
*   **Do** use `on_surface_variant` for secondary information to maintain a sophisticated hierarchy.

### Don't:
*   **Don't** use pure black (#000000) for text. Always use the `on_surface` (#e0e5fb) token to maintain the "midnight" depth.
*   **Don't** use 1px solid dividers. Use `spacing-8` (2rem) of vertical white space to separate thoughts.
*   **Don't** use standard "drop shadows." If it looks like a default plugin setting, it is wrong for this system. Stick to the Ambient Glow specification.