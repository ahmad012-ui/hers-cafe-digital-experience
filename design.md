# Hers Cafe — Design System

This document translates the exported Google Stitch designs into implementation guidance for the Hers Cafe digital experience. The source-of-truth token file is `stitch_hers_cafe_digital_ecosystem/warm_artisanal_bistro/DESIGN.md`; consult it for the full palette and type scale. The exported `screen_*/code.html` and `screen_*/screen.png` files are the visual and markup references for each flow.

## Brand direction

**Warm Artisanal Bistro** combines editorial warmth with tactile modernism. The interface should feel like a boutique neighbourhood café: crafted, welcoming, contemporary, and food-focused.

- Use cream and porcelain surfaces with espresso-colored structure.
- Let food photography and whitespace carry the visual experience.
- Use editorial serif typography for storytelling and clear sans-serif typography for functional UI.
- Prefer soft, organic corners and warm ambient shadows over cold, high-contrast panels.
- Avoid generic delivery-app styling, neon colors, cluttered grids, and unrelated imagery.

## Core color tokens

Use these values consistently. The exported token file includes additional semantic variants.

| Role | Color | Use |
|---|---|---|
| Warm canvas | `#FCF9F4` | Main page/background surface |
| Porcelain | `#FFFFFF` | Cards, sheets, and elevated content |
| Deep espresso | `#250F05` | Primary brand token |
| Espresso container | `#3D2317` | Primary buttons and active states |
| Dark chocolate | `#1C1C19` | High-emphasis text |
| Warm mocha | `#504440` | Secondary text |
| Terracotta | `#97472E` | Warm accent and conversion highlights |
| Soft terracotta | `#FE997A` | Accent container/highlights |
| Fresh botanical | `#003117` | Tertiary dark green token |
| Sage highlight | `#699C77` | Positive/dietary accents where appropriate |
| Oat border | `#D4C3BD` | Subtle outlines and dividers |
| Error | `#BA1A1A` | Error states |

The exported design documentation also describes application-specific supporting tones such as vanilla cream `#FAF7F2`, terracotta glaze `#C86D51`, and sage `#4A7C59`. Where a screen already uses these values, preserve the existing screen styling rather than introducing a conflicting palette. For new shared components, prefer the canonical token values above and consolidate duplicate aliases during implementation.

## Typography

- **Display and editorial headings:** Playfair Display, typically bold or semibold.
- **Functional UI, body copy, and prices:** Plus Jakarta Sans.
- **Prices and totals:** use semibold/bold weight and tabular numerals where supported.
- **Desktop display:** 48px / 56px line height.
- **Mobile display:** 36px / 44px line height.
- **Large headlines:** 32px / 40px.
- **Medium headlines:** 24px / 32px.
- **Body large:** 16px / 26px.
- **Body medium:** 14px / 22px.
- **Small labels:** 12px / 16–18px.

Load the intended fonts reliably and provide sensible sans-serif/serif fallbacks. Keep menu descriptions and operational labels highly legible.

## Spacing and responsive layout

Use the spacing tokens from the source design file:

- Micro spacing: 4px and 8px.
- Standard component spacing: 16px.
- Section/component separation: 24px.
- Large section breaks: 40px.
- Mobile page margins/gutters: 16px.
- Tablet outer margins: 32px.
- Desktop outer margins: 48px.
- Desktop content width: cap at approximately 1280px.

Responsive behavior:
- **Mobile (under 640px):** single-column guest ordering, thumb-friendly actions, sticky tray/cart where shown.
- **Tablet (641–1024px):** flexible 6-column layout and compact split views when useful.
- **Desktop (over 1024px):** 12-column layout with clear max-width and generous gutters.
- Avoid horizontal overflow. Adapt staff tools for touch screens rather than merely shrinking desktop layouts.

## Shape, borders, and elevation

- Inputs and compact controls: about 8px corner radius.
- Standard cards and buttons: about 16px.
- Hero panels, sheets, and modals: about 24px.
- Use full pill shapes for filter chips, badges, and selected call-to-action patterns.
- Standard card shadow: `0 4px 20px -4px rgba(61, 35, 23, 0.06)`.
- Hover/lifted card shadow: `0 8px 30px -6px rgba(61, 35, 23, 0.12)`.
- Borders should be subtle, warm, and used only where they help distinguish surfaces.
- Use restrained transitions and respect reduced-motion preferences.

## Component guidance

### Buttons and touch targets
- Primary actions use espresso backgrounds and high-contrast white text.
- Secondary actions use a light cream surface with dark text and a subtle border.
- Terracotta is an accent for promotions and selected conversion moments, not a competing primary color.
- Aim for at least 48×48px touch targets on mobile; icon controls should be comfortably tappable.
- Include hover, focus, pressed, disabled, and loading states.

### Menu and food cards
- Use white cards with soft borders and approximately 16px corners.
- Food imagery should use consistent crops, commonly 4:3 or 1:1, and remain the visual focus.
- Keep name, short description, price, availability, and add action in a consistent hierarchy.
- Make dietary tags understandable and don't rely on color alone.

### Category filters
- Use horizontally scrollable pill tabs on narrow screens.
- Clearly distinguish active and inactive categories.
- Keep the selected state accessible and ensure keyboard interaction where applicable.

### Forms, cart, and checkout
- Clearly label fields and place validation messages beside the relevant controls.
- Keep quantities, modifiers, item subtotals, fees, and totals easy to scan.
- Preserve user input after validation errors.
- Show clear loading, empty, success, and failure states.
- Never display a successful payment/order state unless the relevant operation has actually succeeded.

### Sticky tray/cart
- Keep it visually separated from the page content, with enough contrast and safe-area padding.
- Show item count and subtotal when available.
- Ensure it does not cover important content or keyboard-focused controls.

### POS, kitchen display, and admin
- Prioritize operational clarity and speed over decorative elements.
- Use readable status labels, consistent order states, and obvious actions.
- Make tablet/desktop layouts dense enough for real workflows without sacrificing readability.
- Use semantic tables or accessible alternative layouts for data-heavy views.

## Motion, imagery, and performance

- Use motion to confirm an action or clarify hierarchy, not as decoration.
- Keep transitions brief and support reduced-motion settings.
- Preserve the supplied Stitch assets and brand direction; do not replace them with unrelated stock imagery.
- Optimize image size and loading; avoid heavy visual effects that delay menu interaction.
- If adding 3D effects, use them selectively and keep ordering flows fast and accessible.

## Accessibility

- Maintain readable contrast across all text and interactive states.
- Use semantic HTML, associated form labels, accessible button names, and visible keyboard focus.
- Communicate state with text/icons as well as color.
- Test keyboard navigation, screen-reader labels, reduced motion, and narrow viewport layouts.

## Screen references in this repository

The exported screen folders cover the main experience:
1. QR menu landing
2. Digital menu home
3. Category menu
4. Food item detail
5. Cart/table order review
6. Dine-in order confirmation
7. Live order tracking
8. Direct online ordering
9. Website home
10. Full online menu
11. Direct checkout
12. Direct order success
13. Customer loyalty and rewards
14. POS cashier station
15. Kitchen order display
16. Admin business dashboard

Use each screen's `code.html` as a reference for its structure and `screen.png` as the visual comparison target. These are exported design prototypes, not proof that production ordering, payment, authentication, POS, or kitchen integrations are implemented.

## Implementation rule

Before changing an existing screen, compare it against its Stitch export and reuse the shared tokens above. Prefer shared components and design tokens over one-off styling. Do not invent business details, menu prices, payment capabilities, or order statuses that have not been confirmed.
