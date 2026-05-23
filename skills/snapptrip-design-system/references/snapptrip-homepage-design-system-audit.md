# Snapptrip Homepage Design System Audit

Source: https://www.snapptrip.com/  
Audit date: 2026-05-17  
Scope: homepage only, RTL Persian travel-booking experience

## 1. Executive Summary

Snapptrip's homepage design system is a pragmatic travel-commerce interface built around a white surface, strong red primary actions, blue secondary actions, dense but readable Persian content, and repeated rounded modules. The system appears to use Next.js with utility classes and component CSS modules. The visual language is closer to an operational booking product than a marketing landing page: compact navigation, a functional service switcher, high-visibility search, promotional image carousels, SEO content, FAQ accordions, and a link-heavy footer.

The most reusable system primitives are:

- RTL-first layout and spacing with a centered `1248px` content shell.
- IRANSansXFa as the core typeface, with Material Icons for service and control icons.
- Red primary brand color for active service and primary actions, blue secondary color for app/download and secondary accents.
- 8px corner radius for most cards, panels, buttons, and imagery.
- Thin neutral outlines for section boundaries, dividers, app badges, tabs, and form fields.
- State overlays instead of heavy color changes for hover, focus, pressed, and disabled states.

## 2. Evidence and Constraints

Verified from production HTML and CSS:

- The root document is `dir="rtl"` and `lang="fa"`.
- Main content container uses `max-w-[1248px]` with horizontal padding.
- Header height is `64px`.
- Hero/travel banner uses an aspect ratio of `1200 / 208`.
- Service tabs are `72px` tall and use icon over label.
- Search skeleton and form controls target `56px` field height.
- Primary carousel cards use `rounded-lg`, full-width slides, and responsive desktop/mobile images.
- Footer uses multiple row sections separated by `outline-thin` borders and a dim neutral background.

Screenshot capture note:

- Browser rendering was attempted, but the in-app browser navigation timed out. This audit therefore uses production HTML, loaded page text, published CSS tokens, and markup-derived responsive classes as the source of truth. A visual QA pass should still be run in a browser before turning this into a final Figma or coded component library.

## 3. Design Tokens

### Color

| Token | Value | Usage |
| --- | --- | --- |
| `color.primary` | `#ed071a` | Active hotel tab, primary actions, brand emphasis |
| `color.primary.inverse` | `#ed071a99` | Lower-emphasis primary overlays |
| `color.secondary` | `#575eff` | Secondary buttons, app download CTA, supporting accent |
| `color.error` | `#b3261e` | Error actions and messages |
| `color.warning` / `color.caution` | `#ffc21c` | Warnings and caution tags |
| `color.success` | `#22a958` | Success states |
| `color.background` | `#ffffff` | Page and card surface |
| `color.dimBackground` | `#f8f9fd` | Footer and low-emphasis background bands |
| `color.outlineThin` | `#ebecf2` | Borders and dividers |
| `color.outlineThick` | `#f8f9fd` | Footer background and thick neutral areas |
| `color.dimSurfaces` | `#ebecf2` | Disabled contained button background, skeletons |
| `color.textHigh` | `#040a1fde` | Main text |
| `color.textMedium` | `#040a1f99` | Supporting text, inactive icons |
| `color.textDisabled` | `#040a1f61` | Disabled text and controls |
| `color.onColorHigh` | `#ffffff` | Text on filled primary/secondary surfaces |

### Interaction Overlays

| Token | Value | Usage |
| --- | --- | --- |
| `states.neutral.hover` | `#0000000a` | Text/neutral button hover |
| `states.neutral.focus` | `#0000001f` | Focus-visible overlay |
| `states.neutral.pressed` | `#0000001a` | Pressed overlay |
| `states.primary.hover` | `#ff201b0a` | Primary tab/button hover |
| `states.primary.focus` | `#ff201b1f` | Primary focus-visible overlay |
| `states.primary.pressed` | `#ff201b1a` | Primary pressed overlay |
| `states.secondary.hover` | `#575eff0a` | Secondary hover |
| `states.secondary.focus` | `#575eff1f` | Secondary focus |
| `states.secondary.pressed` | `#575eff1a` | Secondary pressed |

### Typography

Typeface:

- Sans: `IRANSansXFa`
- Serif fallback: `IRANSansXFa`
- Mono fallback: `IRANSansXFa`
- Icon families: `Material Icons`, `Material Icons Outlined`, `Material Icons Round`, `Material Icons Sharp`

Type scale:

| Token | Size / Line / Weight | Usage |
| --- | --- | --- |
| `headline-3` | `47px / 56px / 400` | Rare large display moments |
| `headline-4` | `33px / 36px / 400` | Large section emphasis |
| `headline-5` | `23px / 24px / 400` | Desktop support phone and larger footer headings |
| `headline-6` | `19px / 24px / 500` | Section headers, FAQ group headers |
| `subtitle-1` | `16px / 24px / 500` | Component titles |
| `subtitle-2` | `14px / 24px / 500` | Compact labels and mobile app subtitle |
| `body-1` | `16px / 24px / 400` | Long-form SEO body copy |
| `body-2` | `14px / 20px / 400` | Compact body text |
| `button` | `14px / 16px / 500` | Button labels |
| `caption` | `12px / 16px / 400` | Helper text, dense metadata |

Typography guidance:

- Preserve Persian shaping by using the site font first and keeping `dir="rtl"` at the document root.
- Use `text-align: start` and logical inline properties rather than hardcoded right/left where possible.
- Keep section headings modest. The homepage uses `16px` headings on smaller screens and promotes to `19px` at large breakpoints.

### Spacing, Layout, and Radius

| Token / Pattern | Value | Usage |
| --- | --- | --- |
| Content shell | `max-width: 1248px` | Header, search, homepage content |
| Page padding | `16px`, `24px` | Header and content horizontal breathing room |
| Header height | `64px` | Top navigation |
| Service tab height | `72px` | Icon over label tabs |
| Search field height | `56px` | Destination, date, passenger/search controls |
| Button heights | `32px`, `36px`, `40px`, `48px`, `56px` | X-small through x-large |
| Main card radius | `8px` | Search section, buttons, badges, footer certificates |
| Pill radius | `9999px` | Round buttons and carousel arrows |
| Carousel gap | `16px` | Slide spacing |
| Section gap | `48px` | Main promotional sections |
| Footer row padding | `32px 0` | Support, link, app, about, copyright sections |

### Elevation

Most homepage modules are flat and divided with borders. Elevation is reserved for floating and overlay surfaces.

| Token | Value | Usage |
| --- | --- | --- |
| `shadow-0` | `none` | Header default and flat modules |
| `shadow-1` | subtle 3-layer shadow | Light raised surfaces |
| `shadow-4` | medium app-bar shadow | Scrolled header |
| `shadow-8` | stronger overlay shadow | Sheets and popovers |
| `shadow-gradient` | inset white plus shadow | Mobile app promotion card |

## 4. Component Inventory

### Header and Top Navigation

Anatomy:

- `64px` high header.
- Centered `1248px` container.
- Snapptrip logo, right-side nav area, agency/company link on medium and larger screens.
- Uses neutral text buttons rather than heavy nav chrome.

States:

- Default header is flat.
- Scrolled header can use `shadow-4`.
- Text actions use neutral hover, focus, and pressed overlays.

Responsive:

- Desktop keeps logo and agency/company link visible.
- Mobile hides secondary desktop nav and relies on compact or client-rendered controls.

Accessibility:

- Logo link has `aria-label="snapptrip"`.
- Keep top-level nav landmarks distinct if adding account, language, or menu actions.

### Mobile App Promotion Banner

Anatomy:

- Fixed bottom mobile card.
- App icon `48px`.
- Title: `اپلیکیشن اسنپ‌تریپ`
- Subtitle: `رزرو و تجربه راحت سفر`
- Secondary round download button.
- Absolute close icon using Material Icon `cancel`.

Visual:

- Background `#F1F0FF`.
- `12px` padding.
- `12px` gap.
- `12px` radius.
- Border `2px` with on-color medium emphasis.
- Uses slide-up/fade animation.

Guidance:

- Keep this mobile-only.
- Close target should be at least `40px` effective hit area, even if the visible icon is smaller.

### Hero Travel Banner

Anatomy:

- Full-width image inside the content area.
- Aspect ratio `1200 / 208`.
- Uses WebP production asset.

Responsive:

- Hidden below medium in current markup.
- Desktop content uses the centered shell.
- Tablet layout can display outside the desktop-only wrapper.

Guidance:

- Treat this as a contextual travel banner, not a hero headline. It supports the search module rather than replacing it.

### Service Tabs

Services:

- Hotel: `business`, active.
- Flight: `flight`.
- Bus: `directions_bus`.
- Villa: `house`.
- Tour: `tour`.

Anatomy:

- Each tab is a full-width flex item.
- Icon sits above label.
- `72px` height.
- Active tab has primary icon, primary label, and `2px` bottom border.
- Inactive tabs use medium-emphasis icon and high-emphasis label.

States:

- Hover: primary hover overlay.
- Pressed: primary pressed overlay.
- Transition: `300ms cubic-bezier(0.4, 0, .2, 1)`.

Responsive:

- Tabs remain equally distributed.
- Labels should stay short and never wrap unless localized names grow substantially.

Accessibility:

- If this is semantically a route switcher, anchors are acceptable.
- If converted to in-page tabs, use `role="tablist"`, `role="tab"`, and `aria-selected`.

### Hotel Search Module

Current visible structure:

- Section wrapper with rounded `8px` corners.
- Border appears from medium breakpoint upward.
- White inner surface.
- Top service-tab row.
- Search content area with `40px` desktop padding and `24px` vertical mobile padding.
- Skeletons reveal the intended layout: destination control, date range control, guests/rooms, search button.

Field dimensions:

- Form controls target `56px` height.
- Destination field flexes.
- Date range control uses fixed desktop width around `283px`.
- Search action compresses to about `96px` on xl and stretches on smaller screens.

Guidance:

- Use a `56px` form-control token for all booking search fields.
- Keep labels concise and high contrast.
- Search button should be full-width on mobile, fixed/action-sized on wide desktop.
- Date and passenger pickers should use elevation only when opened.

Accessibility:

- All inputs need accessible labels in Persian.
- Date range picker must support keyboard selection and announce selected start/end dates.
- Search button should remain disabled only when required fields are invalid, with visible helper text.

### Promotional Carousels

Anatomy:

- Section heading: `رزرو هتل و هتل آپارتمان`.
- First carousel: large single-slide promotional banners.
- Second carousel: multiple `min-width: 288px` cards.
- Images use `rounded-lg`, `object-cover`, and separate desktop/mobile sources.
- Desktop arrows are circular, dark, `36px`, and appear on hover.

Behavior:

- Desktop arrows are hidden until the carousel group is hovered.
- Disabled arrows remain hidden/disabled.
- Touch panning is enabled.

Responsive:

- Mobile uses horizontal overflow with `24px` edge breathing room.
- Large desktop keeps slides aligned to the content shell.

Accessibility:

- Each image needs meaningful alt text when it advertises a promotion.
- Arrows should have Persian `aria-label` values, such as `بنر قبلی` and `بنر بعدی`.
- Consider pagination dots or slide count for screen-reader context.

### Popular City Links

Anatomy:

- Section icon: `pin_drop`.
- Header: `محبوبترین شهرهای ایران`.
- Link list includes Tehran, Mashhad, Shiraz, Isfahan, Kish, Qeshm, Tabriz, Kashan, Yazd, Rasht, Ramsar, Bandar Abbas, Kermanshah, Khorramabad, Sari, Qom.

Guidance:

- Treat as a compact link grid, not cards.
- Use high-emphasis text, underline on hover, and clear focus rings.
- Keep city names short and destination-specific.

Responsive:

- Desktop can use multi-column flow.
- Mobile should preserve a tappable row or chip-like layout with enough spacing.

### SEO Content Blocks

Anatomy:

- Long-form Persian headings and body copy.
- Uses `h2` for major topics and `h3` for nested guidance.
- Includes ordered and unordered lists plus table-like glossary content.

Guidance:

- Use `body-1` for paragraphs.
- Maintain `24px` line-height for readability.
- Use `text-align: start`, not forced justification except where already intentional.
- Preserve semantic heading order for SEO and accessibility.

Content style:

- Copy is direct, practical, and search-oriented.
- Avoid decorative layouts around this content. The current page keeps it text-forward.

### FAQ Accordion

Anatomy:

- Header icon: `help_outline`.
- Section heading: `پاسخ به برخی سوالات`.
- Accordion items have title, optional content, and Material Icon chevron.
- Some items are initially expanded.

States:

- Expanded: `keyboard_arrow_up`.
- Collapsed: `keyboard_arrow_down`.
- Disabled title/subtitle/icon use disabled text token.

Guidance:

- Use native `button` controls for accordion headers.
- Set `aria-expanded` and `aria-controls`.
- Keep body content in `body-1` or `body-2` depending on density.

### Route Planning Link Groups

Anatomy:

- Header: `سفر بعدیت رو از الان برنامه ریزی کن`.
- Three-column grid on xl.
- Groups include domestic flights, international flights, bus routes, villa stays, and hotel city routes.
- Each group behaves like an accordion section with link lists.

Responsive:

- Single-column or stacked grid on mobile/tablet.
- Three columns on xl.

Guidance:

- Links should use high-emphasis text with hover underline.
- Keep groups expanded where SEO/link discoverability is important.

### Footer

Sections:

- Support row with title and phone number.
- Footer link columns: travel services, features, more information.
- Contact information.
- Social media area.
- App download badges.
- About Snapptrip text.
- Trust/certificate badges.
- Copyright row.
- Mobile service navigation group.

Visual:

- Footer background uses `outline-thick` / `#f8f9fd`.
- Rows use `outline-thin` dividers.
- Certificate badges use `100px x 100px` bordered rounded boxes.
- App badges are `48px` tall.

Responsive:

- Support row stacks on mobile, becomes row layout at `1024px`.
- Link columns use two columns on mobile and four at desktop.
- Contact and social areas stack on mobile and split across desktop.

Accessibility:

- Phone numbers should use `dir="ltr"` for readability and should be linkable via `tel:`.
- Trust badge images need descriptive alt text.
- Social links need accessible names, not just icons.

## 5. Button and Control System

Button sizes:

| Size | Height | Equal-dimension width |
| --- | --- | --- |
| x-small | `32px` | `32px` |
| small | `36px` | `36px` |
| medium | `40px` | `40px` |
| large | `48px` | `48px` |
| x-large | `56px` | `56px` |

Button variants:

- Contained: filled primary, secondary, error, or neutral.
- Round: same as contained, radius `9999px`.
- Outline: `1px` border, `8px` radius.
- Round outline: `1px` border, radius `9999px`.
- Text: transparent background, compact horizontal padding.

Shared behavior:

- Label: `14px / 16px / 500`.
- Padding: `12px` inline for standard buttons.
- Gap: `4px`.
- Outline offset: `2px`.
- Transition: `150ms cubic-bezier(0.4, 0, .2, 1)`.
- Disabled: not-allowed cursor, dim surface or transparent background, disabled text color.

Implementation guidance:

- Prefer Material Icon names for controls already used by the site.
- Icon-only buttons must include accessible labels.
- Keep primary red for booking-critical actions. Use secondary blue for supporting actions such as app download, not destructive or booking-confirmation actions.

## 6. Responsive Rules

Breakpoints observed in markup:

- `md`: `768px`.
- `lg`: `1024px`.
- `xl`: `1280px`.
- `2xl`: `1536px`.

Homepage behavior:

- Under `md`, the search module removes the desktop border and uses vertical padding.
- Under `lg`, hero/banner placement and carousel edge spacing shift for smaller screens.
- At `lg`, desktop-oriented nav, footer split layout, and larger section headings activate.
- At `xl`, search controls use a single-row layout with fixed-width controls and compact search action.
- At `2xl`, footer/container padding can collapse to align exactly with the content shell.

RTL rules:

- Use logical properties such as `start`, `end`, `margin-inline`, and `inset-inline`.
- Keep icon glyph direction `ltr` for Material Icons while text remains RTL.
- Use `dir="ltr"` only for phone numbers, IDs, or Latin route codes.

## 7. Accessibility Review

Strengths:

- Document language and direction are set correctly.
- Logo has an accessible label.
- Semantic heading content exists for SEO and screen readers.
- Link-heavy areas use real anchors.

Measured contrast samples:

| Pair | Ratio | Result |
| --- | --- | --- |
| Primary red `#ed071a` on white | `4.52:1` | Passes WCAG AA normal text |
| White on primary red `#ed071a` | `4.52:1` | Passes WCAG AA normal text |
| Secondary blue `#575eff` on white | `4.72:1` | Passes WCAG AA normal text |
| White on secondary blue `#575eff` | `4.72:1` | Passes WCAG AA normal text |
| High-emphasis text on white | `19.66:1` | Passes AAA |
| Medium-emphasis text on white | `5.70:1` | Passes AA |
| Disabled text on white | `2.55:1` | Use only for disabled/non-essential content |
| High-emphasis text on footer dim background | `18.68:1` | Passes AAA |

Risks to verify visually and interactively:

- Carousel arrows need accessible names and keyboard operation.
- Accordion controls need `aria-expanded`.
- Service navigation should expose active state beyond color.
- Search field skeletons imply async client rendering; loading state should announce itself or avoid trapping focus.
- Mobile fixed app banner can obscure bottom content and needs a reliable close control.
- Red primary on white passes for large UI use, but red text and small active labels should be checked in context.
- Footer contrast is likely acceptable for high-emphasis text, but medium-emphasis copy on `#f8f9fd` should be tested.

Recommended acceptance checks:

- Keyboard: tab through header, service tabs, search fields, carousel arrows, FAQ, footer links.
- Screen reader: confirm route tabs, date range picker, accordions, and close/download app banner labels.
- Contrast: test primary red text, inactive tab labels, helper text, footer secondary text, and disabled controls.
- Mobile: ensure fixed app banner does not cover route/footer links or search submit actions.

## 8. Component Naming Proposal

Use these names if this audit becomes a shared library or Figma file:

- `AppShell.Header`
- `Promo.AppInstallBanner`
- `Travel.HeroBanner`
- `Travel.ServiceTabs`
- `Search.HotelSearchPanel`
- `Search.DestinationField`
- `Search.DateRangeField`
- `Search.GuestRoomField`
- `Carousel.PromoBanner`
- `Carousel.CardRail`
- `Links.CityGrid`
- `Content.SeoArticle`
- `Content.FaqAccordion`
- `Links.RoutePlanningGroups`
- `Footer.SupportBar`
- `Footer.LinkColumns`
- `Footer.ContactBlock`
- `Footer.DownloadBadges`
- `Footer.TrustBadges`

## 9. Next Steps

To turn this audit into production assets:

1. Run visual captures at `1440px`, `1024px`, `768px`, and `390px` viewport widths.
2. Confirm exact computed dimensions for rendered search controls after client-side hydration.
3. Build a token file from the verified color, type, radius, spacing, elevation, and state values.
4. Convert the inventory into Figma components or coded components, preserving the homepage naming proposal.
5. Add accessibility annotations for search, accordion, carousel, and mobile app banner interactions.
