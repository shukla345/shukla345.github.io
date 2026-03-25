```markdown
# Design System Specification: Terminal Brutalism

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Sovereign Console."** 

This is not a nostalgic "retro" skin; it is a high-performance, professional environment designed for elite technical workflows. It rejects the "softness" of modern consumer web design—no rounded corners, no soft shadows, and no decorative imagery. Instead, it finds beauty in the mathematical precision of the monospaced grid and the raw authority of high-contrast data. 

To move beyond a "generic" CLI, we use **intentional asymmetry** and **ASCII-driven architecture**. Layouts should feel like a dense information manifest, utilizing extreme verticality and rhythmic spacing to guide the eye through complex datasets without the crutch of traditional UI components.

## 2. Colors & Surface Logic
The palette is binary and uncompromising. We utilize a "Dark Matter" foundation where depth is created not through light, but through the density of information and the strategic use of high-energy phosphor green.

### Surface Hierarchy
We strictly adhere to a **flat-plane architecture**. There are no shadows. Depth is defined by the shift from the void (`surface`) to the functional container.
- **Background (`#131313`)**: The absolute base. All data lives here.
- **Surface Container Lowest (`#0E0E0E`)**: Used for background "wells" or recessed code blocks.
- **Surface Container Highest (`#353534`)**: Used exclusively for active command lines or high-alert status bars.

### The "No-Line" Rule & ASCII Separation
Standard 1px solid borders are strictly prohibited unless they are constructed from ASCII characters. 
- **Structural Boundaries:** Use the `surface-container` tiers to create tonal "zones." 
- **Hard Dividers:** When a physical break is required, use a string of hyphens (`---`), equals signs (`===`), or dots (`...`) mapped to the `outline-variant` token. This reinforces the "machine-readable" aesthetic.

### Signature Accents
- **Primary (`#EAFFDE`)**: Reserved for high-priority readouts.
- **Primary Container (`#00FF00`)**: The "Action Phosphor." Use this for cursors, success states, and primary CTAs.
- **Error (`#FFB4AB`)**: Use sparingly for critical failures.

## 3. Typography: The Monospaced Hierarchy
Typography is the primary structural element. We use `Space Grotesk` for high-level "Display" headers to provide a hint of editorial polish, while `Inter` handles the body. However, all "functional" data must be set in a monospaced font (JetBrains Mono preferred).

- **Display LG (`3.5rem` / Space Grotesk)**: Used for version numbers or system status titles.
- **Headline SM (`1.5rem` / Space Grotesk)**: Used for section headers (e.g., `> SYSTEM_LOGS`).
- **Body MD (`0.875rem` / Inter)**: The workhorse for dense documentation.
- **Label SM (`0.6875rem` / Space Grotesk)**: Used for metadata and timestamps.

**Formatting Note:** All headers should be prefixed with a chevron `>` or a bracket `[` to maintain the command-line persona.

## 4. Elevation & Depth: Tonal Layering
In this system, "Elevation" is a misnomer. We do not elevate; we **segment**.

- **The Layering Principle:** To highlight a specific module, do not add a shadow. Instead, wrap the module in an ASCII box `+---+` and shift the background to `surface-container-low`.
- **The "Ghost Border" Fallback:** If a container requires a border for clarity in a dense list, use the `outline-variant` (`#3B4B35`) at 20% opacity. It should feel like a faint grid line on a blueprint, not a container wall.
- **No Transparency:** Every element is 100% opaque. This ensures maximum readability and reinforces the "raw data" feel.

## 5. Components

### Buttons (Command Triggers)
Buttons must look like selectable terminal strings.
- **Primary**: Background `#00FF00`, Text `#013A00`. No rounded corners (0px).
- **Secondary**: Ghost style. Border using `outline` token (`#84967C`) with text in `#FFFFFF`.
- **Interaction**: On hover, the button should invert colors or add a trailing underscore cursor `_`.

### Input Fields (Command Lines)
Inputs should not look like boxes.
- **Style**: A single bottom border or a prefix cursor `$` or `>`. 
- **Focus State**: The text cursor should blink (0.5s intervals) and the bottom border should shift to `primary-container`.

### Cards & Lists
- **The Divider Rule**: Forbid the use of standard horizontal rules. Separate list items using the Spacing Scale (specifically `spacing-4` or `spacing-6`).
- **Nesting**: Use the `surface-container` shifts to denote "nested" child data. A child list should sit on a slightly lighter or darker background than its parent.

### Chips (Tags)
- **Style**: Encased in square brackets. Example: `[STATUS: ACTIVE]`.
- **Colors**: Use `on-surface-variant` for inactive tags and `primary-container` for active ones.

## 6. Do's and Don'ts

### Do
- **Use White Space as a Tool:** Use the `24` (5.5rem) spacing token to separate major system blocks. 
- **Align to a Grid:** Every element must align to a strict vertical axis.
- **Embrace Upper Case:** Use `text-transform: uppercase` for labels and headers to enhance the "authoritative" tone.

### Don't
- **No Border Radius:** Never use a border-radius. Every corner must be a sharp 90-degree angle.
- **No Gradients:** Color must be flat. If you need to show progress, use a stepped ASCII bar: `[██████░░░░]`.
- **No Icons:** Avoid SVG icons. Use glyphs or ASCII symbols (e.g., `[!]` instead of a warning icon).
- **No Smooth Transitions:** Micro-interactions should be "snappy" (0ms to 100ms) to mimic the instant response of a local machine.```