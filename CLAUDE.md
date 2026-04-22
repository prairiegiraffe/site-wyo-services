# WYO Services — Professional Site Build

## Quick Start
1. Read this file completely before building
2. The shell CSS is at `css/styles.css` — it defines the full design system
3. Section templates are in `sections/` — use them as starting patterns
4. Build each page as a standalone `.html` file in the root directory
5. Run `npx serve .` to preview locally
6. When done, `git add . && git commit -m "Build site" && git push` to deploy

## Business Facts (DO NOT INVENT — write around missing info)

| Field | Value |
|-------|-------|
| **Business Name** | WYO Services |
| **Industry** | Oil and Gas Multi-service site development and reclamation |
| **Type** | Excavation / Earthwork |
| **Tagline** | One Contractor. Complete Solutions. |
| **Years in Business** | 14 years |
| **Phone** | (307)696 - 51616 |
| **Email** | shai@kutthru.com |
| **Address** | 410 Limestone Ave, Gillette, WY |
| **Primary Location** | Gillette & Douglas |
| **Personality** | Rugged & Industrial |
| **Target Audience** | Project Managers, Field Managers, Operation Supervisors, Procurement |
| **Inspiration Sites** | https://h-2e.com/about/ , https://prcwy.com/ |

### About
WYO Services is a Wyoming-based oilfield and land services contractor providing multi-service site development and reclamation throughout the Powder River Basin.

Founded in 2012 by Kyle and Jane Materi, the company started as a small fencing operation before rapidly expanding as client needs grew beyond a single service. Within a few years, WYO Services evolved into a full-service contractor supporting larger oil & gas projects.

Operating primarily out of Gillette and Douglas, WY the company has grown through strong field experience, ranching roots, and a reputation built almost entirely through word-of-mouth relationships.

### Services (7 total)
1. Pad construction & dirt work
2. Reclamation & seeding
3. Fencing & containment
4. Cattle Guards: Fabrication & Installation
5. Site infrastructure support
6. Turnkey site development capabilities
7. Emerging pipeline work

### Service Areas
- Gillette & Douglas (primary)
- WY

## Design System

**Shell**: `industrial_contractor`
**Fonts**: Barlow Condensed (headings) + Barlow (body)
**Brand Color**: Not set — shell uses a default

The shell CSS (`css/styles.css`) defines all design tokens as CSS custom properties:
```
--color-primary: #1f4d2b;
  --color-primary-dark: #102917;
  --color-primary-light: #60bf78;
  --color-primary-tint: rgba(31, 77, 43, 0.08);
  --color-primary-tint-strong: rgba(31, 77, 43, 0.18);
  --color-accent: #247561;
  --color-dark: #0f172a;
  --color-muted: #4b5563;
  --color-border: #e5e7eb;
  --color-surface: #f9fafb;
  --color-surface-alt: #f3f4f6;
  --color-on-primary: #ffffff;
  --font-heading: "Barlow Condensed", system-ui, -apple-system, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
  --font-body: "Barlow", system-ui, -apple-system, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
  --container: 1280px;
  --container-narrow: 860px;
  --radius-sm: 4px;
  --radius: 8px;
  --radius-lg: 12px;
  --radius-md: 8px;
  --shadow-xs: 0 1px 2px rgba(0, 0, 0, 0.06);
  --shadow-sm: 0 2px 8px rgba(0, 0, 0, 0.08);
  --shadow-md: 0 8px 24px rgba(0, 0, 0, 0.1);
  --shadow-lg: 0 20px 40px rgba(0, 0, 0, 0.14);
  --shadow-primary: 0 10px 40px -10px var(--color-primary-tint-strong);
  --transition: 0.25s cubic-bezier(0.2, 0.8, 0.2, 1);
```

### Key CSS Classes
- `.container` — max-width centered container
- `.container-narrow` — narrower container for text-heavy sections
- `.eyebrow` — small uppercase label with accent bar (used above section headings)
- `.btn`, `.btn--outline`, `.btn--inverse`, `.btn--ghost` — button variants
- `.hero` — full-bleed hero with `.hero__bg` background image
- `.stats` — stat strip with `.stat`, `.stat__value`, `.stat__label`
- `.service-grid` + `.service-card` — card grid for services
- `.feature-row` + `.feature-row.reverse` — alternating image/text rows
- `.diff-grid` + `.diff-card` — icon cards for differentiators/values
- `.process-list` — numbered timeline
- `.faq` — accordion using `<details>`/`<summary>`
- `.project-grid` + `.project-card` — photo cards with metadata
- `.testimonial` — two-column quote + photo
- `.contact-grid` + `.contact-form` — form + contact info card
- `.cta-section` — dark call-to-action banner
- `.site-header` — sticky dark header
- `.site-footer` — dark footer with grid columns
- `.page-section`, `.page-section.alt`, `.page-section.dark` — section wrappers

## Pages to Build

Build these as standalone HTML files. Each file should be a complete document
(`<!DOCTYPE html>` through `</html>`) that links to `css/styles.css`.

1. **index.html** (Home) — Hero, stats strip, services overview, featured capabilities with photos, about teaser, service areas, CTA
2. **about.html** — Company story, team/leadership (if info available), values/differentiators, CTA
3. **services.html** — All services as card grid with icons
4. **services/[slug].html** — One per service: hero, overview, what-we-do, process timeline, FAQ, CTA
5. **contact.html** — Contact form + info card + map, company field for B2B
6. **service-areas.html** — Area cards grid (if multiple areas)

### Page Structure Rules
- Every `<section>` needs `data-block-id="page:section-name"` (for the platform editor)
- Editable text slots get `data-content="slot-name"` attributes
- Contact form needs `data-devtools-form` and `data-form-type="contact"`
- Header wraps in `data-devtools-partial="header"`
- Footer wraps in `data-devtools-partial="footer"`
- Hero images: `loading="eager" fetchpriority="high"`
- All other images: `loading="lazy"`
- H1 → H2 → H3 hierarchy, no skips
- Meta description on every page, ≤ 155 chars
- Include LocalBusiness schema JSON-LD on home page

## Section Templates

The `sections/` directory contains HTML section templates you can reference.
These are from the oatmeal-olive-mona and Studio template libraries — adapt
the structure and layout patterns but use the shell's CSS classes, not Tailwind.

Available sections:
- `stats-four-columns.html` — grid of stat cards
- `features-alternating.html` — alternating image/text feature rows
- `features-three-column.html` — three-column feature cards
- `testimonial-large-photo.html` — quote + large photo side by side
- `team-grid.html` — team member photo grid
- `faqs-accordion.html` — two-column FAQ with accordion
- `hero-with-photo.html` — hero with side photo
- `cta-simple.html` — centered call-to-action

## Copy Writing Rules

1. **Never invent facts.** If a specific fact is missing (founding year, certifications, team size), rewrite the sentence so it doesn't need that fact. Don't use placeholder markers.
2. **No slop.** Avoid: "in today's world", "look no further", "state-of-the-art", "one-stop shop", "world-class", "industry-leading", "leverage", "synergies", "cutting-edge", "seamless", "pristine", "unlock the potential", "game-changer", "delve into", "tapestry of", "plethora of", "myriad of".
3. **No self-congratulation.** Skip "We're proud to...", "We take pride in...", "Our commitment to...".
4. **Be direct.** Write what the business does, not what it "may help" with.
5. **Use the business name** at least once per page, not "our company".
6. **Mention specific services and areas by name** — pull from the facts above.
7. **Match the personality** — Rugged & Industrial.
8. **B2B tone** — speak to project managers, procurement, field supervisors. Not homeowners.

## Images

Use placeholder images for now. The client will provide real project photos later.
For placeholders, use Unsplash source URLs:
```
https://source.unsplash.com/1600x900/?Oil%20and%20Gas%20Multi-service%20site%20development%20and%20reclamation,work
https://source.unsplash.com/800x1000/?Oil%20and%20Gas%20Multi-service%20site%20development%20and%20reclamation,team
```

## Deployment

- **Repo**: https://github.com/prairiegiraffe/site-wyo-services
- **Live URL**: https://site-wyo-services.pages.dev
- Push to `main` branch → auto-deploys via Cloudflare Pages
- No build step — CF Pages serves static files directly

## Platform Integration

This site is tracked in the devtools platform as a `captured_sites` row.
After building, the owner can:
- Edit pages visually in the platform editor
- Run SEO audits
- Generate fulfillment plans
- Share with clients for review
