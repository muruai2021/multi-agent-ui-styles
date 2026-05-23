---
name: apple-style
description: "Apple风格 - 戏剧极简奢华科技"
type: ui-style
---

# Apple Style Design System

## Overview

Apple风格是「戏剧极简」的最高体现——每个元素都经过精心雕琢，大量留白创造呼吸感，微妙的深度层次构建奢华感。它代表了对完美的追求和对细节的极致关注。

**Brand**: Apple, macOS, iOS, iPadOS

**Mood**: 奢华、精致、戏剧性、沉浸、简约、未来感、极致工艺

---

## Color Palette

### Light Mode (Primary - Dramatic)

```css
/* Background Scale - Warm whites with subtle depth */
--bg-primary: #FFFFFF;
--bg-secondary: #F5F5F7;
--bg-tertiary: #E8E8ED;
--bg-elevated: rgba(255, 255, 255, 0.8);
--bg-overlay: rgba(0, 0, 0, 0.4);

/* Text - Deep blacks with warmth */
--text-primary: #1D1D1F;
--text-secondary: #86868B;
--text-tertiary: #6E6E73;
--text-placeholder: #AEAEB2;
--text-inverse: #FFFFFF;

/* Borders - Ultra-subtle */
--border-subtle: rgba(0, 0, 0, 0.06);
--border-default: rgba(0, 0, 0, 0.1);
--border-strong: rgba(0, 0, 0, 0.2);

/* Apple Blue - System accent */
--accent-primary: #0071E3;
--accent-hover: #0077ED;
--accent-subtle: rgba(0, 113, 227, 0.08);

/* Semantic Colors - Soft, harmonious */
--success: #34C759;
--warning: #FF9500;
--error: #FF3B30;
--info: #007AFF;

/* Frosted Glass */
--glass-bg: rgba(255, 255, 255, 0.72);
--glass-border: rgba(255, 255, 255, 0.18);
--glass-shadow: 0 8px 32px rgba(0, 0, 0, 0.12);
--glass-blur: blur(20px);
```

### Dark Mode (Dramatic Depth)

```css
--bg-primary-dark: #000000;
--bg-secondary-dark: #1D1D1F;
--bg-tertiary-dark: #2D2D2F;
--bg-elevated-dark: rgba(255, 255, 255, 0.08);

--text-primary-dark: #F5F5F7;
--text-secondary-dark: #86868B;
--text-tertiary-dark: #6E6E73;

--border-subtle-dark: rgba(255, 255, 255, 0.08);
--border-default-dark: rgba(255, 255, 255, 0.16);

--accent-primary-dark: #0A84FF;
```

### Tailwind Config

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        apple: {
          blue: '#0071E3',
          gray: '#86868B',
        },
        bg: {
          primary: '#FFFFFF',
          secondary: '#F5F5F7',
          tertiary: '#E8E8ED',
        },
        text: {
          primary: '#1D1D1F',
          secondary: '#86868B',
        },
      },
      backdropBlur: {
        'xs': '4px',
        'sm': '8px',
        'md': '12px',
        'lg': '20px',
        'xl': '40px',
      },
    },
  },
}
```

---

## Typography

**Font Stack**:
- **Primary**: `SF Pro Display`, `SF Pro Text` (Apple's signature)
- **Fallback**: `-apple-system`, `BlinkMacSystemFont`
- **Web**: `Inter`, `SF Pro`, `-apple-system`

**Important**: Apple typography uses SF Pro with extreme attention to tracking, weight, and optical sizing. The system uses `font-weight: 500` (medium) as default, never bold.

```css
/* Type Scale - Large, dramatic */
--text-xs: 0.6875rem;   /* 11px - captions */
--text-sm: 0.75rem;     /* 12px - fine print */
--text-base: 0.875rem;  /* 14px */
--text-lg: 0.9375rem;   /* 15px */
--text-xl: 1.0625rem;   /* 17px */
--text-2xl: 1.25rem;    /* 20px */
--text-3xl: 1.5rem;     /* 24px */
--text-4xl: 1.875rem;   /* 30px */
--text-5xl: 2.5rem;     /* 40px */
--text-6xl: 3rem;       /* 48px */
--text-7xl: 4rem;       /* 64px - hero */
--text-8xl: 5rem;       /* 80px - dramatic hero */

/* Font Weights - Light to medium */
--font-light: 300;
--font-normal: 400;
--font-medium: 500;
--font-semibold: 600;

/* Line Heights - Generous */
--leading-none: 1;
--leading-tight: 1.15;
--leading-normal: 1.4;
--leading-relaxed: 1.65;

/* Letter Spacing - Slight tracking */
--tracking-tight: -0.02em;
--tracking-normal: 0;
--tracking-wide: 0.01em;
--tracking-wider: 0.03em;
```

### Typography Classes

```css
/* Hero headline - dramatic */
.headline-hero {
  font-size: 4rem;
  font-weight: 600;
  line-height: 1.05;
  letter-spacing: -0.03em;
  color: var(--text-primary);
}

/* Section headline */
.headline-section {
  font-size: 2.5rem;
  font-weight: 600;
  line-height: 1.1;
  letter-spacing: -0.02em;
  color: var(--text-primary);
}

/* Title */
.title {
  font-size: 1.5rem;
  font-weight: 600;
  line-height: 1.2;
  letter-spacing: -0.01em;
}

/* Body - generous spacing */
.body {
  font-size: 0.9375rem;
  font-weight: 400;
  line-height: 1.65;
  letter-spacing: 0.01em;
}

/* Fine print */
.caption {
  font-size: 0.6875rem;
  font-weight: 500;
  letter-spacing: 0.04em;
  color: var(--text-tertiary);
}
```

---

## Spacing System

Generous, dramatic spacing. Base unit: `8px`

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
--space-48: 192px;

/* Layout */
--container-max: 980px;
--container-wide: 1200px;
--container-narrow: 680px;
```

### Layout Characteristics

- **Dramatic whitespace** - Huge margins between sections
- **Content centering** - Most content is centered
- **Visual breathing** - Nothing feels cramped
- **Tiered hierarchy** - Clear visual tiers

---

## Border Radius

Subtle, refined curves. Apple hardware-inspired

```css
/* Border Radius - Refined curves */
--radius-sm: 6px;
--radius-md: 10px;
--radius-lg: 14px;
--radius-xl: 18px;
--radius-2xl: 24px;
--radius-3xl: 32px;
--radius-full: 9999px;
```

---

## Shadow System

Subtle, layered depth with slight blue tint

```css
/* Shadow Layers - Subtle depth */
--shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.06);
--shadow-md: 0 4px 12px rgba(0, 0, 0, 0.08);
--shadow-lg: 0 12px 40px rgba(0, 0, 0, 0.1);
--shadow-xl: 0 24px 64px rgba(0, 0, 0, 0.12);

/* Floating elements */
--shadow-floating: 0 8px 32px rgba(0, 0, 0, 0.12), 0 2px 8px rgba(0, 0, 0, 0.08);

/* Button depth */
--shadow-button: 0 2px 8px rgba(0, 0, 0, 0.08);
--shadow-button-hover: 0 4px 16px rgba(0, 0, 0, 0.12);
```

---

## Component Patterns

### Buttons

Clean, generous, with subtle depth

```css
/* Primary Button - Blue */
.btn-primary {
  background: var(--accent-primary);
  color: white;
  font-weight: 500;
  font-size: 0.9375rem;
  padding: 12px 24px;
  border-radius: var(--radius-xl);
  border: none;
  transition: all 200ms ease;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 6px;
  box-shadow: var(--shadow-button);
}

.btn-primary:hover {
  background: var(--accent-hover);
  box-shadow: var(--shadow-button-hover);
}

.btn-primary:active {
  transform: scale(0.98);
}

/* Secondary Button */
.btn-secondary {
  background: var(--bg-elevated);
  color: var(--accent-primary);
  font-weight: 500;
  font-size: 0.9375rem;
  padding: 12px 24px;
  border-radius: var(--radius-xl);
  border: 1px solid var(--border-default);
  backdrop-filter: blur(20px);
  transition: all 200ms ease;
}

.btn-secondary:hover {
  background: rgba(0, 113, 227, 0.08);
}

/* Pill Button */
.btn-pill {
  padding: 12px 32px;
  border-radius: var(--radius-full);
}

/* Icon Button */
.btn-icon {
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: var(--radius-full);
  background: var(--bg-secondary);
  color: var(--text-primary);
  transition: all 200ms ease;
}

.btn-icon:hover {
  background: var(--bg-tertiary);
}
```

### Cards

Floating cards with glass effect

```css
/* Card */
.card {
  background: white;
  border-radius: var(--radius-2xl);
  padding: 48px;
  box-shadow: var(--shadow-lg);
  transition: all 300ms ease;
}

.card:hover {
  transform: translateY(-4px);
  box-shadow: var(--shadow-xl);
}

/* Glass Card */
.glass-card {
  background: var(--glass-bg);
  border: 1px solid var(--glass-border);
  border-radius: var(--radius-2xl);
  backdrop-filter: blur(20px);
  box-shadow: var(--glass-shadow);
}

/* Image card */
.card-image {
  border-radius: var(--radius-xl);
  overflow: hidden;
  aspect-ratio: 16/10;
}

.card-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 400ms ease;
}

.card-image:hover img {
  transform: scale(1.02);
}
```

### Input Fields

Floating labels, generous padding

```css
/* Input */
.input {
  background: var(--bg-secondary);
  border: 1px solid transparent;
  border-radius: var(--radius-lg);
  padding: 16px 20px;
  font-size: 1rem;
  color: var(--text-primary);
  transition: all 200ms ease;
  outline: none;
  width: 100%;
}

.input::placeholder {
  color: var(--text-placeholder);
}

.input:focus {
  background: white;
  border-color: var(--accent-primary);
  box-shadow: 0 0 0 4px var(--accent-subtle);
}

/* Floating label input */
.input-floating {
  padding: 24px 20px 8px;
}

.input-floating-label {
  position: absolute;
  left: 20px;
  top: 50%;
  transform: translateY(-50%);
  font-size: 1rem;
  color: var(--text-secondary);
  pointer-events: none;
  transition: all 200ms ease;
}

.input-floating:focus + .input-floating-label,
.input-floating:not(:placeholder-shown) + .input-floating-label {
  top: 12px;
  font-size: 0.6875rem;
  color: var(--accent-primary);
}
```

### Navigation

```css
/* Navbar */
.navbar {
  background: var(--glass-bg);
  backdrop-filter: blur(20px);
  border-bottom: 1px solid var(--border-subtle);
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0 24px;
  position: sticky;
  top: 0;
  z-index: 100;
}

/* Navbar link */
.nav-link {
  font-size: 0.75rem;
  font-weight: 500;
  color: var(--text-secondary);
  padding: 8px 16px;
  transition: all 200ms ease;
}

.nav-link:hover {
  color: var(--text-primary);
}

/* Navbar icon */
.nav-icon {
  width: 20px;
  height: 20px;
  color: var(--text-secondary);
}

/* Page header */
.page-header {
  padding: 80px 0 48px;
  text-align: center;
}

/* Section header */
.section-header {
  padding: 64px 0 48px;
  text-align: center;
}
```

### Typography Display

```css
/* Hero text */
.hero-title {
  font-size: 4rem;
  font-weight: 600;
  line-height: 1.05;
  letter-spacing: -0.03em;
  color: var(--text-primary);
  margin-bottom: 16px;
}

.hero-subtitle {
  font-size: 1.25rem;
  font-weight: 400;
  color: var(--text-secondary);
  line-height: 1.5;
  max-width: 600px;
  margin: 0 auto;
}

/* Gradient text */
.gradient-text {
  background: linear-gradient(120deg, #0071E3 0%, #5B5BD6 50%, #8264FA 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
```

---

## Motion & Animation

Fluid, natural, Apple-signature spring animations

```css
/* Timing */
--duration-fast: 150ms;
--duration-normal: 250ms;
--duration-slow: 350ms;
--duration-slower: 500ms;

/* Easing - Spring-like */
--ease-out: cubic-bezier(0.16, 1, 0.3, 1);
--ease-spring: cubic-bezier(0.25, 0.46, 0.45, 0.94);
--ease-smooth: cubic-bezier(0.42, 0, 0.58, 1);

/* Scale hover */
.hover-scale {
  transition: transform var(--duration-normal) var(--ease-out);
}

.hover-scale:hover {
  transform: scale(1.02);
}

/* Lift hover */
.hover-lift {
  transition: transform var(--duration-normal) var(--ease-out), box-shadow var(--duration-normal) var(--ease-out);
}

.hover-lift:hover {
  transform: translateY(-4px);
}

/* Fade animations */
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

@keyframes slideIn {
  from { transform: translateX(-20px); opacity: 0; }
  to { transform: translateX(0); opacity: 1; }
}

.animate-fadeIn {
  animation: fadeIn var(--duration-slow) var(--ease-out);
}

.animate-fadeUp {
  animation: fadeUp var(--duration-slow) var(--ease-out);
}

/* Spring bounce */
@keyframes springIn {
  0% { transform: scale(0.95); opacity: 0; }
  50% { transform: scale(1.02); }
  100% { transform: scale(1); opacity: 1; }
}

.animate-springIn {
  animation: springIn var(--duration-slow) var(--ease-spring);
}
```

---

## Visual Principles

1. **Extreme whitespace** - Luxury through generous space
2. **Content centering** - Most content centered for focus
3. **Large type** - Big, confident typography
4. **Subtle depth** - Floating elements with glass effect
5. **System harmony** - Feels native to Apple ecosystem
6. **Fluid motion** - Spring-based, natural animations

---

## CSS Variables (Complete Set)

```css
:root {
  /* Colors */
  --bg-primary: #FFFFFF;
  --bg-secondary: #F5F5F7;
  --bg-tertiary: #E8E8ED;
  --bg-elevated: rgba(255, 255, 255, 0.8);

  --text-primary: #1D1D1F;
  --text-secondary: #86868B;
  --text-tertiary: #6E6E73;

  --border-subtle: rgba(0, 0, 0, 0.06);
  --border-default: rgba(0, 0, 0, 0.1);

  --accent-primary: #0071E3;
  --accent-hover: #0077ED;
  --accent-subtle: rgba(0, 113, 227, 0.08);

  --success: #34C759;
  --warning: #FF9500;
  --error: #FF3B30;

  /* Glass effect */
  --glass-bg: rgba(255, 255, 255, 0.72);
  --glass-border: rgba(255, 255, 255, 0.18);
  --glass-blur: blur(20px);

  /* Typography */
  --font-sans: 'Inter', -apple-system, 'SF Pro', sans-serif;

  /* Spacing */
  --space-4: 16px;
  --space-6: 24px;
  --space-8: 32px;
  --space-12: 48px;
  --space-16: 64px;
  --space-20: 80px;

  /* Border Radius */
  --radius-sm: 6px;
  --radius-md: 10px;
  --radius-lg: 14px;
  --radius-xl: 18px;
  --radius-2xl: 24px;

  /* Shadows */
  --shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.06);
  --shadow-md: 0 4px 12px rgba(0, 0, 0, 0.08);
  --shadow-lg: 0 12px 40px rgba(0, 0, 0, 0.1);
  --shadow-floating: 0 8px 32px rgba(0, 0, 0, 0.12), 0 2px 8px rgba(0, 0, 0, 0.08);

  /* Transitions */
  --duration-fast: 150ms;
  --duration-normal: 250ms;
  --ease-out: cubic-bezier(0.16, 1, 0.3, 1);
}
```

---

## Usage Tips

- Use extreme whitespace (80px+ section padding)
- Center content for dramatic effect
- Large typography (40px+ hero headlines)
- Subtle glass effect for elevated elements
- Apple blue (#0071E3) for interactive elements
- Spring animations for hover states
- Rounded corners (radius-xl to radius-2xl)