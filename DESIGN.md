# Design System Document: The Financial Luminary

## 1. Overview & Creative North Star

**Creative North Star: "The Illuminated Ledger"**
In a world of flat, sterile financial interfaces, this design system introduces a "High-End Editorial" experience. We are moving away from the "template" look of traditional banking apps toward a digital environment that feels like a premium concierge service. 

The core philosophy is **Illuminated Clarity**. We use deep, immersive navy tones to establish a foundation of unwavering trust, then pierce that depth with "glow" accents—soft gold and vibrant teal—to symbolize growth, insight, and financial awakening. The layout rejects rigid, boxed-in grids in favor of **Intentional Asymmetry** and **Layered Depth**, creating an interface that feels sophisticated, spacious, and empowered.

---

## 2. Colors & The "No-Line" Rule

Our palette is built on tonal depth rather than structural outlines.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to section content. Boundaries must be defined solely through background color shifts or subtle tonal transitions. For example, a `surface-container-low` section sitting on a `surface` background provides all the definition a user needs without the "visual noise" of a stroke.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers, like stacked sheets of frosted glass.
*   **Base Layer:** `surface` (#f8f9fa) or `primary` (#000c1e) for immersive sections.
*   **Layer 1 (The Bed):** `surface-container-low` (#f3f4f5) for large content areas.
*   **Layer 2 (The Focus):** `surface-container-highest` (#e1e3e4) for interactive elements or cards.
*   **The "Glass & Gradient" Rule:** Use Glassmorphism for floating elements. Combine `surface-container-lowest` (#ffffff) with a 60% opacity and a `backdrop-blur` of 20px. This allows the navy or teal accents to "bleed through" the container, softening the layout.

### Signature Textures
Main CTAs and Hero backgrounds should never be a flat hex code. Use a subtle linear gradient (135°):
*   **Primary Action:** `primary` (#000c1e) → `primary-container` (#002344)
*   **The "Glow" State:** `secondary` (#735c00) → `secondary-fixed-dim` (#e9c349)

---

## 3. Typography: The Authoritative Voice

We utilize two high-end sans-serifs to balance editorial authority with modern accessibility.

*   **Display & Headlines (Manrope):** Chosen for its geometric precision and modern "tech-premium" feel. Use `display-lg` (3.5rem) with tight letter-spacing (-0.02em) for hero moments to create a bold, editorial impact.
*   **Body & Titles (Work Sans):** Chosen for its exceptional readability at small scales. The slight quirks in Work Sans keep the brand feeling "accessible" and "human" despite the sophisticated color palette.
*   **Hierarchy Note:** Use `on-surface-variant` (#43474e) for body text to reduce eye strain, reserving `on-surface` (#191c1d) strictly for Headlines and Titles to ensure they "pop" as the primary points of authority.

---

## 4. Elevation & Depth: Tonal Layering

Traditional drop shadows are largely replaced by **Tonal Layering**.

*   **The Layering Principle:** To lift a card, do not add a shadow. Instead, place a `surface-container-lowest` card on a `surface-container-low` background. The subtle shift in hex value creates a "soft lift."
*   **Ambient Shadows:** If a floating element (like a Modal or FAB) requires a shadow, use a "Wide-Ambiance" approach: 
    *   `box-shadow: 0 20px 40px rgba(0, 12, 30, 0.06);` 
    *   The shadow color must be a tinted version of `primary`, never pure black or grey.
*   **The "Ghost Border" Fallback:** If accessibility requirements demand a border, use `outline-variant` (#c3c6cf) at **15% opacity**. It should be felt, not seen.

---

## 5. Components

### Buttons: The "Growth" Triggers
*   **Primary:** A gradient of `primary` to `primary-container`. `xl` roundedness (0.75rem). No border. Label in `on-primary` (#ffffff).
*   **The "Glow" Button:** Use `secondary-container` (#fed65b) for high-conversion moments. It should look like it’s emitting light against the navy background.
*   **Tertiary:** No background. Use `primary` text with a `secondary` 2px bottom-accent bar that appears only on hover.

### Cards & Lists
*   **The Rule:** Total prohibition of divider lines. 
*   **Implementation:** Separate list items using `spacing-3` (1rem) and alternating background tints or subtle `surface-container` shifts.
*   **Financial Cards:** Use `primary` backgrounds with a `tertiary-fixed` (#5af8fb) "glow" gradient in the top-right corner to indicate premium status.

### Inputs: The "Focus" State
*   **Style:** Minimalist. Background `surface-container-high` (#e7e8e9).
*   **Focus State:** Do not just change the border. Shift the background to `surface-container-lowest` (#ffffff) and add a 2px `secondary` (gold) accent on the left-hand side to symbolize "insight."

### Financial Progress Trackers (Unique Component)
*   **The "Glow-Up" Bar:** A progress bar using `primary-container` as the track and a vibrant gradient of `tertiary` (#000e0f) to `tertiary-fixed` (#5af8fb) as the fill. Add a soft outer glow to the fill head using the `tertiary-fixed` color.

---

## 6. Do's and Don'ts

### Do
*   **Do** use asymmetrical white space. Leave one side of a layout "heavier" to create an editorial, non-templated feel.
*   **Do** use `primary` (Deep Navy) for full-page backgrounds on "Success" or "High-Value" screens to create an immersive, premium feel.
*   **Do** rely on the Spacing Scale—specifically `spacing-8` (2.75rem) and `spacing-12` (4rem)—to give content room to breathe.

### Don't
*   **Don't** use 100% opaque borders. They clutter the UI and break the "Glow" metaphor.
*   **Don't** use standard "Success Green." Use our `tertiary` teal tokens to signal growth and positive movement.
*   **Don't** crowd the interface. If you think it needs a divider, it actually needs more white space.
*   **Don't** use sharp corners. Use the `xl` (0.75rem) or `lg` (0.5rem) roundedness tokens to maintain the "sophisticated yet accessible" personality.