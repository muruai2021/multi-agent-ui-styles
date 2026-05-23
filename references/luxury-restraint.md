---
name: luxury-restraint-style
description: "奢侈品风格 - 象牙金克制优雅"
type: ui-style
---

# Luxury Restraint Style Design System

## Overview

奢侈品风格是「克制优雅」的极致——它代表了高端品牌的设计哲学：少即是多，每个元素都必须有存在的理由。象牙白背景、金色点缀、衬线字体，构建出排他性的视觉体验。

**Brands**: Louis Vuitton, CARTIER, HERMES, GUCCI, DIOR, Bottega Veneta

**Mood**: 奢华、高端、克制、优雅、排他、精致、传统、现代简约

---

## Color Palette

### Ivory & Gold (Primary)

```css
/* Background Scale - Warm ivory */
--bg-primary: #FFFEF9;
--bg-secondary: #FDFBF7;
--bg-tertiary: #F8F5EE;
--bg-warm: #F5F1E8;
--bg-cream: #FAF7F2;
--bg-paper: #FDFCF8;

/* Text - Warm blacks */
--text-primary: #1A1A18;
--text-secondary: #4A4A46;
--text-tertiary: #7A7A74;
--text-muted: #A8A8A2;
--text-inverse: #FFFEF9;

/* Ivory border */
--border-subtle: rgba(26, 26, 24, 0.06);
--border-default: rgba(26, 26, 24, 0.1);
--border-strong: rgba(26, 26, 24, 0.2);

/* Gold - Signature accent */
--gold-primary: #C4A052;
--gold-hover: #D4B066;
--gold-light: #E8D5A8;
--gold-dark: #A68B3D;
--gold-subtle: rgba(196, 160, 82, 0.12);
--gold-muted: rgba(196, 160, 82, 0.3);

/* Accent colors - Deep, rich */
--accent-burgundy: #722F37;
--accent-navy: #1B2838;
--accent-forest: #2C3E2D;
--accent-camel: #C19A6B;

/* Semantic Colors - Muted luxury */
--success: #4A7C59;
--warning: #B8860B;
--error: #8B3A3A;
--info: #4A5568;
```

### Dark Mode (Limited, for special sections)

```css
--bg-primary-dark: #1A1A18;
--bg-secondary-dark: #242420;
--text-primary-dark: #FDFBF7;
--text-secondary-dark: #A8A8A2;
--gold-primary-dark: #D4B066;
```

### Tailwind Config

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        ivory: {
          primary: '#FFFEF9',
          secondary: '#FDFBF7',
          tertiary: '#F8F5EE',
        },
        gold: {
          DEFAULT: '#C4A052',
          light: '#E8D5A8',
          dark: '#A68B3D',
        },
        luxury: {
          burgundy: '#722F37',
          navy: '#1B2838',
          forest: '#2C3E2D',
          camel: '#C19A6B',
        },
        text: {
          primary: '#1A1A18',
          secondary: '#4A4A46',
        },
      },
      fontFamily: {
        serif: ['Playfair Display', 'Cormorant Garamond', 'Georgia', 'serif'],
        sans: ['Inter', '-apple-system', 'sans-serif'],
        display: ['Playfair Display', 'Cormorant', 'serif'],
      },
    },
  },
}
```

---

## Typography

**Font Stack**:
- **Display/Headings**: `Playfair Display`, `Cormorant Garamond`, `Didot` - 经典衬线
- **Body**: `Inter`, `DM Sans` - 现代无衬线平衡
- **Accent**: `Caslon`, `Bodoni` - 品牌特定衬线
- **Chinese**: `Source Han Serif`, `Noto Serif SC`

**Important**: Luxury brands use serif fonts for headlines to convey tradition and elegance, but modern sans-serif for body text to maintain readability.

```css
/* Type Scale - Elegant proportions */
--text-xs: 0.75rem;     /* 12px - Fine print */
--text-sm: 0.8125rem;   /* 13px - Secondary */
--text-base: 0.9375rem; /* 15px - Body */
--text-lg: 1.0625rem;   /* 17px - Lead */
--text-xl: 1.25rem;     /* 20px - Subhead */
--text-2xl: 1.5rem;     /* 24px - Heading */
--text-3xl: 2rem;        /* 32px - Title */
--text-4xl: 2.5rem;     /* 40px - Display */
--text-5xl: 3.5rem;     /* 56px - Hero */
--text-6xl: 4.5rem;     /* 72px - Statement */

/* Font Weights - Refined */
--font-light: 300;
--font-normal: 400;
--font-medium: 500;
--font-semibold: 600;
--font-bold: 700;

/* Line Heights - Generous for elegance */
--leading-tight: 1.1;
--leading-normal: 1.5;
--leading-relaxed: 1.75;

/* Letter Spacing - Refined, wide for luxury */
--tracking-tight: -0.02em;
--tracking-normal: 0;
--tracking-wide: 0.05em;
--tracking-wider: 0.1em;
--tracking-widest: 0.2em;

/* Case: UPPERCASE for labels */
--text-label: uppercase;
```

### Typography Classes

```css
/* Display title - Serif */
.title-display {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 3rem;
  font-weight: 400;
  line-height: 1.1;
  letter-spacing: -0.02em;
  color: var(--text-primary);
}

/* Section title */
.title-section {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 2rem;
  font-weight: 400;
  line-height: 1.2;
  letter-spacing: 0;
  color: var(--text-primary);
}

/* Card title */
.title-card {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 1.25rem;
  font-weight: 500;
  line-height: 1.3;
  color: var(--text-primary);
}

/* Body text */
.body {
  font-family: 'Inter', sans-serif;
  font-size: 0.9375rem;
  font-weight: 400;
  line-height: 1.75;
  color: var(--text-secondary);
}

/* Label - Uppercase, tracked */
.label {
  font-family: 'Inter', sans-serif;
  font-size: 0.6875rem;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.2em;
  color: var(--text-tertiary);
}

/* Price - Gold accent */
.price {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 1.125rem;
  font-weight: 400;
  color: var(--gold-primary);
}

/* Caption */
.caption {
  font-size: 0.75rem;
  font-weight: 400;
  font-style: italic;
  color: var(--text-tertiary);
}
```

---

## Spacing System

Generous, breathing space. Base unit: `8px`

```css
/* Spacing Scale - Generous */
--space-0: 0;
--space-1: 4px;
--space-2: 8px;
--space-3: 12px;
--space-4: 16px;
--space-5: 20px;
--space-6: 24px;
--space-8: 32px;
--space-10: 40px;
--space-12: 48px;
--space-16: 64px;
--space-20: 80px;
--space-24: 96px;
--space-32: 128px;
--space-40: 160px;

/* Page rhythm - Luxury spacing */
--page-margin: 80px;
--section-gap: 120px;
--content-max-width: 680px;
--page-max-width: 1440px;
```

### Layout Characteristics

- **Extreme whitespace** - Luxury through space
- **Centered content** - Editorial layout
- **Asymmetric balance** - Deliberate composition
- **Column-based** - Grid with breathing room

---

## Border Radius

Minimal, almost none. Sharp lines convey precision

```css
/* Border Radius - Minimal, sharp */
--radius-sm: 0;
--radius-md: 0;
--radius-lg: 2px;
--radius-xl: 4px;
--radius-full: 9999px;

/* Luxury is precise - no rounded corners */
```

---

## Shadow System

Subtle, refined, almost invisible depth

```css
/* Shadow Layers - Subtle, warm */
--shadow-sm: 0 1px 2px rgba(26, 26, 24, 0.04);
--shadow-md: 0 2px 8px rgba(26, 26, 24, 0.06);
--shadow-lg: 0 4px 16px rgba(26, 26, 24, 0.08);
--shadow-xl: 0 8px 32px rgba(26, 26, 24, 0.1);

/* Gold glow - subtle */
--shadow-gold: 0 0 0 1px var(--gold-light);

/* Card shadow */
--shadow-card: 0 1px 3px rgba(26, 26, 24, 0.04), 0 2px 8px rgba(26, 26, 24, 0.04);
```

---

## Component Patterns

### Buttons

Refined, understated buttons with gold accents

```css
/* Primary Button - Gold accent */
.btn-primary {
  background: var(--text-primary);
  color: var(--text-inverse);
  font-family: 'Inter', sans-serif;
  font-weight: 500;
  font-size: 0.8125rem;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  padding: 16px 40px;
  border-radius: 0;
  border: none;
  transition: all 250ms ease;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
}

.btn-primary:hover {
  background: var(--gold-dark);
}

.btn-primary:focus {
  outline: 2px solid var(--gold-primary);
  outline-offset: 2px;
}

/* Secondary Button - Outline */
.btn-secondary {
  background: transparent;
  color: var(--text-primary);
  font-family: 'Inter', sans-serif;
  font-weight: 500;
  font-size: 0.8125rem;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  padding: 15px 39px;
  border-radius: 0;
  border: 1px solid var(--text-primary);
  transition: all 250ms ease;
}

.btn-secondary:hover {
  background: var(--text-primary);
  color: var(--text-inverse);
}

/* Gold Button */
.btn-gold {
  background: var(--gold-primary);
  color: var(--text-inverse);
  font-family: 'Inter', sans-serif;
  font-weight: 500;
  font-size: 0.8125rem;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  padding: 16px 40px;
  border-radius: 0;
  border: none;
  transition: all 250ms ease;
}

.btn-gold:hover {
  background: var(--gold-hover);
}

/* Ghost Button */
.btn-ghost {
  background: transparent;
  color: var(--text-secondary);
  font-family: 'Inter', sans-serif;
  font-weight: 500;
  font-size: 0.75rem;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  padding: 12px 24px;
  border-radius: 0;
  border: none;
  transition: all 250ms ease;
}

.btn-ghost:hover {
  color: var(--text-primary);
}

/* Text link */
.btn-text {
  background: transparent;
  color: var(--text-secondary);
  font-family: 'Inter', sans-serif;
  font-size: 0.875rem;
  font-weight: 400;
  padding: 0;
  border: none;
  border-bottom: 1px solid var(--border-default);
  transition: all 200ms ease;
}

.btn-text:hover {
  color: var(--text-primary);
  border-bottom-color: var(--text-primary);
}
```

### Cards

Refined, minimal cards with subtle borders

```css
/* Card - Minimal */
.card {
  background: var(--bg-primary);
  border: 1px solid var(--border-subtle);
  padding: 40px;
  transition: all 300ms ease;
}

.card:hover {
  border-color: var(--border-default);
  box-shadow: var(--shadow-md);
}

/* Editorial card */
.card-editorial {
  background: var(--bg-primary);
  padding: 0;
}

.card-image {
  aspect-ratio: 3/4;
  overflow: hidden;
  margin-bottom: 24px;
}

.card-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 500ms ease;
}

.card:hover .card-image img {
  transform: scale(1.03);
}

/* Product card */
.card-product {
  text-align: center;
  padding: 32px 24px;
}

.card-product-image {
  width: 100%;
  aspect-ratio: 1;
  margin-bottom: 24px;
}

.card-product-image img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

.card-product-title {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 1.125rem;
  font-weight: 400;
  color: var(--text-primary);
  margin-bottom: 8px;
}

.card-product-price {
  font-size: 0.875rem;
  color: var(--gold-primary);
  letter-spacing: 0.05em;
}

/* Category card */
.card-category {
  position: relative;
  overflow: hidden;
  aspect-ratio: 2/3;
}

.card-category-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 500ms ease;
}

.card-category:hover .card-category-image {
  transform: scale(1.05);
}

.card-category-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(to top, rgba(26, 26, 24, 0.6) 0%, transparent 60%);
  display: flex;
  align-items: flex-end;
  padding: 32px;
}

.card-category-title {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 1.5rem;
  font-weight: 400;
  color: white;
}
```

### Input Fields

```css
/* Input */
.input {
  background: transparent;
  border: none;
  border-bottom: 1px solid var(--border-default);
  padding: 16px 0;
  font-family: 'Inter', sans-serif;
  font-size: 0.9375rem;
  color: var(--text-primary);
  transition: all 200ms ease;
  outline: none;
  width: 100%;
}

.input::placeholder {
  color: var(--text-muted);
}

.input:hover {
  border-bottom-color: var(--border-strong);
}

.input:focus {
  border-bottom-color: var(--gold-primary);
}

/* Label */
.input-label {
  display: block;
  font-family: 'Inter', sans-serif;
  font-size: 0.6875rem;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.2em;
  color: var(--text-tertiary);
  margin-bottom: 12px;
}

/* Helper text */
.input-helper {
  font-size: 0.75rem;
  color: var(--text-tertiary);
  margin-top: 8px;
}

/* Error state */
.input-error {
  border-bottom-color: var(--error);
}

/* Search input */
.search-input {
  background: var(--bg-secondary);
  border: 1px solid var(--border-subtle);
  padding: 16px 20px 16px 48px;
  font-size: 0.875rem;
}

.search-icon {
  position: absolute;
  left: 16px;
  top: 50%;
  transform: translateY(-50%);
  color: var(--text-tertiary);
}
```

### Navigation

```css
/* Navbar - Transparent */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 100;
  padding: 24px 80px;
  background: transparent;
  transition: all 300ms ease;
}

.navbar.scrolled {
  background: var(--bg-primary);
  box-shadow: var(--shadow-sm);
}

/* Logo */
.navbar-logo {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 1.5rem;
  font-weight: 400;
  color: var(--text-primary);
  letter-spacing: 0.05em;
}

/* Nav link */
.nav-link {
  font-family: 'Inter', sans-serif;
  font-size: 0.75rem;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  color: var(--text-secondary);
  padding: 8px 16px;
  transition: all 200ms ease;
}

.nav-link:hover {
  color: var(--text-primary);
}

/* Hero nav */
.hero-nav {
  padding: 40px 80px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

### Labels & Badges

```css
/* Label - Uppercase gold */
.label-gold {
  display: inline-block;
  font-family: 'Inter', sans-serif;
  font-size: 0.6875rem;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.15em;
  color: var(--gold-primary);
  padding: 4px 12px;
  border: 1px solid var(--gold-light);
}

/* Tag */
.tag {
  display: inline-block;
  font-family: 'Inter', sans-serif;
  font-size: 0.6875rem;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  color: var(--text-secondary);
  padding: 8px 16px;
  background: var(--bg-tertiary);
}

/* Status badge */
.badge {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  font-family: 'Inter', sans-serif;
  font-size: 0.6875rem;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  color: var(--text-secondary);
}

.badge::before {
  content: '';
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: currentColor;
}

.badge-new {
  color: var(--gold-primary);
}

.badge-new::before {
  background: var(--gold-primary);
}
```

### Dividers

```css
/* Divider - Gold line */
.divider {
  width: 100%;
  height: 1px;
  background: var(--border-subtle);
}

.divider-gold {
  width: 60px;
  height: 1px;
  background: var(--gold-primary);
}

/* Section divider */
.section-divider {
  display: flex;
  align-items: center;
  gap: 24px;
  padding: 40px 0;
}

.section-divider::before,
.section-divider::after {
  content: '';
  flex: 1;
  height: 1px;
  background: var(--border-subtle);
}

.section-divider-title {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 0.75rem;
  font-weight: 400;
  text-transform: uppercase;
  letter-spacing: 0.2em;
  color: var(--text-tertiary);
}
```

---

## Motion & Animation

Slow, graceful, deliberate. Luxury takes its time.

```css
/* Timing - Slower, more graceful */
--duration-fast: 200ms;
--duration-normal: 300ms;
--duration-slow: 400ms;
--duration-slower: 600ms;
--duration-slowest: 800ms;

/* Easing - Smooth, refined */
--ease-out: cubic-bezier(0.16, 1, 0.3, 1);
--ease-in-out: cubic-bezier(0.65, 0, 0.35, 1);

/* Fade in - Slower */
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

@keyframes fadeUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Reveal animation */
@keyframes reveal {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fadeIn {
  animation: fadeIn var(--duration-slow) var(--ease-out);
}

.animate-fadeUp {
  animation: fadeUp var(--duration-slow) var(--ease-out);
}

.animate-reveal {
  animation: reveal var(--duration-slower) var(--ease-out);
}

/* Hover - Subtle scale */
.hover-lift {
  transition: all var(--duration-normal) var(--ease-out);
}

.hover-lift:hover {
  transform: translateY(-4px);
}
```

---

## Visual Principles

1. **Restrained color** - Ivory, black, gold only
2. **Serif headlines** - Playfair Display for elegance
3. **Generous space** - Luxury through breathing room
4. **Subtle borders** - Light lines, not heavy shadows
5. **Deliberate motion** - Slow, graceful animations
6. **Quality over quantity** - Every element earns its place
7. **Uppercase labels** - Tracked labels for sophistication

---

## CSS Variables (Complete Set)

```css
:root {
  /* Colors - Ivory & Gold */
  --bg-primary: #FFFEF9;
  --bg-secondary: #FDFBF7;
  --bg-tertiary: #F8F5EE;
  --bg-warm: #F5F1E8;

  --text-primary: #1A1A18;
  --text-secondary: #4A4A46;
  --text-tertiary: #7A7A74;
  --text-muted: #A8A8A2;

  --border-subtle: rgba(26, 26, 24, 0.06);
  --border-default: rgba(26, 26, 24, 0.1);
  --border-strong: rgba(26, 26, 24, 0.2);

  --gold-primary: #C4A052;
  --gold-hover: #D4B066;
  --gold-light: #E8D5A8;
  --gold-dark: #A68B3D;
  --gold-subtle: rgba(196, 160, 82, 0.12);

  --accent-burgundy: #722F37;
  --accent-navy: #1B2838;

  /* Typography */
  --font-serif: 'Playfair Display', 'Cormorant Garamond', Georgia, serif;
  --font-sans: 'Inter', -apple-system, sans-serif;

  /* Spacing */
  --space-1: 4px;
  --space-2: 8px;
  --space-4: 16px;
  --space-6: 24px;
  --space-8: 32px;
  --space-12: 48px;
  --space-16: 64px;
  --space-20: 80px;

  /* Border Radius */
  --radius-lg: 2px;
  --radius-xl: 4px;

  /* Shadows */
  --shadow-sm: 0 1px 2px rgba(26, 26, 24, 0.04);
  --shadow-md: 0 2px 8px rgba(26, 26, 24, 0.06);
  --shadow-lg: 0 4px 16px rgba(26, 26, 24, 0.08);

  /* Transitions */
  --duration-fast: 200ms;
  --duration-normal: 300ms;
  --duration-slow: 400ms;
  --ease-out: cubic-bezier(0.16, 1, 0.3, 1);
}
```

---

## Usage Tips

- Use ivory backgrounds (#FFFEF9) instead of pure white
- Gold (#C4A052) as accent for emphasis, not dominant
- Playfair Display serif for all headlines
- Uppercase tracked labels (letter-spacing: 0.2em)
- Zero or minimal border-radius (0-4px)
- Slow, graceful animations (300ms+)
- Generous whitespace (80px+ page margins)
- Subtle borders, not heavy shadows
- Product photography: minimal, clean, white background