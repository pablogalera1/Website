# Design System Strategy: The Velveteen Editorial

## 1. Overview & Creative North Star: "The Sensual Enigma"
This design system moves away from the transactional, cluttered nature of standard social platforms toward a high-end, editorial experience. The Creative North Star is **"The Sensual Enigma"**—a philosophy where luxury is defined by what is hinted at rather than what is shown. 

We achieve this through **Intentional Asymmetry** and **Tonal Depth**. Instead of a rigid, centered grid, we use expansive white space (using the `20` and `24` spacing tokens) to let imagery breathe. Elements should overlap—a text block (`notoSerif`) partially masking a soft-focus silhouette—to create a sense of physical layering and mystery. We are not building a webpage; we are composing a digital boutique.

## 2. Colors & Surface Philosophy
The palette is a sophisticated blend of deep embers (`#161213`) and luminous accents (`#ffb2bf`, `#ffd799`).

*   **The "No-Line" Rule:** Explicitly prohibit 1px solid borders for sectioning. Structural boundaries must be defined solely through background shifts. For instance, a CTA section using `surface_container_low` should sit directly against the `surface` background. The transition is felt, not seen.
*   **Surface Hierarchy & Nesting:** Treat the UI as stacked sheets of fine silk.
    *   **Base:** `surface` (#161213)
    *   **In-Page Sections:** `surface_container_low` (#1f1a1b)
    *   **Floating Cards/Modals:** `surface_container_high` (#2d292a)
*   **The Glass & Gradient Rule:** To evoke "soft lights," use linear gradients for primary actions, transitioning from `primary` (#ffb2bf) to `primary_container` (#9d0041) at a 135-degree angle. Floating navigation bars must utilize `backdrop-blur` (20px+) with a 60% opacity `surface_container` fill.
*   **Signature Textures:** Apply a subtle grain texture or a radial gradient overlay (from `secondary_container` at 5% opacity to transparent) over large background areas to simulate the warmth of film photography.

## 3. Typography: The Editorial Voice
We pair the authoritative elegance of **Noto Serif** with the modern, clean functionality of **Manrope**.

*   **Display (Noto Serif):** Use `display-lg` and `display-md` for hero statements. These should be set with tight letter-spacing (-0.02em) to feel like a fashion magazine masthead.
*   **Headlines (Noto Serif):** `headline-lg` should be reserved for section titles, often placed asymmetrically (e.g., flush left while content is staggered right).
*   **The Body (Manrope):** `body-lg` is your workhorse. It provides a technical, modern contrast to the romantic serif headers.
*   **Labels (Manrope):** `label-md` must be used in all-caps with increased letter-spacing (0.1em) for a "luxury brand" feel on small metadata or category tags.

## 4. Elevation & Depth: Tonal Layering
Traditional shadows are too "software-like." We use light and tone to imply height.

*   **The Layering Principle:** To lift a "Member Preview" card, do not add a border. Place the card (`surface_container_highest`) onto a `surface_container_low` background. The delta in luminance creates the lift.
*   **Ambient Shadows:** When a floating element (like a subscription modal) requires a shadow, use a spread of `32px` with an opacity of 8%, using the color `on_primary_fixed_variant` (#90003b). This creates a warm, colored glow rather than a dirty grey shadow.
*   **The "Ghost Border" Fallback:** If a button requires definition against a busy background, use a 1px stroke of `outline_variant` at **15% opacity**. It should be a whisper, not a statement.
*   **Glassmorphism:** Navigation and "Locked Content" overlays must use `surface_container` at 40% opacity with a heavy blur. This suggests "steamy glass," aligning with the sensual aesthetic.

## 5. Components

### Buttons (The "Jewel" Elements)
*   **Primary:** Gradient fill (`primary` to `primary_container`). `xl` roundedness (1.5rem). No border. Typography: `label-md` bold, all-caps.
*   **Secondary:** Ghost style. `outline` token at 20% opacity. On hover, transition to 100% opacity `surface_bright`.
*   **Tertiary:** Text only using `secondary` color (#ffd799). Underline on hover with a 2px offset.

### Cards & Content Teasers
*   **Rules:** Absolutely no dividers. Separate content using the `spacing-8` (2.75rem) or `spacing-10` (3.5rem) tokens.
*   **Image Treatments:** Apply a `sm` (0.25rem) or `none` roundedness to images to maintain a sharp, editorial look. Soften the images themselves with a subtle internal vignette rather than rounding the corners of the container.

### Input Fields
*   **Style:** Minimalist underline style. Use `surface_container_highest` as a subtle background block with a bottom-only border of `outline` at 30% opacity. 
*   **States:** On focus, the bottom border transforms to `secondary` (#ffd799).

### Signature Component: The "Veil" Overlay
*   **Context:** Used for locked/premium content previews.
*   **Design:** A high-blur backdrop filter applied to the container, with a `display-sm` Noto Serif "Unlock" prompt centered. Use `secondary_fixed_dim` for the icon/text color to create a golden, high-value glow.

## 6. Do’s and Don’ts

### Do:
*   **Do** use asymmetrical margins. If the left margin is `spacing-12`, try a right margin of `spacing-24` for a boutique feel.
*   **Do** use `secondary` (gold) sparingly for high-conversion elements or "VIP" indicators.
*   **Do** prioritize "Breathing Room." If a layout feels crowded, double the spacing token value.

### Don't:
*   **Don't** use 100% black (#000000). Always use `surface` (#161213) to keep the shadows warm and "filmic."
*   **Don't** use standard icon sets (like heavy Material icons). Use ultra-thin line icons (0.5px to 1px weight) to match the `outline` token.
*   **Don't** use center-alignment for everything. Modern luxury is often found in the unexpected balance of off-center elements.