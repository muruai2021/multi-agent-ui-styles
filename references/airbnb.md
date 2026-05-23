---
name: airbnb-style
description: "Airbnb风格 - 温暖亲和旅行杂志风"
type: ui-style
---

# Airbnb Style Design System

## Overview

Airbnb风格是「温暖亲和」设计的典范——它将旅行杂志的编辑美学与民宿的温馨感融为一体。圆润的形状、温暖的插图、丰富的产品摄影，构建出让用户感到受欢迎和放松的界面。

**Brand**: Airbnb, Vrbo, Hopper, skypicker

**Mood**: 温暖、友好、旅行、探索、杂志感、人文、亲切、有趣

---

## Color Palette

### Warm Neutrals (Primary)

```css
/* Background Scale - Warm creams */
--bg-primary: #FFFFFF;
--bg-secondary: #F7F7F7;
--bg-tertiary: #EBEBEB;
--bg-warm: #FDF9F3;
--bg-cream: #FAF7F2;

/* Text - Warm blacks */
--text-primary: #222222;
--text-secondary: #717171;
--text-tertiary: #B0B0B0;
--text-placeholder: #C4C4C4;
--text-inverse: #FFFFFF;

/* Airbnb Red - Signature warm red */
--accent-primary: #FF385C;
--accent-hover: #E31C5F;
--accent-subtle: rgba(255, 56, 92, 0.1);
--accent-light: #FF5A5F;

/* Secondary accents - Playful palette */
--accent-coral: #FC642D;
--accent-teal: #00A699;
--accent-gold: #FFB400;

/* Semantic Colors */
--success: #008A05;
--warning: #C45500;
--error: #C13515;
--info: #0077CC;

/* Cover/Category colors */
--cover-sage: #C5D3C8;
--cover-sand: #E8DED2;
--cover-blush: #F3E6E2;
--cover-sky: #D0E4ED;
--cover-rose: #F0D7D9;
```

### Dark Mode

```css
--bg-primary-dark: #161616;
--bg-secondary-dark: #1F1F1F;
--text-primary-dark: #FFFFFF;
--text-secondary-dark: #A3A3A3;
--accent-primary-dark: #FF385C;
```

### Tailwind Config

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        airbnb: {
          red: '#FF385C',
          coral: '#FC642D',
          teal: '#00A699',
          gold: '#FFB400',
        },
        bg: {
          primary: '#FFFFFF',
          secondary: '#F7F7F7',
          warm: '#FDF9F3',
        },
        text: {
          primary: '#222222',
          secondary: '#717171',
        },
      },
      borderRadius: {
        'lg': '12px',
        'xl': '16px',
        '2xl': '24px',
        '3xl': '32px',
      },
    },
  },
}
```

---

## Typography

**Font Stack**:
- **Display**: `Airbnb Cereal`, `Neue Montreal`, `Satoshi`, `Circular`
- **Body**: `Inter`, `DM Sans`
- **Fallback**: `system-ui`, `-apple-system`

**Important**: Airbnb uses a custom typeface (Airbnb Cereal) but for web you can approximate with `Satoshi`, `Circular`, or `Inter` with rounded letterforms.

```css
/* Type Scale */
--text-xs: 0.75rem;     /* 12px */
--text-sm: 0.875rem;    /* 14px */
--text-base: 1rem;       /* 16px */
--text-lg: 1.125rem;    /* 18px */
--text-xl: 1.375rem;    /* 22px */
--text-2xl: 1.75rem;    /* 28px */
--text-3xl: 2rem;       /* 32px */
--text-4xl: 2.5rem;     /* 40px */

/* Font Weights - Rounded feel */
--font-normal: 400;
--font-medium: 500;
--font-semibold: 600;
--font-bold: 700;

/* Line Heights - Comfortable */
--leading-tight: 1.2;
--leading-normal: 1.5;
--leading-relaxed: 1.65;

/* Letter Spacing */
--tracking-tight: -0.02em;
--tracking-normal: 0;
--tracking-wide: 0.02em;
```

### Typography Classes

```css
/* Headline */
.headline {
  font-size: 2rem;
  font-weight: 600;
  color: var(--text-primary);
  line-height: 1.2;
  letter-spacing: -0.01em;
}

/* Card title */
.card-title {
  font-size: 1.125rem;
  font-weight: 600;
  color: var(--text-primary);
  line-height: 1.3;
}

/* Body text */
.body {
  font-size: 1rem;
  font-weight: 400;
  color: var(--text-primary);
  line-height: 1.6;
}

/* Price display */
.price {
  font-size: 1.125rem;
  font-weight: 600;
  color: var(--text-primary);
}

.price-amount {
  font-weight: 700;
}

/* Badge text */
.badge-text {
  font-size: 0.75rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.04em;
}
```

---

## Spacing System

Comfortable spacing with rounded feel. Base unit: `8px`

```css
/* Spacing Scale */
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

/* Card spacing */
--card-padding: 16px;
--card-gap: 16px;

/* Page rhythm */
--page-padding: 24px;
--section-gap: 48px;
```

---

## Border Radius

Rounded, friendly, approachable

```css
/* Border Radius - Rounded, friendly */
--radius-sm: 8px;
--radius-md: 12px;
--radius-lg: 16px;
--radius-xl: 24px;
--radius-2xl: 32px;
--radius-full: 9999px;

/* Pill shape */
.rounded-pill {
  border-radius: var(--radius-full);
}

/* Tailwind classes */
.rounded-lg { border-radius: 16px; }
.rounded-xl { border-radius: 24px; }
.rounded-2xl { border-radius: 32px; }
```

---

## Shadow System

Soft, warm shadows with slight color

```css
/* Shadow Layers - Warm undertones */
--shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05);
--shadow-md: 0 2px 8px rgba(0, 0, 0, 0.08);
--shadow-lg: 0 4px 16px rgba(0, 0, 0, 0.1);
--shadow-xl: 0 8px 28px rgba(0, 0, 0, 0.12);

/* Card shadow - warmer */
--shadow-card: 0 2px 8px rgba(0, 0, 0, 0.06);

/* Image shadow */
--shadow-image: 0 2px 8px rgba(0, 0, 0, 0.08);

/* Hover shadow */
--shadow-hover: 0 4px 20px rgba(0, 0, 0, 0.12);
```

---

## Component Patterns

### Buttons

Rounded, warm, inviting buttons

```css
/* Primary Button - Red */
.btn-primary {
  background: var(--accent-primary);
  color: white;
  font-weight: 600;
  font-size: 1rem;
  padding: 14px 24px;
  border-radius: var(--radius-lg);
  border: none;
  transition: all 200ms ease;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
}

.btn-primary:hover {
  background: var(--accent-hover);
  transform: scale(1.02);
}

.btn-primary:active {
  transform: scale(0.98);
}

/* Secondary Button */
.btn-secondary {
  background: white;
  color: var(--text-primary);
  font-weight: 600;
  font-size: 1rem;
  padding: 14px 24px;
  border-radius: var(--radius-lg);
  border: 1px solid var(--text-primary);
  transition: all 200ms ease;
}

.btn-secondary:hover {
  background: var(--bg-secondary);
}

/* Ghost Button */
.btn-ghost {
  background: transparent;
  color: var(--text-primary);
  font-weight: 500;
  font-size: 0.875rem;
  padding: 8px 16px;
  border-radius: var(--radius-lg);
  border: none;
  transition: all 200ms ease;
}

.btn-ghost:hover {
  background: var(--bg-secondary);
}

/* Pill Button */
.btn-pill {
  padding: 10px 20px;
  border-radius: var(--radius-full);
}

/* Icon Button - Rounded square */
.btn-icon {
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: var(--radius-lg);
  background: white;
  border: 1px solid var(--bg-tertiary);
  color: var(--text-primary);
  transition: all 200ms ease;
}

.btn-icon:hover {
  border-color: var(--text-primary);
}

/* Floating Action Button */
.btn-fab {
  position: fixed;
  bottom: 24px;
  right: 24px;
  width: 56px;
  height: 56px;
  border-radius: var(--radius-full);
  background: var(--accent-primary);
  color: white;
  box-shadow: var(--shadow-xl);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 200ms ease;
}

.btn-fab:hover {
  transform: scale(1.1);
  box-shadow: 0 8px 32px rgba(255, 56, 92, 0.4);
}
```

### Cards

Warm, rounded cards with product focus

```css
/* Listing Card */
.card-listing {
  border-radius: var(--radius-xl);
  overflow: hidden;
  cursor: pointer;
  transition: all 200ms ease;
}

.card-listing:hover {
  transform: scale(1.02);
}

.card-listing:hover .card-image img {
  transform: scale(1.05);
}

/* Card Image */
.card-image {
  aspect-ratio: 4/3;
  border-radius: var(--radius-lg);
  overflow: hidden;
  position: relative;
}

.card-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 300ms ease;
}

/* Favorite button */
.card-favorite {
  position: absolute;
  top: 12px;
  right: 12px;
  width: 28px;
  height: 28px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: white;
  border-radius: var(--radius-full);
  color: var(--text-primary);
  transition: all 200ms ease;
}

.card-favorite:hover {
  transform: scale(1.2);
}

.card-favorite.active svg {
  fill: var(--accent-primary);
  stroke: var(--accent-primary);
}

/* Card Content */
.card-content {
  padding: 12px 0;
}

.card-location {
  font-size: 0.875rem;
  font-weight: 500;
  color: var(--text-primary);
}

.card-title {
  font-size: 1rem;
  font-weight: 500;
  color: var(--text-primary);
  margin: 4px 0;
}

.card-price {
  font-size: 1rem;
  font-weight: 600;
  color: var(--text-primary);
}

.card-meta {
  font-size: 0.875rem;
  color: var(--text-secondary);
}

/* Rating badge */
.rating-badge {
  display: inline-flex;
  align-items: center;
  gap: 4px;
  font-size: 0.875rem;
  font-weight: 500;
}

.rating-badge svg {
  width: 14px;
  height: 14px;
  fill: var(--text-primary);
}
```

### Input Fields

Rounded, warm inputs

```css
/* Input */
.input {
  background: white;
  border: 1px solid var(--bg-tertiary);
  border-radius: var(--radius-lg);
  padding: 14px 16px;
  font-size: 1rem;
  color: var(--text-primary);
  transition: all 200ms ease;
  outline: none;
  width: 100%;
}

.input::placeholder {
  color: var(--text-placeholder);
}

.input:hover {
  border-color: var(--text-tertiary);
}

.input:focus {
  border-color: var(--accent-primary);
  box-shadow: 0 0 0 2px var(--accent-subtle);
}

/* Search input */
.search-input {
  padding: 14px 16px 14px 48px;
  border-radius: var(--radius-full);
  box-shadow: var(--shadow-md);
}

.search-input-icon {
  position: absolute;
  left: 16px;
  top: 50%;
  transform: translateY(-50%);
  color: var(--text-secondary);
}

/* Date input */
.date-input {
  padding: 14px 16px;
  border-radius: var(--radius-lg);
  font-size: 1rem;
}

/* Select */
.select {
  appearance: none;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='16' height='16' viewBox='0 0 24 24' fill='none' stroke='%23717171' stroke-width='2'%3E%3Cpath d='M6 9l6 6 6-6'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right 16px center;
  padding-right: 40px;
}
```

### Navigation

```css
/* Navbar */
.navbar {
  background: white;
  border-bottom: 1px solid var(--bg-tertiary);
  height: 80px;
  display: flex;
  align-items: center;
  padding: 0 24px;
  position: sticky;
  top: 0;
  z-index: 100;
}

/* Logo */
.navbar-logo {
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--accent-primary);
}

/* Nav link */
.nav-link {
  font-size: 0.875rem;
  font-weight: 500;
  color: var(--text-primary);
  padding: 8px 16px;
  border-radius: var(--radius-lg);
  transition: all 200ms ease;
}

.nav-link:hover {
  background: var(--bg-secondary);
}

/* Search bar */
.search-bar {
  display: flex;
  align-items: center;
  background: var(--bg-secondary);
  border: 1px solid var(--bg-tertiary);
  border-radius: var(--radius-full);
  padding: 8px 8px 8px 24px;
  gap: 8px;
  transition: all 200ms ease;
}

.search-bar:hover {
  box-shadow: var(--shadow-md);
}

/* Filter pill */
.filter-pill {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 10px 16px;
  background: white;
  border: 1px solid var(--bg-tertiary);
  border-radius: var(--radius-full);
  font-size: 0.875rem;
  font-weight: 500;
  color: var(--text-primary);
  transition: all 200ms ease;
}

.filter-pill:hover {
  border-color: var(--text-primary);
}

.filter-pill.active {
  background: var(--bg-primary);
  border-color: var(--text-primary);
}
```

### Badges

```css
/* Badge */
.badge {
  display: inline-flex;
  align-items: center;
  padding: 6px 12px;
  font-size: 0.75rem;
  font-weight: 600;
  border-radius: var(--radius-full);
  background: var(--bg-secondary);
  color: var(--text-primary);
}

/* Superhost badge */
.badge-superhost {
  background: white;
  border: 1px solid var(--text-primary);
  font-weight: 600;
}

.badge-superhost svg {
  width: 16px;
  height: 16px;
}

/* Category badge */
.badge-category {
  background: var(--bg-warm);
  color: var(--text-primary);
}

/* Price badge */
.badge-price {
  background: var(--text-primary);
  color: white;
}
```

---

## Motion & Animation

Friendly, bouncy, inviting

```css
/* Timing */
--duration-fast: 150ms;
--duration-normal: 200ms;
--duration-slow: 300ms;
--duration-bounce: 400ms;

/* Easing - Bouncy feel */
--ease-out: cubic-bezier(0.16, 1, 0.3, 1);
--ease-bounce: cubic-bezier(0.34, 1.56, 0.64, 1);

/* Hover scale */
.hover-scale {
  transition: transform var(--duration-normal) var(--ease-out);
}

.hover-scale:hover {
  transform: scale(1.03);
}

/* Heart animation */
@keyframes heartBeat {
  0% { transform: scale(1); }
  25% { transform: scale(1.3); }
  50% { transform: scale(1); }
  75% { transform: scale(1.3); }
  100% { transform: scale(1); }
}

.heart-animation {
  animation: heartBeat 0.4s ease-in-out;
}

/* Fade animations */
@keyframes fadeUp {
  from {
    opacity: 0;
    transform: translateY(16px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fadeUp {
  animation: fadeUp var(--duration-slow) var(--ease-out);
}

/* Stagger children */
.stagger-children > * {
  opacity: 0;
  transform: translateY(16px);
  animation: fadeUp var(--duration-slow) var(--ease-out) forwards;
}

.stagger-children > *:nth-child(1) { animation-delay: 0ms; }
.stagger-children > *:nth-child(2) { animation-delay: 100ms; }
.stagger-children > *:nth-child(3) { animation-delay: 200ms; }
.stagger-children > *:nth-child(4) { animation-delay: 300ms; }
```

---

## Visual Principles

1. **Warmth first** - Cream backgrounds, coral accents, friendly feel
2. **Rounded everything** - Large radii (12-24px) for approachable look
3. **Product photography** - Large images, hero photos dominate
4. **Bouncy interactions** - Slight bounce on hover/click
5. **Category colors** - Subtle color coding for organization
6. **Trust signals** - Ratings, reviews, verified badges

---

## CSS Variables (Complete Set)

```css
:root {
  /* Colors */
  --bg-primary: #FFFFFF;
  --bg-secondary: #F7F7F7;
  --bg-tertiary: #EBEBEB;
  --bg-warm: #FDF9F3;

  --text-primary: #222222;
  --text-secondary: #717171;
  --text-tertiary: #B0B0B0;

  --accent-primary: #FF385C;
  --accent-hover: #E31C5F;
  --accent-subtle: rgba(255, 56, 92, 0.1);
  --accent-coral: #FC642D;
  --accent-teal: #00A699;

  --success: #008A05;
  --warning: #C45500;
  --error: #C13515;

  /* Typography */
  --font-sans: 'Inter', -apple-system, sans-serif;

  /* Spacing */
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-6: 24px;
  --space-8: 32px;
  --space-10: 40px;
  --space-12: 48px;

  /* Border Radius */
  --radius-sm: 8px;
  --radius-md: 12px;
  --radius-lg: 16px;
  --radius-xl: 24px;
  --radius-2xl: 32px;
  --radius-full: 9999px;

  /* Shadows */
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05);
  --shadow-md: 0 2px 8px rgba(0, 0, 0, 0.08);
  --shadow-lg: 0 4px 16px rgba(0, 0, 0, 0.1);
  --shadow-xl: 0 8px 28px rgba(0, 0, 0, 0.12);

  /* Transitions */
  --duration-fast: 150ms;
  --duration-normal: 200ms;
  --duration-slow: 300ms;
  --ease-out: cubic-bezier(0.16, 1, 0.3, 1);
  --ease-bounce: cubic-bezier(0.34, 1.56, 0.64, 1);
}
```

---

## Usage Tips

- Use warm cream backgrounds (#FDF9F3) instead of pure white
- Large rounded corners (16-24px) for friendly feel
- Airbnb red (#FF385C) for primary CTAs
- Product photography should dominate cards
- Bouncy hover animations (scale 1.02-1.03)
- Rating stars with numeric display
- Pill-shaped search bar and filter buttons