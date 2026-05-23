---
name: ibm-style
description: "IBM风格 - 企业规范Carbon设计系统"
type: ui-style
---

# IBM Style Design System (Carbon)

## Overview

IBM风格是「企业规范」设计的标准——它源于Carbon Design System，代表了严谨、可访问、规模化的大企业设计哲学。每个决策都有明确的理由，每个组件都遵循一致的规范。

**Brands**: IBM, Oracle, SAP, Siemens, Microsoft Enterprise

**Mood**: 专业、规范、可访问、规模化、企业级、可靠、严谨

---

## Color Palette

### IBM Carbon Colors

```css
/* Gray Scale - IBM's signature cool grays */
--gray-100: #161616;
--gray-90: #262626;
--gray-80: #393939;
--gray-70: #525252;
--gray-60: #6F6F6F;
--gray-50: #8D8D8D;
--gray-40: #A8A8A8;
--gray-30: #C6C6C6;
--gray-20: #E0E0E0;
--gray-10: #F4F4F4;
--gray-05: #FAFCF8;
--gray-04: #FCFCFE;
--gray-03: #FFFFFF;

/* Background */
--bg-primary: #161616;
--bg-secondary: #262626;
--bg-tertiary: #393939;
--bg-elevated: #525252;

/* Text */
--text-primary: #F4F4F4;
--text-secondary: #C6C6C6;
--text-tertiary: #8D8D8D;
--text-placeholder: #6F6F6F;
--text-inverse: #161616;

/* Interactive Blue - IBM Blue */
--accent-primary: #0F62FE;
--accent-hover: #0353E9;
--accent-subtle: rgba(15, 98, 254, 0.2);
--accent-muted: rgba(15, 98, 254, 0.4);

/* Support Colors */
--support-error: #DA1E28;
--support-warning: #F1C21B;
--support-success: #198038;
--support-info: #0043CE;

/* Interactive States */
--hover-ui: rgba(255, 255, 255, 0.08);
--active-ui: rgba(255, 255, 255, 0.16);
--focus-ui: #0F62FE;
```

### Light Mode

```css
--bg-primary-light: #FFFFFF;
--bg-secondary-light: #F4F4F4;
--bg-tertiary-light: #E0E0E0;
--text-primary-light: #161616;
--text-secondary-light: #525252;
--text-tertiary-light: #8D8D8D;
```

### Tailwind Config

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        carbon: {
          blue: '#0F62FE',
          gray: {
            100: '#161616',
            90: '#262626',
            80: '#393939',
            70: '#525252',
            60: '#6F6F6F',
            50: '#8D8D8D',
            30: '#C6C6C6',
            10: '#F4F4F4',
          },
        },
        ui: {
          hover: 'rgba(255, 255, 255, 0.08)',
          active: 'rgba(255, 255, 255, 0.16)',
        },
      },
      fontFamily: {
        sans: ['IBM Plex Sans', '-apple-system', 'sans-serif'],
        mono: ['IBM Plex Mono', 'monospace'],
      },
    },
  },
}
```

---

## Typography

**Font Stack**:
- **Primary**: `IBM Plex Sans` - IBM's signature typeface
- **Mono**: `IBM Plex Mono` - For code and data
- **Fallback**: `-apple-system`, `system-ui`

**Important**: IBM's Carbon uses a strict type system with 5 levels. Font loading should use `font-display: swap` for performance.

```css
/* Type Scale - Carbon productive */
--text-01: 0.75rem;    /* 12px - labels, metadata */
--text-02: 0.875rem;   /* 14px - body, body small */
--text-03: 1rem;       /* 16px - body large */
--text-04: 1.25rem;    /* 20px - headings */
--text-05: 1.5rem;     /* 24px - headings */
--text-06: 1.75rem;    /* 28px - headings */
--text-07: 2rem;       /* 32px - display */
--text-08: 2.625rem;   /* 42px - display */
--text-09: 3rem;        /* 48px - display */

/* Carbon naming convention */
--text-label-01: 0.75rem;
--text-label-02: 0.875rem;
--text-body-01: 0.875rem;
--text-body-02: 1rem;
--text-heading-01: 1.25rem;
--text-heading-02: 1.5rem;
--text-heading-03: 1.75rem;
--text-display-01: 2rem;
--text-display-02: 2.625rem;
--text-display-03: 3rem;

/* Font Weights */
--font-light: 300;
--font-regular: 400;
--font-medium: 500;
--font-semibold: 600;
--font-bold: 700;

/* Line Heights */
--leading-01: 1;
--leading-02: 1.25;
--leading-03: 1.4;
--leading-04: 1.5;

/* Letter Spacing */
--tracking-01: 0.32px;
--tracking-02: 0.32px;
--tracking-03: 0.32px;
--tracking-04: 0.64px;
```

### Typography Classes

```css
/* Productivity label */
.label-01 {
  font-size: 0.75rem;
  font-weight: 500;
  letter-spacing: 0.32px;
  color: var(--text-secondary);
}

/* Body text */
.body-01 {
  font-size: 0.875rem;
  font-weight: 400;
  color: var(--text-primary);
  line-height: 1.4;
}

/* Heading */
.heading-03 {
  font-size: 1.75rem;
  font-weight: 600;
  color: var(--text-primary);
  line-height: 1.25;
}

/* Code / Mono */
.mono {
  font-family: var(--font-mono);
  font-size: 0.875rem;
}
```

---

## Spacing System

8px grid system. Base unit: `8px`

```css
/* Spacing Scale - 8px grid */
--space-01: 2px;
--space-02: 4px;
--space-03: 8px;
--space-04: 12px;
--space-05: 16px;
--space-06: 24px;
--space-07: 32px;
--space-08: 40px;
--space-09: 48px;
--space-10: 64px;
--space-11: 80px;
--space-12: 96px;
--space-13: 128px;

/* Layout */
--container-sm: 576px;
--container-md: 768px;
--container-lg: 1060px;
--container-xl: 1312px;
--container-max: 1584px;
```

---

## Border Radius

Minimal, Carbon-style. Use sparingly.

```css
/* Border Radius - Carbon style */
--radius-sm: 0;
--radius-md: 0;
--radius-lg: 4px;
--radius-xl: 4px;
--radius-full: 9999px;

/* IBM Carbon: Nearly flat, only 4px max */
```

---

## Shadow System

IBM uses z-index layers instead of shadows for elevation

```css
/* Instead of shadows, IBM uses pseudo-layers */

/* Interactive element elevation */
--elevation-overlay: 9999;
--elevation-sticky: 1020;
--elevation-dropdown: 1060;
--elevation-modal: 1080;
--elevation-tooltip: 1090;

/* For components that need shadow */
--shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.3);
--shadow-md: 0 2px 6px rgba(0, 0, 0, 0.3);
--shadow-lg: 0 4px 12px rgba(0, 0, 0, 0.4);
```

---

## Component Patterns

### Buttons

IBM Carbon buttons - flat, minimal

```css
/* Primary Button */
.btn-primary {
  background: var(--accent-primary);
  color: white;
  font-weight: 500;
  font-size: 0.875rem;
  padding: 12px 24px;
  border-radius: 0;
  border: none;
  min-width: 120px;
  transition: all 150ms ease;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
}

.btn-primary:hover {
  background: var(--accent-hover);
}

.btn-primary:active {
  background: #002D9C;
}

/* Secondary Button */
.btn-secondary {
  background: transparent;
  color: var(--accent-primary);
  font-weight: 500;
  font-size: 0.875rem;
  padding: 12px 24px;
  border-radius: 0;
  border: 1px solid var(--accent-primary);
  min-width: 120px;
  transition: all 150ms ease;
}

.btn-secondary:hover {
  background: var(--accent-subtle);
}

/* Ghost Button */
.btn-ghost {
  background: transparent;
  color: var(--text-primary);
  font-weight: 500;
  font-size: 0.875rem;
  padding: 12px 24px;
  border-radius: 0;
  border: none;
  transition: all 150ms ease;
}

.btn-ghost:hover {
  background: var(--hover-ui);
}

.btn-ghost:active {
  background: var(--active-ui);
}

/* Danger Button */
.btn-danger {
  background: var(--support-error);
  color: white;
  font-weight: 500;
  font-size: 0.875rem;
  padding: 12px 24px;
  border-radius: 0;
  border: none;
  min-width: 120px;
  transition: all 150ms ease;
}

.btn-danger:hover {
  background: #A82027;
}

/* Icon Button */
.btn-icon {
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: transparent;
  color: var(--text-secondary);
  border-radius: 0;
  border: none;
  transition: all 150ms ease;
}

.btn-icon:hover {
  background: var(--hover-ui);
  color: var(--text-primary);
}

/* Disabled state */
.btn:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}
```

### Input Fields

```css
/* Input */
.input {
  background: var(--bg-secondary);
  border: none;
  border-bottom: 1px solid var(--gray-70);
  padding: 12px 16px;
  font-size: 0.875rem;
  color: var(--text-primary);
  transition: all 150ms ease;
  outline: none;
  width: 100%;
}

.input::placeholder {
  color: var(--text-placeholder);
}

.input:focus {
  border-bottom-color: var(--accent-primary);
  background: var(--bg-tertiary);
}

/* Label above input */
.input-label {
  display: block;
  font-size: 0.75rem;
  font-weight: 500;
  color: var(--text-secondary);
  margin-bottom: 8px;
  letter-spacing: 0.32px;
}

/* Helper text */
.input-helper {
  font-size: 0.75rem;
  color: var(--text-tertiary);
  margin-top: 8px;
}

/* Error state */
.input-error {
  border-bottom-color: var(--support-error);
}

.input-error + .input-label {
  color: var(--support-error);
}

/* Textarea */
.textarea {
  min-height: 100px;
  resize: vertical;
  background: var(--bg-secondary);
  border: none;
  border-bottom: 1px solid var(--gray-70);
  padding: 12px 16px;
  font-size: 0.875rem;
  color: var(--text-primary);
  transition: all 150ms ease;
  outline: none;
  width: 100%;
}

.textarea:focus {
  border-bottom-color: var(--accent-primary);
}

/* Select */
.select {
  appearance: none;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='16' height='16' viewBox='0 0 24 24' fill='none' stroke='%238D8D8D' stroke-width='2'%3E%3Cpath d='M6 9l6 6 6-6'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right 16px center;
  padding-right: 40px;
  background-color: var(--bg-secondary);
  border: none;
  border-bottom: 1px solid var(--gray-70);
  padding: 12px 40px 12px 16px;
  font-size: 0.875rem;
  color: var(--text-primary);
  width: 100%;
}
```

### Data Table

```css
/* Table */
.table {
  width: 100%;
  border-collapse: collapse;
  background: var(--bg-secondary);
}

.table th {
  text-align: left;
  padding: 16px;
  font-size: 0.75rem;
  font-weight: 600;
  color: var(--text-secondary);
  border-bottom: 1px solid var(--gray-70);
  letter-spacing: 0.32px;
}

.table td {
  padding: 16px;
  font-size: 0.875rem;
  color: var(--text-primary);
  border-bottom: 1px solid var(--gray-90);
}

.table tr:hover td {
  background: var(--hover-ui);
}

/* Table toolbar */
.table-toolbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 16px;
  background: var(--bg-secondary);
  border-bottom: 1px solid var(--gray-90);
}

.table-toolbar-title {
  font-size: 0.875rem;
  font-weight: 600;
  color: var(--text-primary);
}
```

### Tile / Card

```css
/* Tile */
.tile {
  background: var(--bg-secondary);
  padding: 16px;
  border-bottom: 1px solid var(--gray-90);
  transition: all 150ms ease;
  cursor: pointer;
}

.tile:hover {
  background: var(--bg-tertiary);
}

.tile-title {
  font-size: 0.875rem;
  font-weight: 500;
  color: var(--text-primary);
  margin-bottom: 4px;
}

.tile-description {
  font-size: 0.75rem;
  color: var(--text-secondary);
}

/* Clickable tile */
.tile-clickable {
  display: block;
  text-decoration: none;
  color: inherit;
}

.tile-clickable:hover {
  background: var(--bg-tertiary);
}

/* Selected tile */
.tile.selected {
  background: var(--accent-subtle);
  border-left: 3px solid var(--accent-primary);
}
```

### Navigation

```css
/* Header */
.header {
  height: 48px;
  background: var(--bg-primary);
  border-bottom: 1px solid var(--gray-90);
  display: flex;
  align-items: center;
  padding: 0 16px;
}

/* Header nav */
.header-nav {
  display: flex;
  align-items: center;
  height: 100%;
}

.header-nav-item {
  padding: 0 16px;
  height: 100%;
  display: flex;
  align-items: center;
  color: var(--text-secondary);
  font-size: 0.875rem;
  font-weight: 500;
  border-bottom: 3px solid transparent;
  transition: all 150ms ease;
}

.header-nav-item:hover {
  color: var(--text-primary);
  background: var(--hover-ui);
}

.header-nav-item.active {
  color: var(--text-primary);
  border-bottom-color: var(--accent-primary);
}

/* Side panel */
.side-panel {
  width: 256px;
  background: var(--bg-secondary);
  border-right: 1px solid var(--gray-90);
  height: 100vh;
  overflow-y: auto;
}

.side-panel-section {
  padding: 16px;
  border-bottom: 1px solid var(--gray-90);
}

.side-panel-title {
  font-size: 0.75rem;
  font-weight: 600;
  color: var(--text-secondary);
  text-transform: uppercase;
  letter-spacing: 0.64px;
  margin-bottom: 12px;
}

/* Side nav item */
.side-nav-item {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 12px 16px;
  color: var(--text-secondary);
  font-size: 0.875rem;
  transition: all 150ms ease;
  cursor: pointer;
}

.side-nav-item:hover {
  background: var(--hover-ui);
  color: var(--text-primary);
}

.side-nav-item.active {
  background: var(--accent-subtle);
  color: var(--accent-primary);
}

.side-nav-item svg {
  width: 20px;
  height: 20px;
}
```

### Tags

```css
/* Tag */
.tag {
  display: inline-flex;
  align-items: center;
  gap: 4px;
  padding: 4px 10px;
  font-size: 0.75rem;
  font-weight: 500;
  background: var(--bg-tertiary);
  color: var(--text-secondary);
  border-radius: 0;
}

.tag-blue {
  background: var(--accent-subtle);
  color: var(--accent-primary);
}

.tag-green {
  background: rgba(25, 128, 56, 0.2);
  color: #42BE65;
}

.tag-red {
  background: rgba(218, 30, 40, 0.2);
  color: #FA4D56;
}

.tag-yellow {
  background: rgba(241, 194, 27, 0.2);
  color: #F1C21B;
}
```

---

## Motion & Animation

IBM Carbon motion - quick, purposeful, accessible

```css
/* Timing */
--duration-fast: 70ms;
--duration-normal: 110ms;
--duration-slow: 170ms;
--duration-slower: 240ms;

/* Easing */
--ease-standard: cubic-bezier(0.4, 0.14, 0.3, 1);
--ease-entrance: cubic-bezier(0, 0, 0.3, 1);
--ease-exit: cubic-bezier(0.4, 0.14, 1, 1);

/* IBM's standard easing */
--ease-productive: cubic-bezier(0.4, 0.14, 0.3, 1);
--ease-expressive: cubic-bezier(0, 0, 0.3, 1);

/* Transition */
.transition-fast {
  transition: all var(--duration-fast) var(--ease-standard);
}

.transition-normal {
  transition: all var(--duration-normal) var(--ease-standard);
}
```

---

## Visual Principles

1. **Strict grid** - 8px grid system, everything aligned
2. **Flat design** - No shadows, use z-index for elevation
3. **Minimal radius** - Nearly zero border-radius (4px max)
4. **Functional color** - Blue for interactive, semantic for status
5. **IBM Plex fonts** - Monospace for data, sans for UI
6. **Accessibility first** - WCAG AA minimum, IBM's standard

---

## CSS Variables (Complete Set)

```css
:root {
  /* Colors */
  --gray-100: #161616;
  --gray-90: #262626;
  --gray-80: #393939;
  --gray-70: #525252;
  --gray-60: #6F6F6F;
  --gray-50: #8D8D8D;
  --gray-40: #A8A8A8;
  --gray-30: #C6C6C6;
  --gray-20: #E0E0E0;
  --gray-10: #F4F4F4;

  --bg-primary: #161616;
  --bg-secondary: #262626;
  --bg-tertiary: #393939;

  --text-primary: #F4F4F4;
  --text-secondary: #C6C6C6;
  --text-tertiary: #8D8D8D;

  --accent-primary: #0F62FE;
  --accent-hover: #0353E9;
  --accent-subtle: rgba(15, 98, 254, 0.2);

  --support-error: #DA1E28;
  --support-warning: #F1C21B;
  --support-success: #198038;
  --support-info: #0043CE;

  --hover-ui: rgba(255, 255, 255, 0.08);
  --active-ui: rgba(255, 255, 255, 0.16);

  /* Typography */
  --font-sans: 'IBM Plex Sans', -apple-system, sans-serif;
  --font-mono: 'IBM Plex Mono', monospace;

  /* Spacing - 8px grid */
  --space-03: 8px;
  --space-05: 16px;
  --space-06: 24px;
  --space-07: 32px;
  --space-08: 40px;
  --space-09: 48px;
  --space-10: 64px;

  /* Border Radius */
  --radius-lg: 4px;
  --radius-xl: 4px;

  /* Transitions */
  --duration-fast: 70ms;
  --duration-normal: 110ms;
  --ease-standard: cubic-bezier(0.4, 0.14, 0.3, 1);
}
```

---

## Usage Tips

- Use 8px grid for all spacing
- IBM Plex Sans/Mono fonts for consistency
- Minimal border-radius (4px max)
- Blue (#0F62FE) for interactive elements
- Flat design - no shadows, use z-index
- Quick transitions (70-110ms)
- Strict functional color usage