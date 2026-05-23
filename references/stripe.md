---
name: stripe-style
description: "Stripe风格 - 精致奢华金融风"
type: ui-style
---

# Stripe Style Design System

## Overview

Stripe风格代表「精致奢华」与金融级信任——每个细节都经过精心打磨，传达专业、可靠、高端的品牌形象。它融合了瑞士平面设计的严谨与现代科技产品的流畅。

**Brands**: Stripe, Square, Plaid, Mercury, Brex, Carta

**Mood**: 专业、精致、信任、高端、金融级、精确、优雅

---

## Color Palette

### Refined Light (Primary)

```css
/* Background Scale - Clean whites with subtle warmth */
--bg-primary: #FFFFFF;
--bg-secondary: #F6F9FC;
--bg-tertiary: #F1F5F9;
--bg-elevated: #FFFFFF;
--bg-overlay: rgba(0, 0, 0, 0.4);

/* Text - Warm blacks */
--text-primary: #1A1F36;
--text-secondary: #697386;
--text-tertiary: #8792A2;
--text-placeholder: #ABB5C4;
--text-inverse: #FFFFFF;

/* Borders - Subtle definition */
--border-subtle: #E3E8EE;
--border-default: #CBD2DC;
--border-strong: #9CA3AF;

/* Stripe Purple - Signature accent */
--accent-primary: #635BFF;
--accent-hover: #7A73FF;
--accent-subtle: rgba(99, 91, 255, 0.1);
--accent-muted: rgba(99, 91, 255, 0.25);

/* Semantic Colors - Refined, not alarming */
--success: #30D158;
--success-bg: rgba(48, 209, 88, 0.1);
--warning: #FF9500;
--warning-bg: rgba(255, 149, 0, 0.1);
--error: #FF3B30;
--error-bg: rgba(255, 59, 48, 0.1);
--info: #007AFF;
--info-bg: rgba(0, 122, 255, 0.1);

/* Gradient - Subtle, not overwhelming */
--gradient-start: #635BFF;
--gradient-end: #8B5CF6;
```

### Dark Mode

```css
--bg-primary-dark: #0A0A0F;
--bg-secondary-dark: #111118;
--bg-tertiary-dark: #1A1A24;
--text-primary-dark: #F6F9FC;
--text-secondary-dark: #8792A2;
--border-subtle-dark: #2A2A38;
--accent-primary-dark: #7A73FF;
```

### Tailwind Config

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        stripe: {
          purple: '#635BFF',
          hover: '#7A73FF',
        },
        bg: {
          primary: '#FFFFFF',
          secondary: '#F6F9FC',
          tertiary: '#F1F5F9',
        },
        text: {
          primary: '#1A1F36',
          secondary: '#697386',
        },
        border: {
          subtle: '#E3E8EE',
          DEFAULT: '#CBD2DC',
        },
      },
    },
  },
}
```

---

## Typography

**Font Stack**:
- **Headings**: `Chartograph`, `Placard`, custom display fonts
- **Body**: `Inter` (Stripe uses Inter, customized)
- **Numeric/Mono**: `JetBrains Mono` for numbers and code

**Important**: Stripe uses custom fonts for display but Inter for body. The key is the extreme attention to weight contrast and optical sizing.

```css
/* Type Scale - Generous, readable */
--text-xs: 0.75rem;     /* 12px */
--text-sm: 0.8125rem;   /* 13px */
--text-base: 0.9375rem; /* 15px - Stripe's base is larger */
--text-lg: 1.0625rem;   /* 17px */
--text-xl: 1.25rem;     /* 20px */
--text-2xl: 1.5rem;     /* 24px */
--text-3xl: 1.875rem;   /* 30px */
--text-4xl: 2.25rem;    /* 36px */
--text-5xl: 3rem;        /* 48px */

/* Font Weights - Refined range */
--font-normal: 400;
--font-medium: 500;
--font-semibold: 600;
--font-bold: 700;

/* Line Heights - Elegant spacing */
--leading-tight: 1.2;
--leading-normal: 1.5;
--leading-relaxed: 1.65;

/* Letter Spacing - Refined */
--tracking-tight: -0.02em;
--tracking-normal: 0;
--tracking-wide: 0.02em;
```

### Typography Classes

```css
/* Hero heading */
.heading-hero {
  font-size: 3rem;
  font-weight: 600;
  line-height: 1.1;
  letter-spacing: -0.03em;
  color: var(--text-primary);
}

/* Section heading */
.heading-section {
  font-size: 1.875rem;
  font-weight: 600;
  line-height: 1.2;
  letter-spacing: -0.02em;
  color: var(--text-primary);
}

/* Card title */
.title-card {
  font-size: 1.125rem;
  font-weight: 600;
  line-height: 1.3;
  color: var(--text-primary);
}

/* Body text */
.body {
  font-size: 0.9375rem;
  font-weight: 400;
  line-height: 1.65;
  color: var(--text-primary);
}

/* Secondary text */
.text-secondary {
  font-size: 0.9375rem;
  color: var(--text-secondary);
  line-height: 1.6;
}

/* Numeric display */
.numeric {
  font-family: 'JetBrains Mono', monospace;
  font-weight: 500;
  font-variant-numeric: tabular-nums;
}
```

---

## Spacing System

Generous spacing that conveys luxury and confidence. Base unit: `4px`

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

/* Page layout */
--page-max-width: 1200px;
--content-max-width: 720px;
--sidebar-width: 280px;
```

### Layout Characteristics

- **Large whitespace** - Premium feel through generous margins
- **Centered focus** - Content often centered for emphasis
- **Grid rhythm** - Consistent 8px-based grid

---

## Border Radius

Refined, gentle curves. Not harsh, not bouncy.

```css
/* Border Radius - Elegant curves */
--radius-sm: 4px;
--radius-md: 8px;
--radius-lg: 12px;
--radius-xl: 16px;
--radius-2xl: 24px;
--radius-full: 9999px;
```

---

## Shadow System

Subtle, refined shadows with slight blue tint for depth

```css
/* Shadow Layers - Blue-tinted, refined */
--shadow-sm: 0 1px 2px rgba(26, 31, 54, 0.04);
--shadow-md: 0 4px 12px rgba(26, 31, 54, 0.08);
--shadow-lg: 0 8px 24px rgba(26, 31, 54, 0.12);
--shadow-xl: 0 16px 48px rgba(26, 31, 54, 0.16);

/* Elevated card shadow */
--shadow-card: 0 1px 3px rgba(26, 31, 54, 0.04), 0 4px 12px rgba(26, 31, 54, 0.06);

/* Button shadow */
--shadow-button: 0 1px 2px rgba(26, 31, 54, 0.04);
--shadow-button-hover: 0 4px 12px rgba(99, 91, 255, 0.25);

/* Focus ring */
--shadow-focus: 0 0 0 3px rgba(99, 91, 255, 0.15);
```

---

## Component Patterns

### Buttons

Premium buttons with subtle depth and refined interactions

```css
/* Primary Button */
.btn-primary {
  background: var(--accent-primary);
  color: white;
  font-weight: 500;
  font-size: 0.9375rem;
  padding: 12px 24px;
  border-radius: var(--radius-md);
  border: none;
  transition: all 200ms ease;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  box-shadow: var(--shadow-button);
}

.btn-primary:hover {
  background: var(--accent-hover);
  box-shadow: var(--shadow-button-hover);
  transform: translateY(-1px);
}

.btn-primary:active {
  transform: translateY(0);
  box-shadow: var(--shadow-sm);
}

/* Secondary Button */
.btn-secondary {
  background: white;
  color: var(--text-primary);
  font-weight: 500;
  font-size: 0.9375rem;
  padding: 12px 24px;
  border-radius: var(--radius-md);
  border: 1px solid var(--border-default);
  transition: all 200ms ease;
}

.btn-secondary:hover {
  background: var(--bg-secondary);
  border-color: var(--border-strong);
  box-shadow: var(--shadow-sm);
}

/* Outline Button - Subtle */
.btn-outline {
  background: transparent;
  color: var(--accent-primary);
  font-weight: 500;
  font-size: 0.9375rem;
  padding: 12px 24px;
  border-radius: var(--radius-md);
  border: 1.5px solid var(--accent-primary);
  transition: all 200ms ease;
}

.btn-outline:hover {
  background: var(--accent-subtle);
}

/* Ghost Button */
.btn-ghost {
  background: transparent;
  color: var(--text-secondary);
  font-weight: 500;
  font-size: 0.9375rem;
  padding: 12px 16px;
  border-radius: var(--radius-md);
  border: none;
  transition: all 200ms ease;
}

.btn-ghost:hover {
  background: var(--bg-secondary);
  color: var(--text-primary);
}

/* Large Button */
.btn-lg {
  font-size: 1rem;
  padding: 16px 32px;
  border-radius: var(--radius-lg);
}

/* Small Button */
.btn-sm {
  font-size: 0.8125rem;
  padding: 8px 16px;
}
```

### Input Fields

Clean, spacious inputs with subtle borders

```css
/* Input Base */
.input {
  background: white;
  border: 1px solid var(--border-default);
  border-radius: var(--radius-md);
  padding: 14px 16px;
  font-size: 0.9375rem;
  color: var(--text-primary);
  transition: all 200ms ease;
  outline: none;
  width: 100%;
}

.input::placeholder {
  color: var(--text-placeholder);
}

.input:hover {
  border-color: var(--border-strong);
}

.input:focus {
  border-color: var(--accent-primary);
  box-shadow: var(--shadow-focus);
}

/* Label */
.input-label {
  display: block;
  font-size: 0.875rem;
  font-weight: 500;
  color: var(--text-primary);
  margin-bottom: 6px;
}

/* Helper text */
.input-helper {
  font-size: 0.8125rem;
  color: var(--text-tertiary);
  margin-top: 6px;
}

/* Error state */
.input-error {
  border-color: var(--error);
}

.input-error:focus {
  box-shadow: 0 0 0 3px var(--error-bg);
}

/* Floating label input */
.input-floating {
  padding: 18px 16px 6px;
}

.input-floating-label {
  position: absolute;
  left: 16px;
  top: 50%;
  transform: translateY(-50%);
  font-size: 0.9375rem;
  color: var(--text-placeholder);
  pointer-events: none;
  transition: all 200ms ease;
}

.input-floating:focus + .input-floating-label,
.input-floating:not(:placeholder-shown) + .input-floating-label {
  top: 10px;
  font-size: 0.6875rem;
  color: var(--accent-primary);
}
```

### Cards

Refined cards with subtle shadows and generous padding

```css
/* Card - Clean and spacious */
.card {
  background: white;
  border: 1px solid var(--border-subtle);
  border-radius: var(--radius-xl);
  padding: 32px;
  transition: all 200ms ease;
}

.card:hover {
  box-shadow: var(--shadow-md);
  border-color: var(--border-default);
}

/* Card with icon */
.card-icon {
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--accent-subtle);
  border-radius: var(--radius-lg);
  color: var(--accent-primary);
  margin-bottom: 20px;
}

/* Feature card */
.card-feature {
  padding: 40px;
}

.card-feature-title {
  font-size: 1.25rem;
  font-weight: 600;
  color: var(--text-primary);
  margin-bottom: 12px;
}

.card-feature-description {
  font-size: 0.9375rem;
  color: var(--text-secondary);
  line-height: 1.6;
}

/* Pricing card */
.card-pricing {
  padding: 40px;
  text-align: center;
}

.card-pricing.highlighted {
  border-color: var(--accent-primary);
  box-shadow: var(--shadow-lg);
}
```

### Navigation

```css
/* Navbar */
.navbar {
  background: white;
  border-bottom: 1px solid var(--border-subtle);
  height: 64px;
  display: flex;
  align-items: center;
  padding: 0 24px;
}

/* Nav link */
.nav-link {
  font-size: 0.9375rem;
  font-weight: 500;
  color: var(--text-secondary);
  padding: 8px 16px;
  border-radius: var(--radius-md);
  transition: all 200ms ease;
}

.nav-link:hover {
  color: var(--text-primary);
  background: var(--bg-secondary);
}

.nav-link.active {
  color: var(--text-primary);
}

/* Sidebar nav */
.sidebar-nav {
  padding: 24px;
}

.sidebar-item {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 12px 16px;
  border-radius: var(--radius-md);
  color: var(--text-secondary);
  font-size: 0.9375rem;
  font-weight: 500;
  transition: all 200ms ease;
}

.sidebar-item:hover {
  background: var(--bg-secondary);
  color: var(--text-primary);
}

.sidebar-item.active {
  background: var(--accent-subtle);
  color: var(--accent-primary);
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
  color: var(--text-secondary);
}

/* Accent badge */
.badge-accent {
  background: var(--accent-subtle);
  color: var(--accent-primary);
}

/* Status badge */
.badge-success {
  background: var(--success-bg);
  color: var(--success);
}

.badge-warning {
  background: var(--warning-bg);
  color: var(--warning);
}

.badge-error {
  background: var(--error-bg);
  color: var(--error);
}
```

### Tables

```css
/* Table */
.table {
  width: 100%;
  border-collapse: collapse;
}

.table th {
  text-align: left;
  padding: 16px 20px;
  font-size: 0.75rem;
  font-weight: 600;
  color: var(--text-tertiary);
  text-transform: uppercase;
  letter-spacing: 0.05em;
  border-bottom: 1px solid var(--border-subtle);
}

.table td {
  padding: 20px;
  font-size: 0.9375rem;
  color: var(--text-primary);
  border-bottom: 1px solid var(--border-subtle);
}

.table tr:hover td {
  background: var(--bg-secondary);
}

/* Numeric table cell */
.table-numeric {
  font-family: 'JetBrains Mono', monospace;
  text-align: right;
}
```

---

## Motion & Animation

Smooth, refined, never jarring

```css
/* Timing */
--duration-fast: 150ms;
--duration-normal: 200ms;
--duration-slow: 300ms;

/* Easing - Smooth deceleration */
--ease-out: cubic-bezier(0.16, 1, 0.3, 1);
--ease-in-out: cubic-bezier(0.65, 0, 0.35, 1);

/* Hover lift */
.hover-lift {
  transition: all var(--duration-normal) var(--ease-out);
}

.hover-lift:hover {
  transform: translateY(-2px);
  box-shadow: var(--shadow-md);
}

/* Fade animations */
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

@keyframes slideUp {
  from {
    opacity: 0;
    transform: translateY(12px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fadeIn {
  animation: fadeIn var(--duration-normal) var(--ease-out);
}

.animate-slideUp {
  animation: slideUp var(--duration-slow) var(--ease-out);
}

/* Stagger animation */
.stagger-item {
  opacity: 0;
  transform: translateY(8px);
  animation: slideUp var(--duration-slow) var(--ease-out) forwards;
}

.stagger-item:nth-child(1) { animation-delay: 0ms; }
.stagger-item:nth-child(2) { animation-delay: 100ms; }
.stagger-item:nth-child(3) { animation-delay: 200ms; }
.stagger-item:nth-child(4) { animation-delay: 300ms; }
```

---

## Visual Principles

1. **Generous whitespace** - Luxury through breathing room
2. **Refined purple accent** - #635BFF is the signature
3. **Premium typography** - Large, readable, confident sizing
4. **Subtle shadows** - Blue-tinted for warmth and depth
5. **Smooth transitions** - 200ms+ for refined feel
6. **Clean surfaces** - White backgrounds, no clutter

---

## CSS Variables (Complete Set)

```css
:root {
  /* Colors */
  --bg-primary: #FFFFFF;
  --bg-secondary: #F6F9FC;
  --bg-tertiary: #F1F5F9;

  --text-primary: #1A1F36;
  --text-secondary: #697386;
  --text-tertiary: #8792A2;

  --border-subtle: #E3E8EE;
  --border-default: #CBD2DC;

  --accent-primary: #635BFF;
  --accent-hover: #7A73FF;
  --accent-subtle: rgba(99, 91, 255, 0.1);

  --success: #30D158;
  --warning: #FF9500;
  --error: #FF3B30;
  --info: #007AFF;

  /* Typography */
  --font-sans: 'Inter', -apple-system, sans-serif;
  --font-mono: 'JetBrains Mono', monospace;

  /* Spacing */
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-6: 24px;
  --space-8: 32px;
  --space-10: 40px;
  --space-12: 48px;
  --space-16: 64px;

  /* Border Radius */
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 12px;
  --radius-xl: 16px;
  --radius-2xl: 24px;
  --radius-full: 9999px;

  /* Shadows */
  --shadow-sm: 0 1px 2px rgba(26, 31, 54, 0.04);
  --shadow-md: 0 4px 12px rgba(26, 31, 54, 0.08);
  --shadow-lg: 0 8px 24px rgba(26, 31, 54, 0.12);
  --shadow-focus: 0 0 0 3px rgba(99, 91, 255, 0.15);

  /* Transitions */
  --duration-fast: 150ms;
  --duration-normal: 200ms;
  --ease-out: cubic-bezier(0.16, 1, 0.3, 1);
}
```

---

## Usage Tips

- Use generous padding (24px+) for cards and sections
- Stripe purple (#635BFF) is reserved for primary actions
- Large font sizes (15-17px base) for premium readability
- Subtle blue-tinted shadows for warmth
- Smooth 200ms transitions for refined feel
- Clean white backgrounds with subtle borders
- Monospace for numbers and financial data