<div align="center">

<img src="https://raw.githubusercontent.com/bilnxny/phoenix-infotech/main/.github/logo.svg" width="72" alt="Phoenix Infotech" />

# Phoenix Infotech

**Ethical hacking · Penetration testing · Red team operations**

Based in Ernakulam, Kerala — serving India, the UAE and Singapore.

[![Live Site](https://img.shields.io/badge/live-phoenix--infotech-FF5C1A?style=flat-square)](https://bilnxny.github.io/phoenix-infotech/)
[![License](https://img.shields.io/badge/license-Proprietary-232329?style=flat-square)](#license)
[![Made with](https://img.shields.io/badge/built%20with-HTML%20%7C%20CSS%20%7C%20JS-FF5C1A?style=flat-square)](#tech-stack)
[![Animations](https://img.shields.io/badge/animations-enabled-22C55E?style=flat-square)](#-animation-system)

</div>

---

## Table of contents

- [Overview](#overview)
- [Live demo](#live-demo)
- [Tech stack](#tech-stack)
- [Animation system](#-animation-system)
- [Project structure](#project-structure)
- [Local development](#local-development)
- [Deployment](#deployment)
- [SEO & structured data](#-seo--structured-data)
- [Accessibility](#-accessibility)
- [Performance](#-performance)
- [Customisation guide](#customisation-guide)
- [Legal notice](#legal-notice)
- [License](#license)

---

## Overview

Phoenix Infotech is a single-page marketing site for an offensive-security firm. It is:

- **Zero-build** — plain HTML, CSS and vanilla JavaScript. No bundler, no framework, no `npm install`.
- **Mobile-first** — fully responsive from 320px up.
- **Animated** — a cohesive motion system built on native CSS transitions, `IntersectionObserver` and `requestAnimationFrame`.
- **SEO-ready** — Schema.org structured data, Open Graph, geo-targeted meta for Kerala and India.
- **Accessible** — keyboard navigable, semantic HTML, honours `prefers-reduced-motion`.

The entire site ships as a **single `index.html`** file. Nothing needs compiling.

---

## Live demo

🌐 **https://bilnxny.github.io/phoenix-infotech/**

---

## Tech stack

| Layer | Choice | Why |
|---|---|---|
| Markup | Semantic HTML5 | Fast, accessible, indexable |
| Styling | Vanilla CSS with custom properties | No build step, instant theming |
| Scripting | Vanilla ES2019+ JavaScript | No dependencies, tiny footprint |
| Fonts | Inter + JetBrains Mono (Google Fonts) | Clean UI + technical accents |
| Icons | Font Awesome 6 (CDN) | Consistent icon language |
| Animation | CSS transitions + `IntersectionObserver` + `requestAnimationFrame` | GPU-accelerated, jank-free |
| Hosting | GitHub Pages | Free, HTTPS, auto-deploy on push |

**No dependencies. No node_modules. No build pipeline.**

---

## ✨ Animation system

Every animation is native — no GSAP, no Framer Motion, no scroll libraries. The whole motion layer adds under 15 KB of unminified JS.

### 1. Page load

| Element | Animation | Implementation |
|---|---|---|
| Scroll progress bar | Accent-gradient fill tracking scroll % | Fixed 2px bar, width updated on `scroll` |
| Preloader | SVG stroke-draw of the phoenix mark + rotating ring + bar fill | `stroke-dasharray` + `@keyframes spin` |
| Preloader exit | Fade + visibility transition | `.done` class, `opacity` + `visibility` |

### 2. Hero section

| Effect | Description |
|---|---|
| **Drifting orbs** | Three blurred radial-gradient circles drifting on 18s/22s/26s loops |
| **Animated grid** | 64px accent-tinted grid slowly scrolling diagonally, masked with a radial fade |
| **Mouse-follow glow** | A soft accent halo tracking the cursor with lerped interpolation |
| **Orb parallax** | Orbs shift subtly based on mouse position (depth-weighted, disabled on touch) |
| **Word-by-word title reveal** | Each word fades in with a `rotateX(-40deg)` → `0deg` transform, staggered 55ms apart |
| **Live badge ping** | Green status dot pulses with an expanding ring (`@keyframes ping`) |

### 3. Scroll reveals

Four reveal variants, all triggered by a single `IntersectionObserver`:

```css
.rv          → fade + slide up
.rv-left     → fade + slide from left
.rv-right    → fade + slide from right
.rv-scale    → fade + scale from 94%
