# Design System Strategy: The Luminous Obsidian

## 1. Overview & Creative North Star
**Creative North Star: The Digital Alchemist**
This design system rejects the "flatness" of standard SaaS interfaces in favor of a deep, atmospheric environment where light and shadow feel tactile. By combining the infinite depth of `#010101` with hyper-vibrant, neon-infused gradients, we create a "Luminous Obsidian" aesthetic. The goal is to make the user feel as though they are interacting with a high-end physical interface made of polished volcanic glass and projected light.

We break the "template" look by utilizing **intentional asymmetry** and **high-contrast typography scales**. Large, airy headers in *Manrope* contrast against tight, technical labels in *Space Grotesk*, creating an editorial feel that prioritizes focus and premium "breathing room."

---

### 2. Colors & Surface Philosophy

Our color palette is built on the contrast between absolute void and ethereal energy.

*   **Background (`#0e0e0e` / `#000000`):** The foundation is a "super-black." It is the stage upon which light performs.
*   **The Primary Gradient:** Our signature. A three-point transition from `primary` (#FA93FA) via `secondary` (#C967E8) to a deep violet (#983AD6). Use this sparingly for high-impact CTAs, progress indicators, or "glow" backdrops behind glass cards.

#### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid, high-contrast borders for sectioning. Boundaries must be defined solely through background color shifts. To separate a main feed from a sidebar, use `surface-container-low` sitting against a `surface` background. If the eye cannot see the transition, increase the tonal shift, do not add a line.

#### Surface Hierarchy & Nesting
Treat the UI as a series of nested, frosted glass panes.
*   **Level 0:** `surface_dim` (#0e0e0e) - The base canvas.
*   **Level 1:** `surface_container` (#1a1919) - Main content blocks.
*   **Level 2:** `surface_container_high` (#201f1f) - Active states or elevated cards.
*   **The Glass Effect:** For floating elements (modals, dropdowns, navigation bars), use a custom utility: `bg-white/10` with a `backdrop-blur-xl`. This creates a "frosted" look that allows background gradients to bleed through softly.

---

### 3. Typography: The Editorial Scale

We use a tripartite font strategy to balance modern tech with high-end luxury.

*   **Display & Headlines (Manrope):** These are your "vibe" setters. Use `display-lg` (3.5rem) with tight letter-spacing (-0.02em) for hero sections to create an authoritative, architectural presence.
*   **Body & Titles (Inter):** The workhorse. *Inter* provides maximum legibility at `body-md` (0.875rem) for complex data. Ensure line-heights are generous (1.5x - 1.6x) to maintain the premium feel.
*   **Technical Labels (Space Grotesk):** Used for `label-md` and `label-sm`. The geometric quirks of *Space Grotesk* signal "Tech-Focused" and "Future-Proof." Use this for metadata, tags, and micro-copy.

---

### 4. Elevation & Depth: Tonal Layering

Shadows and borders are secondary to light.

*   **The Layering Principle:** Depth is achieved by stacking `surface-container` tiers. A `surface_container_highest` card should naturally sit atop a `surface_container_low` background.
*   **Ambient Shadows:** For floating glass panels, use "The Void Shadow": A 32px to 64px blur, 6% opacity, using the `on_surface` color (White). This mimics the way light diffracts around a physical object.
*   **The "Ghost Border" Fallback:** When separation is vital for accessibility, use a "Ghost Border": `outline_variant` at 15% opacity. It should be felt, not seen.
*   **Glow States:** Instead of standard shadows for active buttons, use a blurred "drop-glow" using a 20% opacity version of the `primary` token.

---

### 5. Components

#### Buttons
*   **Primary:** A hard-edge (rounded-md: 0.75rem) container using the `Primary Gradient`. Text is `on_primary` (Bold). On hover, increase the gradient saturation.
*   **Secondary/Glass:** A `bg-white/5` fill with a `backdrop-blur-md` and a 10% `outline`. This is the signature "Glassmorphism" button.
*   **Tertiary:** Pure text using `primary` color, no container, `label-md` styling.

#### Cards
*   **The Obsidian Card:** No borders. Background: `surface_container`. Padding: `spacing-6` (2rem). 
*   **The Glass Overlay:** For featured content, use `bg-white/5` + `backdrop-blur`. Ensure a subtle "inner-glow" by adding a top-edge stroke of `white/15` only.

#### Input Fields
*   **State:** Default state is `surface_container_highest` with no border. On focus, the bottom edge gains a 2px `primary` gradient "underline" while the background subtly brightens.

#### Lists & Navigation
*   **Divider Forfeiture:** Absolute prohibition of horizontal dividers. Separate list items using `spacing-3` (1rem) gaps and subtle `surface` color shifts on hover.

---

### 6. Do’s and Don'ts

**Do:**
*   **Embrace the Void:** Leave large areas of `#010101` empty. White space in dark mode is "Luxury Space."
*   **Layer with Intent:** Ensure that when glass elements overlap, the `backdrop-blur` is strong enough to maintain text contrast.
*   **Use Asymmetry:** Place your `display-lg` typography off-center to break the "Bootstrap" feel.

**Don't:**
*   **Don't use Grey:** Avoid standard mid-greys. If you need a softer tone, use `surface_variant` or `outline` which are tuned to our dark-mode palette.
*   **Don't use 100% Opacity Borders:** They shatter the illusion of glass and light.
*   **Don't Over-Gradients:** If everything is a gradient, nothing is a gradient. Save the `Primary-to-Tertiary` transition for the "Hero" actions only.

**Accessibility Note:**
While we use glass effects, ensure all text on `white/10` backgrounds meets a minimum 4.5:1 contrast ratio by using `on_surface` (White) or `primary_fixed` for high-importance text.