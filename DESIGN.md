# Hers Cafe — Design System

## Overview

Hers Cafe is a warm, artisanal café digital experience concept. The design should feel welcoming, premium, tactile, and food-focused—not like a generic ordering template.

**Source of truth:** the exported Google Stitch screens and the accompanying design system assets. When implementing, inspect the exported screen images and code before introducing new patterns.

## Design principles

- **Warm and inviting:** use a café-inspired visual language with soft, natural tones.
- **Editorial, not cluttered:** give food photography and key actions room to breathe.
- **Clear ordering flow:** menu discovery, item details, cart, and checkout should be easy to understand.
- **Consistent across touchpoints:** QR menu, customer website, ordering flow, POS, kitchen display, and admin tools should feel related while being optimized for their users.
- **Mobile-first for guests:** QR scanning and table-side ordering are primarily mobile experiences.
- **Practical for staff:** POS and kitchen interfaces should prioritize speed, legibility, and status clarity.

## Color

Use the exact color tokens in the exported Stitch design-system file where available. Do not invent a competing palette.

- **Primary surfaces:** warm, light neutral tones.
- **Text:** high-contrast dark, warm-toned text for readability.
- **Accent:** use the existing brand accent sparingly for important actions, selected states, and highlights.
- **Borders and separators:** subtle warm neutrals rather than harsh, heavy outlines.
- **Status colors:** reserve distinct colors for success, warning, and error states; pair color with text or icons.

## Typography

- Follow the typefaces, scale, weights, and line heights defined in the exported design-system file.
- Use expressive heading typography for brand and editorial moments, with a highly readable body face for menus and operational screens.
- Keep item names, prices, modifiers, and primary actions easy to scan.
- Avoid overly small text, especially on mobile menus and staff-facing screens.

## Layout and spacing

- Use a consistent spacing scale based on the exported design tokens.
- Keep content aligned to a clear grid and maintain generous whitespace around featured food imagery.
- On mobile, keep primary actions reachable and avoid horizontal overflow.
- Use responsive layouts rather than scaling desktop screens down unchanged.
- Group related controls and information; use dividers and cards only where they improve hierarchy.

## Imagery

- Food and café imagery should feel authentic, appetizing, and consistent in lighting and treatment.
- Preserve the supplied brand assets and existing screen imagery where appropriate.
- Avoid unrelated stock imagery, mismatched image styles, or decorative images that compete with menu items.
- Provide useful alt text for meaningful images and sensible fallbacks when images fail to load.

## Components and interaction

### Buttons
- Establish clear primary, secondary, and tertiary action styles.
- Make labels specific and action-oriented.
- Include visible hover, focus, pressed, disabled, and loading states where applicable.

### Menu items and product details
- Present item name, description, price, and image consistently.
- Make add-ons, modifiers, quantity changes, and availability understandable.
- Clearly distinguish selected options and validation errors.

### Navigation
- Keep guest navigation simple and predictable.
- Maintain clear paths between categories, item details, cart, and checkout.
- For staff/admin tools, prioritize task-oriented navigation and visible current location.

### Forms and checkout
- Label every field and show validation beside the relevant input.
- Preserve entered information when validation fails.
- Communicate totals, fees, and order status transparently.
- Do not imply a payment succeeded unless the payment provider confirms it.

### POS and kitchen display
- Optimize for quick scanning and repeated use.
- Make order status, item details, and urgent changes obvious.
- Use large enough controls for touch operation and distinguish status with both text and visual cues.

### Feedback and states
Design loading, empty, success, error, unavailable-item, and offline/failure states—not just the ideal path. Interactive elements must perform their stated action; avoid decorative controls that appear functional but do nothing.

## Motion and depth

- Use subtle transitions to support feedback and hierarchy.
- Keep motion short and purposeful; respect reduced-motion preferences.
- Any 3D or depth effects should reinforce the café’s tactile character without reducing readability or slowing ordering.
- Prefer performance-conscious effects and provide a graceful fallback on low-powered devices.

## Accessibility

- Maintain strong text/background contrast.
- Use semantic HTML and correctly associated form labels.
- Ensure keyboard access and visible focus indicators.
- Provide accessible names for icon-only controls.
- Do not rely on color alone to communicate state.
- Respect reduced-motion settings and test layouts at narrow viewport widths.

## Responsive behavior

- **Guest QR menu and ordering:** mobile-first, fast to load, thumb-friendly.
- **Marketing website:** responsive editorial layout with clear brand story and ordering entry points.
- **POS and kitchen display:** prioritize tablet/desktop workflows while remaining usable on touch screens.
- **Admin dashboard:** use responsive tables or alternate compact layouts for smaller screens.

## Implementation guidance

1. Treat the exported Stitch screens and design-system file as the primary reference.
2. Reuse shared tokens and components instead of duplicating one-off styles.
3. Keep content, pricing, availability, and order state data-driven.
4. Validate every user-facing interaction and error path.
5. Optimize images and defer nonessential visual effects.
6. Keep this concept clearly separate from production integrations until ordering, payment, authentication, and operational workflows have been implemented and tested.

## Project status

This repository currently documents a design concept. The exported screens are references for future implementation; they do not, by themselves, constitute a deployed or production-ready ordering system.
