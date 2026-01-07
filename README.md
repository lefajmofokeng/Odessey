# Odessey

## Project Overview

Odessey is a high-fidelity front-end interface designed to demonstrate the power of strict grid systems and typographic hierarchy in modern web development. This project replicates a premium editorial layout often found in high-end architectural and educational portfolios.

The core objective of Odessey is to present diverse content types—textual testimonials, ambient video media, and statistical data—within a unified, geometrically balanced framework. It prioritizes readability, visual weight distribution, and responsive adaptability without relying on heavy external frameworks or JavaScript libraries.

<img width="1920" height="1502" alt="odessey" src="https://github.com/user-attachments/assets/80b6a035-0372-463e-bb95-c98ea8f04698" />

## Live Deployment

[Preview Live Demo](https://lefajmofokeng.github.io/Odessey)

## Design Philosophy

The visual language of Odessey is grounded in two primary design principles:

1. **Strict Grid Symmetry:** Unlike masonry layouts that allow for variable heights, Odessey utilizes a strict, equal-height card system. This creates a sense of stability and order, often associated with institutional trust and professional precision.
2. **Typographic Contrast:** The design juxtaposes the editorial elegance of *Libre Caslon Condensed* (a classic serif) with the modern utility of *42dot Sans* (a clean geometric sans-serif). This combination creates a sophisticated interplay between the "voice" of the brand (headers/quotes) and the "utility" of the UI (buttons/body text).

## Technical Architecture

This project serves as an educational resource for implementing resilient CSS architectures. Below are the key technical strategies employed.

### 1. Namespaced CSS Architecture

To ensure this component can be integrated into any existing codebase (React, Vue, WordPress, or legacy HTML) without style leakage, the CSS utilizes a strict BEM-like namespacing strategy.

Every class is prefixed with `pw2-` (e.g., `.pw2-card`, `.pw2-btn-dark`). This acts as a manual styling scope, preventing generic class names like `.card` or `.container` from conflicting with other stylesheets in a larger application.

### 2. CSS Grid for Structural Equality

The three-column layout is achieved not through Flexbox, but through CSS Grid. This ensures mathematical equality in width while the fixed height property enforces vertical alignment.

```css
.pw2-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr); /* Creates three equal columns */
    gap: 24px;
    width: 100%;
}

.pw2-card {
    height: var(--pw2-card-height); /* Enforces strict height across all children */
}

```

### 3. CSS Custom Properties (Variables)

The project utilizes CSS variables for semantic tokenization. This allows for centralized management of the design system. Changing a single hex code in the `:root` alters the theme across the entire component.

```css
:root {
    --pw2-font-serif: 'Libre Caslon Condensed', serif;
    --pw2-color-dark: #1A1A1A;
    --pw2-color-bg: #FFFCF8;
    --pw2-card-height: 580px;
}

```

### 4. Ambient Video Integration

The middle card features a video element configured to function as a dynamic background. The attributes `autoplay`, `loop`, `muted`, and `playsinline` are essential for ensuring the video plays automatically on modern browsers without user interaction, particularly on mobile devices where autoplay is often blocked for unmuted media.

## Installation and Usage

### Prerequisites

This project is built with vanilla HTML5 and CSS3. No package managers (npm/yarn) or build steps are required.

### deployment

1. Clone the repository:
```bash
git clone https://github.com/lefajmofokeng/Odessey.git

```


2. Navigate to the project directory.
3. Open `index.html` in your preferred browser.

### Integration Guide

To use this component within another project:

1. Copy the CSS within the `<style>` tags.
2. Paste it into your project's stylesheet.
3. Copy the HTML structure inside `.pw2-container`.
4. Ensure the Google Fonts link in the `<head>` is included to render the typography correctly.

## Typographic System

The typography is a critical component of the Odessey identity. It is imported via the Google Fonts API.

* **Primary Display:** *Libre Caslon Condensed* (Weights: 400 Regular, 400 Italic). Used for headlines, large quotes, and statistical numbers to evoke an editorial feel.
* **Secondary UI:** *42dot Sans* (Weights: 300, 400, 500, 600). Used for body text, button labels, and metadata for maximum legibility at small sizes.

## Responsiveness

The layout is fully responsive and adapts to three primary breakpoints:

* **Desktop (> 1024px):** Displays the strict 3-column grid with full height (580px).
* **Tablet (< 1024px):** Maintains the grid structure but adjusts font sizes and padding to prevent overflow.
* **Mobile (< 768px):** The grid collapses into a single column (`grid-template-columns: 1fr`). Card heights are reduced to 450px to fit better within vertical viewports, and interaction targets (buttons) are sized for touch accessibility.

## License

This project is open-source and available under the MIT License. You are free to modify and use this code for personal or commercial projects.
