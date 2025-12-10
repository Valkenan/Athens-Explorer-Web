# Athens Explorer Web

**A modern, accessible tourism landing page for Athens, Greece, utilizing next-generation CSS color spaces.**

![HTML5](https://img.shields.io/badge/HTML5-Semantic-orange.svg) ![CSS3](https://img.shields.io/badge/CSS3-Modern-blue.svg) ![Status](https://img.shields.io/badge/Status-Responsive-green.svg)

## 📖 Overview

Athens Explorer is a responsive, high-performance landing page designed to showcase the cultural and gastronomic highlights of Athens. Unlike traditional static sites, this project leverages **Modern CSS (Level 4)** features, including the `oklch()` color space for perceptually uniform gradients and high-fidelity color management.

## 🎨 UI/UX Architecture

The design system is built on a "Mobile-First" philosophy (adapted for desktop) with a focus on visual hierarchy and readability.

* **Color System:** Migrated away from sRGB/Hex codes to **OKLCH**. This ensures that color lightness ($L$) and chroma ($C$) remain consistent across different hues, improving readability and accessibility.
* **Typography:** Uses *Manrope*, a modern sans-serif font, ensuring legibility on high-DPI displays.
* **Layout Engine:** Utilizes CSS Flexbox for a fluid, adaptive layout that maintains structure across different viewport sizes.

## ⚡ Technical Decisions

### 1. Perceptual Color Space (`oklch`)
I chose `oklch` over standard Hex/RGB because it decouples **Lightness** from **Chroma** (intensity).
* *Code:* `color: oklch(0.76 0.05 264);`
* *Benefit:* This allows for generating dynamic hover states and gradients (like the navbar background) without accidental shifts in perceived brightness, which is a common issue with HSL.

### 2. Semantic HTML5
The markup strictly follows semantic standards (`<header>`, `<main>`, `<section>`, `<nav>`) rather than using generic `<div>` wrappers.
* **SEO:** Helps search engines understand the priority of content.
* **Accessibility:** Allows screen readers to navigate the "Landmark" regions of the page effectively.

### 3. Performance Optimization
* **Lazy Loading:** All images utilize `loading="lazy"` to defer off-screen image decoding. This significantly improves the **Largest Contentful Paint (LCP)** metric on initial load.
* **Compositor-Only Animations:** The navbar underline animation targets the `width` and `opacity` properties to minimize main-thread layout thrashing.

## 🚀 Features

* **Sticky Navigation:** Implemented with pure CSS (`position: sticky`), removing the need for JavaScript event listeners.
* **Interactive Cards:** Hover states with `transform: scale()` and opacity transitions create a tactile feel for the user.
* **Smooth Scrolling:** Native CSS `scroll-behavior: smooth` provides a polished navigation experience between sections.

## 💻 Setup & Usage

1.  Clone the repository.
2.  Open `index.html` in any modern browser.
    * *Note:* No build step (npm/webpack) is required, adhering to the "Vanilla Web" philosophy.
