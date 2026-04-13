# Design System Strategy: Precision Performance

This design system is engineered for a global IT services powerhouse. It moves beyond the utilitarian "table-and-form" nature of legacy HR software to create a high-end, editorial experience. We are building a platform that doesn't just track data—it narrates career growth.

---

## 1. Overview & Creative North Star: "Structural Transparency"

The Creative North Star for this system is **Structural Transparency**. In an enterprise appraisal context, "transparency" refers to the clarity of data, while "structural" refers to the reliability of the organization. 

We break the "template" look by utilizing **Intentional Asymmetry**. Rather than perfectly centered grids, we use weighted typography and offset containers to guide the eye toward key performance indicators (KPIs). The interface should feel like a premium business journal: authoritative, airy, and deeply sophisticated.

---

## 2. Colors & Surface Philosophy

We use a palette of deep corporate blues and sophisticated grays to establish trust, punctuated by high-chroma status colors for immediate feedback.

### The "No-Line" Rule
Standard enterprise UI relies on 1px borders to separate ideas. **We prohibit this.** Boundaries must be defined through background color shifts or tonal transitions.
- Use `surface_container_low` (#f1f4f6) for the main page body.
- Use `surface_container_lowest` (#ffffff) for primary content modules.
- The contrast between these two tokens creates a "borderless" edge that feels more modern and less cluttered.

### Surface Hierarchy & Nesting
Think of the UI as physical layers.
1.  **Base Layer:** `surface` (#f7fafc).
2.  **Section Layer:** `surface_container` (#ebeef0) to group related performance metrics.
3.  **Action Layer:** `surface_container_highest` (#e0e3e5) for interactive sidebar elements or drawers.

### The "Glass & Gradient" Rule
To elevate the "out-of-the-box" feel, primary actions and hero data points should utilize subtle gradients.
- **Primary CTAs:** A linear gradient from `primary` (#004384) to `primary_container` (#005aaf) adds a three-dimensional "soul" to the button.
- **Glassmorphism:** For floating modals or "Hover Quick-Views," use `surface_container_lowest` at 80% opacity with a `20px` backdrop-blur to maintain context of the underlying data.

---

## 3. Typography: The Editorial Voice

We pair **Manrope** (Display/Headlines) with **Inter** (Body/Labels) to create a high-contrast, professional hierarchy.

- **The Authority (Manrope):** Use `display-lg` and `headline-md` for performance scores and employee names. The geometric nature of Manrope feels modern and precise.
- **The Narrative (Inter):** Use `body-md` (#434654) for feedback comments. It is optimized for long-form reading and clarity.
- **The Data (Inter Bold):** All numerical data should use `label-md` or `title-sm` with increased letter spacing to ensure "scannability" during rapid reviews.

---

## 4. Elevation & Depth: Tonal Layering

Traditional drop shadows are often too "heavy" for enterprise tools. We achieve depth through light and tone.

- **The Layering Principle:** Place a `surface_container_lowest` card on a `surface_container_low` background. This creates a soft, natural lift without a single line of CSS shadow.
- **Ambient Shadows:** For "Active" states or floating cards, use a shadow with a 24px blur, 0px offset, and 6% opacity of `on_surface` (#181c1e). It should look like a soft glow, not a dark smudge.
- **The Ghost Border:** If a boundary is required for accessibility in data-heavy tables, use `outline_variant` (#c3c6d6) at **15% opacity**. This provides a "suggestion" of a line that disappears into the background, maintaining the "No-Line" aesthetic.

---

## 5. Components & Signature Patterns

### Buttons
- **Primary:** Gradient fill (`primary` to `primary_container`), `on_primary` text, and `lg` (0.5rem) roundedness.
- **Secondary:** `surface_container_high` fill with `primary` text. No border.
- **Tertiary:** Ghost style. `on_surface_variant` text that shifts to `primary` on hover.

### Precision Modules (Cards)
Forbid the use of divider lines within cards. Separate the "Header," "Body," and "Footer" of a performance card using:
- **Header:** `surface_container_low`
- **Body:** `surface_container_lowest`
- **Padding:** 24px (1.5rem) of vertical white space as a natural separator.

### Signature Data Landscapes
Instead of standard bar charts, use "Filled Area" charts with a gradient from `primary` (40% opacity) to transparent. Use `error` (#ba1a1a) and `tertiary_container` (#a33500) for "Low" and "Mid" performance markers, but always pair them with a text label for accessibility.

### Performance Chips
- **High (Green):** Use a custom success green (e.g., #2e7d32) at 10% opacity for the background, with the solid color for text.
- **Status Shapes:** Use `full` roundedness (9999px) for status indicators to contrast against the `lg` (0.5rem) roundedness of the main UI containers.

---

## 6. Do’s and Don’ts

### Do
- **Do** use `surface_bright` for page headers to create a sense of "Sky" and openness.
- **Do** use `inter` for all data-entry fields to ensure maximum legibility during input.
- **Do** use `display-sm` for large, heroic percentage numbers (e.g., "98% Goal Completion").

### Don’t
- **Don’t** use 100% black text. Always use `on_surface` (#181c1e) or `on_surface_variant` (#434654) to reduce eye strain.
- **Don’t** use the `DEFAULT` (0.25rem) roundedness for large containers; use `xl` (0.75rem) to make the enterprise tool feel approachable and "soft."
- **Don’t** use standard "Select" dropdowns. Use a custom `surface_container_lowest` menu with `MD` (0.375rem) roundedness and a soft ambient shadow.

---

## 7. Interaction Design
Every interaction should feel intentional. When a user hovers over a performance card, do not change the border; instead, transition the background color from `surface_container_lowest` to `surface_bright`. This subtle "light up" effect mimics the behavior of a physical lightbox, reinforcing the "Transparency" North Star.