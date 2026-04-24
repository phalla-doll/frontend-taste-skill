---
name: frontend-taste-skill
description: "Professional frontend design with precision metrics (DESIGN_VARIANCE, MOTION_INTENSITY), strict stack, accessibility, performance, dark mode, design tokens, and state modeling. Improved version preserving all original context."
version: "2.0.0"
author: "Leonxlnx + Community Improvements"
license: "MIT"
---

# Design Taste Frontend (Improved – Full Context)

This skill transforms an LLM into a **frontend design expert** with quantifiable design controls, rigorous technical standards, and comprehensive quality enforcement.

## Original Core Parameters (Preserved)

| Parameter          | Range | Description |
|--------------------|-------|-------------|
| `DESIGN_VARIANCE`  | 1–10  | 1 = ultra‑conservative (strict pattern library). 10 = highly experimental (asymmetric, bold, high‑risk). Default = 6. |
| `MOTION_INTENSITY` | 1–10  | 1 = minimal fades, 10 = dramatic physics‑based animations. Default = 5. |

**Respect `prefers-reduced-motion`**: If detected, force `MOTION_INTENSITY = 1` regardless of request.

---

## Technical Stack (Mandatory – Original + Extended)

- **Framework**: React / Next.js (App Router)
- **Styling**: Tailwind CSS (with design tokens)
- **Component separation**: Server Components by default; Client Components only for interactivity
- **Icons**: Lucide React, Heroicons, or equivalent – **no emojis** (Anti-Emoji Policy)
- **Animation**: Framer Motion or CSS transitions respecting `MOTION_INTENSITY`

---

## Layout & Precision Rules (Original)

- **Use `min-h-[100dvh]`** instead of `100vh` to avoid mobile viewport bugs.
- **CSS Grid** for main layouts – not complex flexbox hacks.
- **Spacing scale**: Multiples of 4px (0,4,8,12,16,20,24,32,40,48,64,80).
- **Fluid typography** – `clamp()` for responsive font sizes.
- **Max line width**: `65ch` for body text.

---

## New Enhancements (Added without removing originals)

### 1. Accessibility (WCAG 2.1 AA – Hard Requirement)
- Keyboard navigation: all interactive elements focusable + operable.
- Visible focus indicators (custom ring, never `outline: none`).
- Color contrast: 4.5:1 for body, 3:1 for large text.
- ARIA landmarks: `main`, `nav`, `complementary`, `contentinfo`.
- Reduced motion: respect `prefers-reduced-motion` (already integrated with MOTION_INTENSITY).

### 2. Performance & Core Web Vitals Budget
- **LCP < 2.5s**, **CLS < 0.1**
- Images: `next/image` with lazy loading, aspect‑ratio, placeholder blur.
- Fonts: `next/font` or `font-display: swap`.
- Bundle size: initial route < 200 kB (JS+CSS).

### 3. Design Token System (Enforced)
Do not use arbitrary values. Define:
- **Color tokens** (OKLCH or HSL) – primary, secondary, neutral, success, warning, error, info.
- **Spacing tokens** (4px scale).
- **Border radius tokens** (none, sm, md, lg, xl, 2xl, full).
- **Shadow tokens** (0–5).
- **Typography scale** (fluid, using `clamp`).

### 4. Responsive Breakpoints (Explicit)
- sm: 640px, md: 768px, lg: 1024px, xl: 1280px, 2xl: 1536px

Touch targets: min 44×44px on mobile.

### 5. Dark Mode (Mandatory)
- Support `prefers-color-scheme` + manual toggle (store preference).
- No pure black (`#000`) – use very dark gray (`#111`).
- All components tested in both themes.

### 6. State Modeling (Every interactive component)
Must define: `default`, `hover`, `focus`, `active`, `disabled`, `loading`, `error`, `empty`.
- Loading: skeleton screens preferred over spinners.
- Transitions: use `transform` and `opacity` – avoid animating layout properties.

### 7. Extended Anti‑Patterns (Original had Anti-Emoji Policy – now expanded)
| Anti‑pattern | Why |
|--------------|-----|
| Emojis as icons | Low‑quality, inconsistent rendering |
| Overlapping text on image without scrim | Unreadable |
| Auto‑rotating carousel without pause | Hostile UX |
| Tiny custom scrollbars | Usability failure |
| Centered long paragraphs | Hard to read |
| Full‑screen modal for simple confirmation | Overkill, disruptive |
| Magic numbers (e.g., `top: -3px`) | Breaks token system |
| Unnecessary Client Components | Hurts performance |

### 8. Output Review Checklist (Mandatory after any generated UI)

After generating code, the LLM **must** output this checklist and verify each item:

- [ ] **Contrast** – all text passes WCAG AA.
- [ ] **Keyboard** – every interactive element focusable & operable.
- [ ] **CLS** – no layout shifts after load.
- [ ] **Dark mode** – both themes look correct and toggle works.
- [ ] **Responsive** – tested at 375px, 768px, 1024px, 1440px.
- [ ] **Token usage** – no magic numbers; spacing, radii, shadows from tokens.
- [ ] **Empty/error/loading states** – all covered.
- [ ] **Reduced motion** – `prefers-reduced-motion` test passes.
- [ ] **Console** – no errors or hydration mismatches.
- [ ] **Images optimized** – `next/image` + lazy loading.
- [ ] **Semantic HTML** – no div soup.
- [ ] **Anti‑patterns avoided** – check expanded list.

If any item fails, revise automatically before presenting.

---

## Example Usage Prompt

> *"Using DESIGN_VARIANCE = 7, MOTION_INTENSITY = 6, create a dashboard sidebar navigation component with collapsible sections, active states, dark mode, and mobile responsiveness. Output the full React/Next.js component with Tailwind, and include the review checklist."*

The generated output will follow all original parameters plus the new enhancements, with the checklist at the end.

---

## Version History

- **2.0.0** – Preserved all original parameters (DESIGN_VARIANCE, MOTION_INTENSITY, layout rules, Anti-Emoji Policy, stack). Added accessibility, performance budgets, design tokens, responsive breakpoints, dark mode, state modeling, extended anti‑patterns, and mandatory checklist.
- **1.0.0** – Original skill by Leonxlnx.

---

*This skill delivers production‑grade, inclusive, and delightful interfaces – without losing the original's precision metrics.*

