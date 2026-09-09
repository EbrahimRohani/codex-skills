---
name: snapptrip-design-system
description: Use when Codex needs to design, audit, critique, prototype, or implement UI consistent with Snapptrip's homepage design system, especially RTL Persian travel-booking experiences, homepage redesigns, booking search panels, service tabs, promotional carousels, footer/link systems, or Snapptrip-branded screenshots and mockups.
---

# Snapptrip Design System

Use this skill to keep Snapptrip UI work aligned with the homepage design-system audit captured on 2026-05-17.

## Quick Start

For any Snapptrip-branded UI, load `references/snapptrip-homepage-design-system-audit.md` before making visual, layout, token, or component decisions.

Apply these core rules by default:

- Build RTL-first Persian interfaces with `dir="rtl"` and `lang="fa"`.
- Use a practical travel-booking product layout, not a decorative marketing landing page.
- Use a white surface, thin neutral borders, compact information density, and 8px radii.
- Use primary red `#ed071a` for active services and main booking actions.
- Use secondary blue `#575eff` for supporting CTAs such as app download.
- Use IRANSansXFa-style typography and Material Symbols/Material Icons-style glyphs.
- Use a centered `1248px` desktop content shell with responsive `16px` to `24px` horizontal padding.

## Common Tasks

When designing or generating screenshots:

- Include the homepage primitives from the audit: top navigation, app promotion, service tabs, hotel search panel, promotional carousel, city links, FAQ, and footer blocks.
- Keep Persian text readable, aligned to the logical start, and free of overlap.
- Favor real travel and hotel imagery over abstract gradients or decorative shapes.
- Show desktop, tablet, and mobile variants when the user asks for a homepage or responsive redesign.

When implementing UI:

- Convert the audit tokens into local theme variables before creating component-specific styles.
- Preserve the button sizes, typography scale, state overlays, and field heights from the audit.
- Use semantic controls for tabs, accordions, links, inputs, date pickers, and carousel controls.
- Verify keyboard access, focus states, and contrast for primary red, secondary blue, text, tabs, accordions, and footer content.

When reviewing UI:

- Compare against the reference audit for token drift, RTL mistakes, spacing changes, missing states, inaccessible controls, and over-marketed visual treatment.
- Treat the audit as homepage-first; do not invent checkout, account, hotel-detail, or search-results rules unless the user provides those surfaces.

## Reference

Detailed tokens, components, responsive behavior, accessibility notes, and naming proposals live in:

`references/snapptrip-homepage-design-system-audit.md`
