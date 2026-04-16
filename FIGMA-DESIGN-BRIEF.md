# Figma Design Brief — PLG Onboarding Phase 1

**For:** Design team
**From:** Daniel Harper
**Date:** 2026-04-16
**HTML prototype:** Open `prototype/index.html` in a browser for clickable reference
**Full wireframe spec:** `plg/phase1/02-wireframes.md`

---

## Design System Components to Use

All components from **RudderStack Design System 1.0** Figma library. Component names below match the library.

### Buttons
| Usage | Component | Variant |
|-------|-----------|---------|
| Primary CTA ("Create account", "Continue", "Finish setup") | `button-primary` | Default, Large |
| Secondary ("Back", "Test connection") | `button-secondary` | Default |
| Text/link ("Skip", "Docs", "Learn more") | `button-tetiary` | Default |
| Google OAuth | `button-secondary` | With leading Google icon, Large |

### Inputs
| Usage | Component | Notes |
|-------|-----------|-------|
| Text fields (name, email, org) | Standard input from design system | Height: 36px, border-radius: 6px, border: #D8DEE4 |
| Dropdowns (role, attribution) | Select component | With chevron icon |
| Search field (tech stack tools) | Input with search icon prefix | Typeahead behavior |

### Selection Controls
| Usage | Component | Notes |
|-------|-----------|-------|
| Persona type (Screen A) | `radio button` | Styled as cards with icon + title + description |
| Setup preferences (Screen A) | Checkbox variant | Styled as selectable cards |
| Language selection (Screen A) | Checkbox variant | Horizontal chip layout |
| Region (Screen B) | `radio button` | Two-column card layout |
| Migration source (Screen B) | `radio button` | Vertical list, compact |
| Warehouse picker (Screen B, Install step 3) | Chip/tag component | With emoji/icon prefix, selectable |
| Event volume (Screen B) | `radio button` | Horizontal wrap layout |
| Goal cards (Screen C) | Custom card component | 2-column grid, checkbox in corner, icon + title + desc |
| Plan cards (Install step 4) | Custom card component | 3-column grid, border highlight on selected |

### Layout
| Usage | Notes |
|-------|-------|
| Auth screens (Signup, Setup Workspace) | Centered single-column, max-width 520px (580px for tech stack), white card on grey-50 background |
| Install screens | Centered, max-width 800px, step indicator at top |
| Quick Start drawer | 480px wide left panel, alongside main app content |

### Other Components
| Usage | Component/Pattern | Notes |
|-------|-------------------|-------|
| Progress bar (Setup Workspace) | 4px horizontal bar | Blue fill, 33%/66%/100% per step |
| Step indicator (Install) | 5 dots with connecting lines | Blue=active/complete, grey=pending |
| Tabs (Install step 1) | `single tab` component | 2 tabs: npm/CLI, JS snippet |
| Code blocks | Dark (grey-900) background | Monospace font, Copy button top-right |
| Event monitor | Bordered box | Spinner animation while waiting, green checkmark on receipt |
| Toggles (Install step 2) | Switch/toggle component | ON=blue, OFF=grey |
| Badges | Tag/badge component | ENTERPRISE (purple), MOST POPULAR (blue), GROWTH TRIAL (blue) |
| Chips (selected tools) | Tag with X dismiss | Blue border when selected |
| Section headers (Quick Start) | Text, uppercase, 12px, grey-500 | With counter on right |
| Lock icon | FontAwesome `lock` or equivalent | On locked checklist items |
| Checklist items | Custom list item | Circle icon (complete/current/pending/locked/greyed) + title + arrow |

---

## Screen-by-Screen Design Notes

### Screen 1: Signup
- **Layout:** Centered card (520px) on grey-50 background
- **Logo:** RudderStack logo + wordmark, centered
- **Headline:** "Start your free RudderStack account" (24px, 600 weight)
- **Subhead:** "30-day free trial of all Growth-tier features" (14px, grey-500)
- **Google button:** Full-width, white bg, grey border, Google logo left-aligned
- **Divider:** "or sign up with email" with horizontal rules
- **Form:** 4 required fields + 1 optional + TOS checkbox + CTA
- **Footer:** "Trusted by 10,000+ data teams" + "Already have an account? Login"

### Screens 2-4: Setup Your Workspace
- **Shared:** Progress bar at top (33/66/100%), step counter, "Skip" link top-right
- **Screen A:** 3 question blocks — persona (radio cards), setup prefs (checkbox cards), languages (horizontal chips)
- **Screen B:** 5 question blocks — region (2-col radio), migration (compact list), warehouse (chips), tools (searchable), volume (horizontal radio)
- **Screen C:** 2x3 grid of visual goal cards — each has emoji icon (28px), title (14px bold), description (13px grey), checkbox in top-right corner. Selected state: blue border + blue-50 background

### Screens 5-9: Install Experience
- **Shared:** 5-dot step indicator at top with labels underneath, "Skip to app" in header
- **Step 1 (SDK):** Tab bar for npm/JS snippet, code blocks, write key/data plane display, event monitor with spinner
- **Step 2 (Configure):** Toggle rows for autoTrack features, environment radio cards
- **Step 3 (Warehouse):** Chip picker (pre-selected from survey), config form, connection test button, "invite a teammate" callout box
- **Step 4 (Plan):** 3-column plan cards. Growth card has "MOST POPULAR" badge floating above. Selected card has blue border + blue-50 bg. Price centered, features as bullet list
- **Step 5 (Invite):** Multi-row form (email + role selector per row), "+ Add another" link, personal message textarea, email preview panel

### Screen 10: In-App Quick Start
- **Layout:** 480px drawer panel on left of app, main content visible behind
- **Header:** Sticky, "Getting started" with lightning bolt + "2/11 complete" counter + close X
- **Sections:** DATA COLLECTION (with Data Source / Data Destination subheaders), DATA GOVERNANCE, DATA ACTIVATION, YOUR PLAN, YOUR TEAM
- **Section headers:** Uppercase, 12px, 600 weight, grey-500, counter on right
- **Subsection headers:** 11px, 500 weight, grey-400, dashed bottom border
- **Checklist items:** 22px circle icon + title + arrow. States:
  - Complete: green-500 filled circle with white checkmark
  - Current: blue-500 filled circle with step number
  - Pending: grey-200 border circle, empty
  - Locked: grey-200 border circle with lock icon
  - Greyed (Enterprise): grey-200 dashed border, italic text, ENTERPRISE badge
- **Expanded step:** Grey-50 background card with description, code snippet, CTA buttons
- **Tag Manager banner:** Gradient background (blue-50 to purple-50), title + description + CTA
- **Specialist banner:** Blue-50 background, "Talk to a Product Specialist" link
- **Plan step expanded:** Upgrade copy + "View plans" primary CTA + "Remind me later" text link
- **Team step expanded:** Copy + "Invite teammates" primary CTA + "It's just me!" text link

---

## Typography Quick Reference

| Element | Size | Weight | Color |
|---------|------|--------|-------|
| Page title (auth) | 24px | 600 | grey-900 |
| Page subtitle | 14px | 400 | grey-500 |
| Section header (Quick Start) | 12px | 600 | grey-500 |
| Step title (Install) | 20px | 600 | grey-900 |
| Checklist item title | 13px | 500 | grey-900 (locked: grey-300) |
| Body text | 14px | 400 | grey-600 |
| Label | 13px | 500 | grey-800 |
| Code | 13px | 400 | #E5E7EB on grey-900 |
| Badge | 11px | 600 | varies |
| Help link | 13px | 400 | grey-500, hover blue-500 |

## Color Quick Reference

| Token | Hex | Usage |
|-------|-----|-------|
| Primary | #105ED5 | CTAs, active states, links, selected borders |
| Primary bg | #EBF3FD | Selected card backgrounds, callout backgrounds |
| Grey-50 | #F5F6F8 | Page backgrounds, hover states, expanded step bg |
| Grey-100 | #D8DEE4 | Borders, dividers, progress bar track |
| Grey-300 | #99A5B8 | Placeholder text, disabled states |
| Grey-500 | #6C7688 | Section headers, secondary text |
| Grey-900 | #21252C | Primary text, headings |
| Green-500 | #02BB7F | Success/complete icons |
| Enterprise purple | #7C3AED bg #F3E8FF | Enterprise badges |

---

## Assets Needed from Design

1. RudderStack logo SVG (already in app, extract from `src/`)
2. Goal card icons — can use emoji for MVP or design custom icons
3. Warehouse logos (Snowflake, BigQuery, Redshift, Databricks, Postgres) — may exist in integrations catalog
4. Plan feature comparison content (confirm with billing/pricing)
5. Email invite preview template styling
