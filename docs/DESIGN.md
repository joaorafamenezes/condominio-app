---
name: CondoResolve
colors:
  surface: '#f8f9ff'
  surface-dim: '#cbdbf5'
  surface-bright: '#f8f9ff'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#eff4ff'
  surface-container: '#e5eeff'
  surface-container-high: '#dce9ff'
  surface-container-highest: '#d3e4fe'
  on-surface: '#0b1c30'
  on-surface-variant: '#3d4a42'
  inverse-surface: '#213145'
  inverse-on-surface: '#eaf1ff'
  outline: '#6d7a72'
  outline-variant: '#bccac0'
  surface-tint: '#006c4a'
  primary: '#006948'
  on-primary: '#ffffff'
  primary-container: '#00855d'
  on-primary-container: '#f5fff7'
  inverse-primary: '#68dba9'
  secondary: '#545f73'
  on-secondary: '#ffffff'
  secondary-container: '#d5e0f8'
  on-secondary-container: '#586377'
  tertiary: '#006194'
  on-tertiary: '#ffffff'
  tertiary-container: '#007bb9'
  on-tertiary-container: '#fdfcff'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#85f8c4'
  primary-fixed-dim: '#68dba9'
  on-primary-fixed: '#002114'
  on-primary-fixed-variant: '#005137'
  secondary-fixed: '#d8e3fb'
  secondary-fixed-dim: '#bcc7de'
  on-secondary-fixed: '#111c2d'
  on-secondary-fixed-variant: '#3c475a'
  tertiary-fixed: '#cce5ff'
  tertiary-fixed-dim: '#93ccff'
  on-tertiary-fixed: '#001d31'
  on-tertiary-fixed-variant: '#004b73'
  background: '#f8f9ff'
  on-background: '#0b1c30'
  surface-variant: '#d3e4fe'
typography:
  display-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 36px
    fontWeight: '700'
    lineHeight: 44px
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 28px
    fontWeight: '700'
    lineHeight: 36px
    letterSpacing: -0.015em
  headline-lg-mobile:
    fontFamily: Plus Jakarta Sans
    fontSize: 24px
    fontWeight: '700'
    lineHeight: 32px
    letterSpacing: -0.01em
  headline-md:
    fontFamily: Plus Jakarta Sans
    fontSize: 22px
    fontWeight: '600'
    lineHeight: 28px
    letterSpacing: -0.01em
  headline-sm:
    fontFamily: Plus Jakarta Sans
    fontSize: 18px
    fontWeight: '600'
    lineHeight: 24px
  body-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
  body-md:
    fontFamily: Plus Jakarta Sans
    fontSize: 14px
    fontWeight: '400'
    lineHeight: 20px
  body-sm:
    fontFamily: Plus Jakarta Sans
    fontSize: 12px
    fontWeight: '400'
    lineHeight: 16px
  label-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 14px
    fontWeight: '600'
    lineHeight: 20px
    letterSpacing: 0.01em
  label-md:
    fontFamily: Plus Jakarta Sans
    fontSize: 12px
    fontWeight: '600'
    lineHeight: 16px
    letterSpacing: 0.02em
  label-sm:
    fontFamily: Plus Jakarta Sans
    fontSize: 11px
    fontWeight: '700'
    lineHeight: 14px
    letterSpacing: 0.04em
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  gutter: 1.5rem
  gutter-mobile: 1rem
  margin: 2rem
  margin-mobile: 1rem
  space-xs: 0.25rem
  space-sm: 0.5rem
  space-md: 1rem
  space-lg: 1.5rem
  space-xl: 2.5rem
---

## Brand & Style

The design system establishes a welcoming, dependable, and systematically clear digital environment for residential community management. Built to bridge property managers (síndicos), residents, and field maintenance staff, the visual language balances civic transparency with domestic warmth.

### Visual Aesthetic & Philosophy
The aesthetic blends **Modern Corporate** reliability with a refined **Lifestyle Functionalism**:
- **Clarity over ornament:** Information hierarchy is immediate. Residents seeking immediate answers (maintenance updates, gate clearances, amenity reservations) encounter uncluttered screens and deliberate whitespace.
- **Calm authority:** The palette evokes structural durability, environmental freshness, and operational resolution.
- **Tactile feedback:** Interactive elements provide subtle, reassuring state transitions without gimmicks, evoking the precision of modern smart-building hardware.

## Colors

The palette is engineered to communicate security, rapid resolution, and environmental harmony within residential spaces.

### Roles & Intent
- **Primary (`#059669` - Emerald Resolution):** Used for primary conversion points, success metrics, resolved ticket states, and active confirmation indicators. Signals health, green community spaces, and completed resolutions.
- **Secondary (`#1E293B` - Slate Navy):** Anchors headers, high-level navigation, key structural containers, and dominant text elements. Conveys governance, durability, and institutional trust.
- **Tertiary (`#0284C7` - Cyan Slate):** Employed for informational indicators, amenity reservation highlights, calendar badges, and ongoing communications.
- **Neutral (`#64748B` - Slate Gray):** Governs structural borders, secondary labels, disabled conditions, and metadata.

### Occurrence Status Palette (Fixed Semantic Tokens)
- **Aberto (Open / New):** Amber warning tint (Background: `#FEF3C7`, Text/Border: `#B45309`).
- **Em Análise (Under Review):** Ocean blue tint (Background: `#E0F2FE`, Text/Border: `#0369A1`).
- **Em Execução (In Progress):** Focused indigo tint (Background: `#E0E7FF`, Text/Border: `#4338CA`).
- **Resolvido (Resolved):** Emerald success tint (Background: `#D1FAE5`, Text/Border: `#047857`).
- **Cancelado (Canceled / Closed):** Muted slate tint (Background: `#F1F5F9`, Text/Border: `#475569`).

## Typography

The design system implements **Plus Jakarta Sans** across all roles to achieve a blend of contemporary geometric clarity and approachable human geometry.

### Hierarchy & Usage
- **Headlines & Titles:** Set with tighter tracking (`-0.01em` to `-0.02em`) and heavier weights (600/700) to maintain crisp, authoritative section landmarks.
- **Body Content:** Kept at standard tracking with generous line-height ratios (1.4–1.5x) to ensure clear legibility for bylaws, incident logs, assembly minutes, and notifications.
- **Labels & Status Pills:** Shifted to semi-bold and bold weights with subtle positive letter spacing for quick ocular scanning in data tables and status boards.

## Layout & Spacing

A structured fluid layout provides a steady baseline rhythm for complex operational dashboards and streamlined resident views.

### Grid & Breakpoints
- **Desktop (1024px+):** 12-column responsive layout with `2rem` outer page margins and `1.5rem` gutters. Content containers capped at `1280px` max-width to protect line lengths.
- **Tablet (768px – 1023px):** 8-column layout with `1.5rem` outer margins and `1rem` gutters. Two-column cards collapse to single or stacked variations.
- **Mobile (< 768px):** 4-column layout with `1rem` outer margins and `1rem` gutters. Actions, data grids, and filter toolbars dock to bottom sheet drawers or stack vertically.

## Elevation & Depth

Visual hierarchy uses **tonal layer stacking combined with ultra-diffused ambient drop shadows** and delicate micro-borders to maintain order without heavy visual weight.

### Depth Hierarchy
1. **Level 0 (Canvas Base):** Background canvas rendered in cool neutral off-white (`#F8FAFC`).
2. **Level 1 (Card & Module Layer):** Surface containers use pure white (`#FFFFFF`) framed by a low-contrast 1px border (`#E2E8F0`) and an ambient shadow: `0 1px 3px 0 rgba(15, 23, 42, 0.05), 0 1px 2px -1px rgba(15, 23, 42, 0.05)`.
3. **Level 2 (Interactive Elements & Dropdowns):** Popovers, dropdown menus, and hovered cards elevate using `0 10px 15px -3px rgba(15, 23, 42, 0.08), 0 4px 6px -4px rgba(15, 23, 42, 0.04)`.
4. **Level 3 (Modal Overlays & System Notices):** Emergency alerts, maintenance creation dialogs, and booking confirmations sit over an assertive backdrop scrim (`#0F172A` at 45% opacity) with shadow `0 20px 25px -5px rgba(15, 23, 42, 0.12), 0 8px 10px -6px rgba(15, 23, 42, 0.06)`.

## Shapes

The design system adopts **Roundedness Level 2 (Rounded)**:
- Standard elements (buttons, inputs, status badges) apply `0.5rem` (8px) radius.
- Cards, dashboards tiles, and notification panels feature `rounded-lg` at `1rem` (16px).
- Modals, large feature containers, and major app modules use `rounded-xl` at `1.5rem` (24px).
- Fully pill-shaped geometry (`9999px`) is reserved exclusively for numerical avatars, status indicators, and micro-tags.

## Components

### Buttons
- **Primary:** Background in emerald `#059669`, text `#FFFFFF`, hover `#047857`, active `#065F46`. 8px border radius, 40px height for desktop (`space-sm` vertical, `space-md` horizontal).
- **Secondary:** Surface `#FFFFFF`, border 1px solid `#CBD5E1`, text `#1E293B`. Hover shifts background to `#F8FAFC` and border to `#94A3B8`.
- **Destructive/Urgent:** Subtle rose wash `#FEE2E2` with text `#B91C1C` for incident removals or dispute filings.

### Occurrence Badges & Chips
Status badges use uppercase tracking (`label-sm`), pill shapes (`rounded-full`), and strict semantic contrast:
- **Aberto:** Amber background `#FEF3C7`, text `#92400E`, dot indicator `#D97706`.
- **Em Análise:** Blue background `#E0F2FE`, text `#075985`, dot indicator `#0284C7`.
- **Em Execução:** Indigo background `#E0E7FF`, text `#3730A3`, dot indicator `#4F46E5`.
- **Resolvido:** Emerald background `#D1FAE5`, text `#065F46`, dot indicator `#059669`.
- **Cancelado:** Neutral background `#F1F5F9`, text `#475569`, dot indicator `#94A3B8`.

### Input Fields & Controls
- **Inputs & Selects:** White background, 1px border `#CBD5E1`, height 42px, radius 8px, text `#0F172A`. Focused state transitions border to `#059669` accompanied by a 3px soft focus ring in `rgba(5, 150, 105, 0.15)`.
- **Checkboxes & Radios:** Emerald active fill (`#059669`) with white vector tick/dot. Slate border (`#94A3B8`) in unselected resting state.

### Incident Cards & Community Modules
- Structured with high clarity: top row shows block/unit metadata with status badge; middle section provides occurrence title and brief snippet; bottom footer displays reporter avatar, timestamp, and comment counter.
- Bounded by 1px `#E2E8F0` border, transitions smoothly on hover via subtle `-1px` vertical translation and elevation shadow tier 2.

### Specialized Condominium Components
- **Amenity Booking Grid:** Date/slot picker using emerald fills for selected reservations, light red cross-hatching for locked hours, and clear neutral pill tags for available slots.
- **Visitor Quick-Pass Generator:** Clean card format prioritizing quick QR code generation, guest name input, and scheduled expiration timestamps.