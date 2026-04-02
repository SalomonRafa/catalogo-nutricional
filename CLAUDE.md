# CLAUDE.md — AI Assistant Guide for catalogo-nutricional

## Project Overview

This is a **static HTML portfolio/catalog website** for Rafael Salomon, a Brazilian clinical and sports nutritionist. It showcases services, pricing plans, FAQs, and contact information, with no backend or build infrastructure.

**Live URL**: Hosted on GitHub Pages via the `main` branch.

---

## Repository Structure

```
catalogo-nutricional/
├── CLAUDE.md                                    # This file
├── README.md                                    # Minimal project description
├── index.html                                   # Entry point — redirects to main catalog
├── Catálogo - Rafael Salomon - 2026.html        # Main catalog (current, ~865 lines)
└── Catalogo_Salomon.html                        # Legacy catalog (older version, archived)
```

**The main file to edit is**: `Catálogo - Rafael Salomon - 2026.html`

`index.html` is a thin redirect wrapper — only update it if the main catalog filename changes.

---

## Technology Stack

- **HTML5** with embedded CSS3 and minimal vanilla JavaScript
- **No build tools, no package managers, no frameworks**
- **Font Awesome 6.4.0** (icons via CDN — no local install needed)
- **External integrations** (hardcoded URLs):
  - WhatsApp Business: `https://wa.me/5561995662828`
  - InfinitePay payment gateway: `https://loja.infinitepay.io/rafasalomon`

---

## Development Workflow

Since there is no build process, development is direct file editing:

1. Edit `Catálogo - Rafael Salomon - 2026.html` (or the relevant HTML file)
2. Open in a browser to preview changes locally
3. Commit and push to `main` — GitHub Pages deploys automatically

**No commands to run.** No `npm install`, no `build`, no `test`.

```bash
# The only workflow:
git add "Catálogo - Rafael Salomon - 2026.html"
git commit -m "descriptive message"
git push origin main
```

---

## Page Sections (Main Catalog)

The main catalog contains these sections in order:

| Section | HTML anchor | Description |
|---|---|---|
| Hero | `id="topo"` | Profile photo (base64), credentials, CTA buttons |
| Methodology | *(no anchor)* | 7-step cycle diagram (pure CSS) |
| Plans | *(no anchor)* | 3 pricing tiers with service details |
| Procedures | *(no anchor)* | Policies: scheduling, delivery SLAs, support terms |
| FAQ | *(no anchor)* | 4 collapsible categories, JS-toggled |
| Final CTA | *(no anchor)* | Conversion call-to-action |
| Footer | *(no anchor)* | Contact, payment link, LGPD notice |
| Floating buttons | *(fixed position)* | WhatsApp + payment sticky sidebar |

---

## CSS Conventions

All CSS is embedded in a `<style>` block inside each HTML file. There are no external `.css` files.

### CSS Custom Properties (Design Tokens)

```css
:root {
  --p:      #50C7C0;  /* Primary teal */
  --s:      #2DA6A6;  /* Secondary darker teal */
  --bg:     #0A0E12;  /* Page background (dark) */
  --bgm:    #151B23;  /* Medium background */
  --bgc:    #1A2332;  /* Card background */
  --txt:    #E8EAED;  /* Primary text */
  --txt2:   #B8BDC3;  /* Secondary/muted text */
  --border: #2A3647;  /* Border color */
  --verde:  #4ADE80;  /* Green accent (checkmarks, positives) */
  --amarelo:#FFC107;  /* Yellow accent (warnings, highlights) */
}
```

Always use these variables instead of hardcoded color values.

### Typography

Fluid typography via `clamp()` — do not use fixed `px` font sizes for headings:
```css
font-size: clamp(1.4rem, 4vw, 2.2rem);
```

### Naming Convention

BEM-like class names: `section-element` or `section-element-modifier`
Examples: `faq-item`, `hero-card-top`, `plan-feature`, `floating-btn`

---

## JavaScript Conventions

JavaScript is minimal and embedded at the bottom of each HTML file (before `</body>`). The only current functionality is FAQ accordion toggling:

```javascript
document.querySelectorAll('.faq-q').forEach(q => {
  q.addEventListener('click', () => {
    q.parentElement.classList.toggle('active');
  });
});
```

**Conventions:**
- Use `querySelectorAll` + `forEach` for DOM queries
- Use `classList.toggle/add/remove` for state changes
- No jQuery, no external JS libraries
- Keep JS minimal — prefer CSS-only solutions where possible

---

## Content & Contact Details

All contact details are hardcoded directly in the HTML:

| Field | Value |
|---|---|
| Professional | Rafael Salomon |
| Registration | CRN-1/16718 |
| WhatsApp | +55 61 99566-2828 |
| Email | rafaelsalomon@gmail.com |
| Instagram | @rafaelsalomon.nutri |
| Payment portal | https://loja.infinitepay.io/rafasalomon |

**Language**: All content is in Brazilian Portuguese.

---

## Pricing Plans (current)

| Plan | Price | Duration |
|---|---|---|
| Plano Inicial | R$ 540 | 3 months |
| Plano Intermediário | R$ 1.200 | 6 months |
| Plano Integral | R$ 2.880 | 12 months |

When updating prices or plan names, also update the corresponding InfinitePay links.

---

## Key Conventions for AI Assistants

1. **Edit the right file**: Always work on `Catálogo - Rafael Salomon - 2026.html` unless specifically asked about another file.
2. **Preserve design tokens**: Use CSS variables (`var(--p)`, `var(--txt)`, etc.) — never hardcode colors.
3. **No build steps**: Do not suggest `npm install` or any build commands — there are none.
4. **Language**: All user-visible content must remain in Brazilian Portuguese.
5. **Minimal JS**: Avoid adding JavaScript unless absolutely necessary. Prefer CSS-only interactions.
6. **No new files**: Add new sections within the existing HTML file rather than creating separate pages.
7. **Images are base64**: The profile photo is embedded as a base64 data URI — do not reference external image URLs for the profile photo.
8. **Compliance**: The LGPD (Lei Geral de Proteção de Dados) notice in the footer must be preserved.
9. **Accessibility**: Maintain `rel="noopener noreferrer"` on all `target="_blank"` links.
10. **Branch**: Develop on `claude/add-claude-documentation-9MuSd`; production deploys from `main`.

---

## Git Branch Strategy

| Branch | Purpose |
|---|---|
| `main` | Production — auto-deploys to GitHub Pages |
| `claude/add-claude-documentation-9MuSd` | Active AI development branch |

Create feature branches off `main` for significant changes; use the Claude development branch for AI-assisted work.
