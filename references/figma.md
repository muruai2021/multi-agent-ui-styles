---
name: figma-style
description: "Figma风格 - 工具美学B&W设计"
type: ui-style
---

# Figma Style Design System

## Overview

Figma风格是「工具美学」的极致体现——功能驱动、精确、克制的黑白为主的设计语言。它代表了专业设计工具的视觉哲学：让工具本身消失，用户关注的是内容而非界面。

**Brands**: Figma, Framer, Canva, Adobe XD, Miro

**Mood**: 专业、精确、工具感、高效、极简、功能驱动

---

## Color Palette

### Black & White (Primary Palette)

```css
/* Pure B&W Foundation */
--black: #000000;
--white: #FFFFFF;

/* Grayscale Scale - Cool undertones */
--gray-50: #FAFAFA;
--gray-100: #F5F5F5;
--gray-200: #E5E5E5;
--gray-300: #D4D4D4;
--gray-400: #A3A3A3;
--gray-500: #737373;
--gray-600: #525252;
--gray-700: #404040;
--gray-800: #262626;
--gray-900: #1A1A1A;

/* Background - Light mode first */
--bg-primary: #FFFFFF;
--bg-secondary: #F5F5F5;
--bg-tertiary: #EEEEEE;
--bg-elevated: #FFFFFF;        /* Elevated surfaces are white */
--bg-overlay: rgba(0, 0, 0, 0.5); /* Overlay for modals */

/* Text - High contrast */
--text-primary: #000000;
--text-secondary: #525252;
--text-tertiary: #737373;
--text-disabled: #A3A3A3;
--text-inverse: #FFFFFF;

/* Borders */
--border-light: #E5E5E5;
--border-medium: #D4D4D4;
--border-strong: #A3A3A3;

/* Figma Accent - Blue (used sparingly) */
--accent-primary: #A3A3FF;      /* Figma's signature lavender-blue */
--accent-hover: #8B8BFF;
--accent-subtle: rgba(163, 163, 255, 0.15);
--accent-muted: rgba(163, 163, 255, 0.4);

/* Semantic Colors */
--success: #14B878;
--warning: #FFB020;
--error: #F53D3D;
--info: #4D80FF;
```

### Dark Mode

```css
/* Tool aesthetic dark mode */
--bg-primary-dark: #1E1E1E;
--bg-secondary-dark: #252525;
--bg-tertiary-dark: #2D2D2D;
--bg-elevated-dark: #303030;

--text-primary-dark: #FFFFFF;
--text-secondary-dark: #A3A3A3;
--text-tertiary-dark: #737373;

--border-light-dark: #404040;
--border-medium-dark: #525252;
```

### Tailwind Config

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        black: '#000000',
        white: '#FFFFFF',
        gray: {
          50: '#FAFAFA',
          100: '#F5F5F5',
          200: '#E5E5E5',
          300: '#D4D4D4',
          400: '#A3A3A3',
          500: '#737373',
          600: '#525252',
          700: '#404040',
          800: '#262626',
          900: '#1A1A1A',
        },
        accent: {
          DEFAULT: '#A3A3FF',
          hover: '#8B8BFF',
        },
      },
      fontFamily: {
        sans: ['Inter', '-apple-system', 'sans-serif'],
        mono: ['JetBrains Mono', 'Fira Code', 'monospace'],
      },
    },
  },
}
```

---

## Typography

**Font Stack**:
- **Primary**: `Inter` (by Rasmus Andersson, used by Figma)
- **Mono**: `JetBrains Mono` for code and technical elements
- **Alternative**: `Satoshi`, `Plus Jakarta Sans`

**Important**: Figma uses Inter exclusively. The key is how it's used — tight tracking, precise weight contrast, generous line height.

```css
/* Type Scale */
--text-xs: 0.6875rem;   /* 11px - very small for dense UI */
--text-sm: 0.75rem;     /* 12px */
--text-base: 0.8125rem; /* 13px - Figma's base is small */
--text-lg: 0.9375rem;   /* 15px */
--text-xl: 1.125rem;    /* 18px */
--text-2xl: 1.375rem;   /* 22px */
--text-3xl: 1.75rem;    /* 28px */

/* Font Weights */
--font-light: 300;
--font-normal: 400;
--font-medium: 500;
--font-semibold: 600;
--font-bold: 700;

/* Line Heights - Tight for density */
--leading-tight: 1.2;
--leading-normal: 1.4;
--leading-relaxed: 1.5;

/* Letter Spacing */
--tracking-tight: -0.02em;
--tracking-normal: 0;
--tracking-wide: 0.04em;
```

### Typography Classes

```css
/* Labels - Uppercase, wide tracking */
.label {
  font-size: 0.6875rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.04em;
  color: var(--text-secondary);
}

/* Body text */
.body {
  font-size: 0.8125rem;
  font-weight: 400;
  color: var(--text-primary);
  line-height: 1.4;
}

/* Property text */
.property {
  font-size: 0.75rem;
  font-weight: 500;
  color: var(--text-secondary);
}
```

---

## Spacing System

Dense, efficient spacing for tool interfaces. Base unit: `4px`

```css
/* Spacing Scale - Tight */
--space-0: 0;
--space-0.5: 2px;
--space-1: 4px;
--space-1.5: 6px;
--space-2: 8px;
--space-2.5: 10px;
--space-3: 12px;
--space-4: 16px;
--space-5: 20px;
--space-6: 24px;
--space-8: 32px;

/* UI-specific */
--toolbar-height: 48px;
--panel-width: 240px;
--sidebar-width: 280px;
--property-pane-width: 280px;
```

### Panel Layout

```css
/* Toolbar */
.toolbar {
  height: var(--toolbar-height);
  background: var(--bg-primary);
  border-bottom: 1px solid var(--border-light);
  display: flex;
  align-items: center;
  padding: 0 8px;
  gap: 4px;
}

/* Panel */
.panel {
  background: var(--bg-primary);
  border-right: 1px solid var(--border-light);
  width: var(--panel-width);
  height: 100vh;
  overflow-y: auto;
}

.panel-section {
  padding: 12px;
  border-bottom: 1px solid var(--border-light);
}

.panel-section-title {
  font-size: 0.6875rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.04em;
  color: var(--text-tertiary);
  margin-bottom: 8px;
}
```

---

## Border Radius

Minimal, almost non-existent. Sharp corners dominate.

```css
/* Border Radius - Sharp, functional */
--radius-sm: 2px;     /* Micro elements */
--radius-md: 4px;     /* Buttons, inputs */
--radius-lg: 6px;     /* Cards, panels */
--radius-xl: 8px;     /* Modals */

/* No pill buttons - tool UIs avoid full rounding */
--radius-full: 9999px; /* Only for avatars, badges */
```

### Tailwind Classes

```css
.rounded-sm { border-radius: 2px; }
.rounded-md { border-radius: 4px; }
.rounded-lg { border-radius: 6px; }
.rounded-xl { border-radius: 8px; }
```

---

## Shadow System

Sharp, defined shadows. Not soft or diffused.

```css
/* Sharp Shadows */
--shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.1);
--shadow-md: 0 2px 8px rgba(0, 0, 0, 0.12);
--shadow-lg: 0 4px 16px rgba(0, 0, 0, 0.15);
--shadow-xl: 0 8px 32px rgba(0, 0, 0, 0.2);

/* Focus shadow - crisp outline style */
--shadow-focus: 0 0 0 2px var(--accent-primary);

/* Selection highlight */
--shadow-selection: 0 0 0 1px var(--accent-primary);
```

### Tailwind Classes

```css
.shadow-sm { box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1); }
.shadow-md { box-shadow: 0 2px 8px rgba(0, 0, 0, 0.12); }
.shadow-lg { box-shadow: 0 4px 16px rgba(0, 0, 0, 0.15); }
.shadow-xl { box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2); }
```

---

## Component Patterns

### Buttons

Functional, sharp, no-nonsense buttons

```css
/* Primary Button - Black */
.btn-primary {
  background: var(--black);
  color: var(--white);
  font-weight: 500;
  font-size: 0.75rem;
  padding: 6px 12px;
  border-radius: var(--radius-md);
  border: none;
  transition: all 100ms ease;
  display: inline-flex;
  align-items: center;
  gap: 6px;
}

.btn-primary:hover {
  background: var(--gray-800);
}

.btn-primary:active {
  background: var(--gray-900);
}

/* Secondary Button - Outline */
.btn-secondary {
  background: transparent;
  color: var(--text-primary);
  border: 1px solid var(--border-medium);
  padding: 6px 12px;
  border-radius: var(--radius-md);
  font-weight: 500;
  font-size: 0.75rem;
  transition: all 100ms ease;
}

.btn-secondary:hover {
  background: var(--gray-50);
  border-color: var(--gray-400);
}

/* Ghost Button - No border */
.btn-ghost {
  background: transparent;
  color: var(--text-secondary);
  border: none;
  padding: 6px 10px;
  border-radius: var(--radius-md);
  font-weight: 500;
  font-size: 0.75rem;
  transition: all 100ms ease;
}

.btn-ghost:hover {
  background: var(--gray-100);
  color: var(--text-primary);
}

/* Icon Button */
.btn-icon {
  width: 28px;
  height: 28px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: var(--radius-md);
  background: transparent;
  color: var(--text-secondary);
  transition: all 100ms ease;
}

.btn-icon:hover {
  background: var(--gray-100);
  color: var(--text-primary);
}

.btn-icon.active {
  background: var(--gray-200);
  color: var(--text-primary);
}
```

### Input Fields

Dense, precise inputs

```css
/* Input Base */
.input {
  background: var(--bg-primary);
  border: 1px solid var(--border-light);
  border-radius: var(--radius-md);
  padding: 6px 10px;
  font-size: 0.75rem;
  color: var(--text-primary);
  transition: all 100ms ease;
  outline: none;
  width: 100%;
  height: 28px;
}

.input::placeholder {
  color: var(--text-disabled);
}

.input:hover {
  border-color: var(--border-medium);
}

.input:focus {
  border-color: var(--black);
  box-shadow: var(--shadow-focus);
}

/* Textarea */
.textarea {
  min-height: 60px;
  height: auto;
  resize: vertical;
}

/* Select */
.select {
  appearance: none;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 24 24' fill='none' stroke='%23737373' stroke-width='2'%3E%3Cpath d='M6 9l6 6 6-6'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right 10px center;
  padding-right: 28px;
}

/* With icon */
.input-icon-left {
  padding-left: 28px;
}

.input-icon {
  position: absolute;
  left: 8px;
  top: 50%;
  transform: translateY(-50%);
  color: var(--text-tertiary);
  pointer-events: none;
}
```

### Panels & Sections

```css
/* Panel container */
.panel {
  background: var(--bg-primary);
  width: var(--panel-width);
  height: 100vh;
  overflow-y: auto;
  overflow-x: hidden;
}

/* Section divider */
.section {
  padding: 12px;
  border-bottom: 1px solid var(--border-light);
}

.section-title {
  font-size: 0.6875rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.04em;
  color: var(--text-tertiary);
  margin-bottom: 8px;
}

/* Property row */
.property-row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 6px 0;
  min-height: 28px;
}

.property-label {
  font-size: 0.75rem;
  color: var(--text-secondary);
}

.property-value {
  font-size: 0.75rem;
  color: var(--text-primary);
  font-weight: 500;
}

/* Divider */
.divider {
  height: 1px;
  background: var(--border-light);
  margin: 12px 0;
}

/* Spacer */
.spacer {
  height: 12px;
}
```

### Toolbar

```css
/* Toolbar */
.toolbar {
  height: var(--toolbar-height);
  background: var(--bg-primary);
  border-bottom: 1px solid var(--border-light);
  display: flex;
  align-items: center;
  padding: 0 8px;
  gap: 2px;
}

/* Toolbar Group */
.toolbar-group {
  display: flex;
  align-items: center;
  gap: 2px;
  padding: 0 4px;
  border-right: 1px solid var(--border-light);
}

.toolbar-group:last-child {
  border-right: none;
}

/* Toolbar Button */
.toolbar-btn {
  width: 28px;
  height: 28px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: var(--radius-md);
  background: transparent;
  color: var(--text-secondary);
  transition: all 100ms ease;
}

.toolbar-btn:hover {
  background: var(--gray-100);
  color: var(--text-primary);
}

.toolbar-btn.active {
  background: var(--gray-200);
  color: var(--text-primary);
}

/* Toolbar Label */
.toolbar-label {
  font-size: 0.6875rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.04em;
  color: var(--text-tertiary);
  padding: 0 8px;
}
```

### Layers / Hierarchy

```css
/* Layer Row */
.layer-row {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 4px 8px;
  border-radius: var(--radius-md);
  cursor: pointer;
  transition: all 100ms ease;
}

.layer-row:hover {
  background: var(--gray-100);
}

.layer-row.selected {
  background: var(--accent-subtle);
}

.layer-row.selected:hover {
  background: rgba(163, 163, 255, 0.25);
}

/* Layer Thumbnail */
.layer-thumb {
  width: 24px;
  height: 24px;
  border-radius: var(--radius-sm);
  background: var(--gray-200);
  border: 1px solid var(--border-light);
  flex-shrink: 0;
}

/* Layer Name */
.layer-name {
  font-size: 0.75rem;
  color: var(--text-primary);
  flex: 1;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

/* Layer Meta */
.layer-meta {
  font-size: 0.6875rem;
  color: var(--text-tertiary);
}
```

### Context Menus

```css
/* Context Menu */
.context-menu {
  background: var(--bg-primary);
  border: 1px solid var(--border-light);
  border-radius: var(--radius-lg);
  padding: 4px;
  min-width: 180px;
  box-shadow: var(--shadow-lg);
}

.context-menu-item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 6px 10px;
  border-radius: var(--radius-md);
  cursor: pointer;
  transition: all 100ms ease;
}

.context-menu-item:hover {
  background: var(--gray-100);
}

.context-menu-label {
  font-size: 0.75rem;
  color: var(--text-primary);
}

.context-menu-shortcut {
  font-size: 0.6875rem;
  color: var(--text-tertiary);
}

/* Separator */
.context-menu-separator {
  height: 1px;
  background: var(--border-light);
  margin: 4px 0;
}
```

---

## Motion & Animation

Minimal, functional, fast. Tools prioritize speed over flourish.

```css
/* Timing */
--duration-fast: 50ms;     /* Almost instant */
--duration-normal: 100ms; /* Quick */
--duration-slow: 150ms;   /* Noticeable */

/* Easing - Linear for precision */
--ease-linear: linear;
--ease-out: cubic-bezier(0.16, 1, 0.3, 1);

/* Transitions */
.transition-fast {
  transition: all var(--duration-fast) var(--ease-out);
}

.transition-normal {
  transition: all var(--duration-normal) var(--ease-out);
}
```

---

## Visual Principles

1. **Black and white first** - Color is accent, not foundation
2. **Density over whitespace** - Compact UI, more information
3. **Function over form** - Every element serves a purpose
4. **Sharp edges** - Minimal border-radius, precise lines
5. **High contrast** - Clear hierarchy, readable at small sizes
6. **Tool-like** - Interface should feel like precision instrument

---

## CSS Variables (Complete Set)

```css
:root {
  /* Colors */
  --black: #000000;
  --white: #FFFFFF;

  --gray-50: #FAFAFA;
  --gray-100: #F5F5F5;
  --gray-200: #E5E5E5;
  --gray-300: #D4D4D4;
  --gray-400: #A3A3A3;
  --gray-500: #737373;
  --gray-600: #525252;
  --gray-700: #404040;
  --gray-800: #262626;
  --gray-900: #1A1A1A;

  --bg-primary: #FFFFFF;
  --bg-secondary: #F5F5F5;
  --bg-tertiary: #EEEEEE;

  --text-primary: #000000;
  --text-secondary: #525252;
  --text-tertiary: #737373;
  --text-disabled: #A3A3A3;

  --border-light: #E5E5E5;
  --border-medium: #D4D4D4;
  --border-strong: #A3A3A3;

  --accent-primary: #A3A3FF;
  --accent-hover: #8B8BFF;
  --accent-subtle: rgba(163, 163, 255, 0.15);

  /* Typography */
  --font-sans: 'Inter', -apple-system, sans-serif;
  --font-mono: 'JetBrains Mono', 'Fira Code', monospace;

  /* Spacing */
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-6: 24px;
  --space-8: 32px;

  /* Border Radius */
  --radius-sm: 2px;
  --radius-md: 4px;
  --radius-lg: 6px;
  --radius-xl: 8px;

  /* Shadows */
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.1);
  --shadow-md: 0 2px 8px rgba(0, 0, 0, 0.12);
  --shadow-lg: 0 4px 16px rgba(0, 0, 0, 0.15);
  --shadow-focus: 0 0 0 2px var(--accent-primary);

  /* Transitions */
  --duration-fast: 50ms;
  --duration-normal: 100ms;
  --ease-out: cubic-bezier(0.16, 1, 0.3, 1);
}
```

---

## Usage Tips

- Use small font sizes (11-13px) for dense tool UI
- Keep border-radius minimal (2-4px)
- Use black (#000) and white (#FFF) as primary colors
- Add accent color sparingly (only for selection and focus states)
- Compact spacing with 4-8px gaps between related items
- Use uppercase labels with wide tracking for section titles
- Prioritize information density over generous whitespace