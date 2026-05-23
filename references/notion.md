---
name: notion-style
description: "Notion风格 - 温暖极简创意风"
type: ui-style
---

# Notion Style Design System

## Overview

Notion风格是一种温暖、亲和的设计美学，融合了日式极简与创意工具的特质。它强调的是「家的感觉」——温暖但不花哨，有个性但不张扬。

**Brands**: Notion, Obsidian, Craft, Bear, Roam Research

**Mood**: 温暖、创意、包容、手工感、编辑感、文艺

---

## Color Palette

### Warm Neutrals (Primary Palette)

```css
/* Background Scale - Warm tinted */
--bg-primary: #FFFFFF;           /* 纯白背景 */
--bg-secondary: #F7F6F3;           /* 温暖米色 - 主背景 */
--bg-tertiary: #EFECE8;            /* 更暖的卡片背景 */
--bg-hover: #E8E6E1;               /* 悬浮态 */
--bg-active: #DDD9D2;             /* 激活态 */

/* Text Scale - Warm grays */
--text-primary: #37352F;          /* 主文字 - 温暖深棕 */
--text-secondary: #787774;         /* 次要文字 */
--text-tertiary: #9B9A97;         /* 弱化文字 */
--text-placeholder: #C5C4C0;      /* 占位符 */
--text-inverse: #FFFFFF;          /* 反色文字 */

/* Borders - Subtle warm */
--border-subtle: #E8E6E1;
--border-default: #D9D7D4;
--border-strong: #C4C2BD;

/* Accent - Notion Blue */
--accent-primary: #2EAADC;        /* Notion蓝 */
--accent-hover: #238AB7;          /* 悬浮态 */
--accent-subtle: rgba(46, 170, 220, 0.1);
--accent-text: #2EAADC;          /* 文字中的强调色 */

/* Semantic Colors - Softer saturation */
--success: #0F7B6C;              /* 更温暖的绿色 */
--success-bg: #EDF9F6;
--warning: #B9710C;              /* 琥珀色 */
--warning-bg: #FEF6E7;
--error: #EB5757;                /* 柔和红 */
--error-bg: #FEF2F2;
--info: #2EAADC;                 /* 同accent */
--info-bg: rgba(46, 170, 220, 0.08);

/* Cover Colors - Pastel palette for content */
--cover-red: #FFE2DD;
--cover-orange: #FFDECF;
--cover-yellow: #FFF3C4;
--cover-green: #D5F0E6;
--cover-blue: #C8E5FF;
--cover-purple: #E4DFFF;
--cover-pink: #FFD9E8;
--cover-gray: #E8E6E1;
```

### Dark Mode (Warm Dark)

```css
/* Dark mode with warm undertones */
--bg-primary-dark: #191919;
--bg-secondary-dark: #202020;
--bg-tertiary-dark: #262626;
--bg-hover-dark: #2D2D2D;

--text-primary-dark: #E8E6E1;
--text-secondary-dark: #9B9A97;
--text-tertiary-dark: #6B6966;

--border-subtle-dark: #333333;
--border-default-dark: #404040;

--accent-primary-dark: #2EAADC;
```

### Tailwind Config

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        bg: {
          primary: '#FFFFFF',
          secondary: '#F7F6F3',
          tertiary: '#EFECE8',
        },
        text: {
          primary: '#37352F',
          secondary: '#787774',
        },
        accent: {
          DEFAULT: '#2EAADC',
          hover: '#238AB7',
        },
        cover: {
          red: '#FFE2DD',
          orange: '#FFDECF',
          yellow: '#FFF3C4',
          green: '#D5F0E6',
          blue: '#C8E5FF',
          purple: '#E4DFFF',
          pink: '#FFD9E8',
        },
      },
    },
  },
}
```

---

## Typography

**Font Stack**:
- **Headings**: `Sega`, `Lora`, `Georgia` - 有个性但不张扬
- **Body**: `Inter` 已过时，换用 `Plus Jakarta Sans`, `DM Sans`, 或系统字体
- **Chinese**: `Source Han Sans`, `Noto Sans SC`, `-apple-system`

**Important**: Notion从不使用纯黑色文字，而是使用温暖的深棕色 `#37352F`

```css
/* Font Sizes - Slightly smaller than typical */
--text-xs: 0.75rem;     /* 12px */
--text-sm: 0.8125rem;   /* 13px */
--text-base: 0.9375rem; /* 15px - Notion偏大 */
--text-lg: 1rem;        /* 16px */
--text-xl: 1.125rem;   /* 18px */
--text-2xl: 1.375rem;   /* 22px */
--text-3xl: 1.75rem;    /* 28px */

/* Font Weights - Lighter feel */
--font-normal: 400;
--font-medium: 500;
--font-semibold: 600;

/* Line Heights - Relaxed for readability */
--leading-tight: 1.3;
--leading-normal: 1.5;
--leading-relaxed: 1.65;

/* Letter Spacing - Slight tracking */
--tracking-tight: -0.01em;
--tracking-normal: 0;
--tracking-wide: 0.02em;
```

### Typography Examples

```css
/* Page Title */
.page-title {
  font-size: 1.75rem;
  font-weight: 600;
  color: var(--text-primary);
  line-height: 1.3;
  letter-spacing: -0.01em;
}

/* Section Heading */
.heading {
  font-size: 1rem;
  font-weight: 600;
  color: var(--text-primary);
  line-height: 1.4;
}

/* Body Text */
.body {
  font-size: 0.9375rem;
  font-weight: 400;
  color: var(--text-primary);
  line-height: 1.65;
}

/* Secondary Text */
.secondary {
  font-size: 0.8125rem;
  color: var(--text-secondary);
  line-height: 1.5;
}
```

---

## Spacing System

Base unit: `4px` with a focus on generous whitespace

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
--space-24: 96px;

/* Notion-specific: Content padding */
--content-padding: 24px;
--content-max-width: 900px;
--sidebar-width: 240px;
```

### Layout Characteristics

- **Content max-width**: 900px for readability
- **Sidebar**: 240px fixed width
- **Generous margins**: 24px minimum around content
- **Breathing room**: Elements don't feel cramped

---

## Border Radius

Soft, subtle rounded corners

```css
/* Border Radius - Soft, not overly rounded */
--radius-sm: 4px;     /* 小元素 */
--radius-md: 6px;     /* 按钮、输入框 */
--radius-lg: 8px;     /* 卡片 */
--radius-xl: 12px;    /* 模态框 */
--radius-full: 9999px; /* 圆形 - 头像、图标背景 */

/* Tailwind */
.rounded-sm { border-radius: 4px; }
.rounded-md { border-radius: 6px; }
.rounded-lg { border-radius: 8px; }
.rounded-xl { border-radius: 12px; }
```

---

## Shadow System

Very subtle, warm-tinted shadows. Notion avoids harsh drop shadows.

```css
/* Shadow Layers - Subtle and warm */
--shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.04);
--shadow-md: 0 2px 8px rgba(0, 0, 0, 0.08);
--shadow-lg: 0 4px 16px rgba(0, 0, 0, 0.12);

/* Hover state shadow */
--shadow-hover: 0 2px 12px rgba(0, 0, 0, 0.1);

/* No harsh shadows - everything feels hand-crafted */
```

### Tailwind Shadow Classes

```css
.shadow-sm { box-shadow: 0 1px 2px rgba(0, 0, 0, 0.04); }
.shadow-md { box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08); }
.shadow-lg { box-shadow: 0 4px 16px rgba(0, 0, 0, 0.12); }
```

---

## Component Patterns

### Buttons

Notion buttons feel "ink-like" — they don't have hard boundaries but do have clear affordance

```css
/* Primary Button - Solid with warm feel */
.btn-primary {
  background: var(--text-primary);
  color: var(--bg-primary);
  font-weight: 500;
  font-size: 0.875rem;
  padding: 8px 16px;
  border-radius: var(--radius-md);
  border: none;
  transition: all 150ms ease;
}

.btn-primary:hover {
  opacity: 0.9;
}

/* Secondary Button - Transparent with border */
.btn-secondary {
  background: transparent;
  color: var(--text-primary);
  border: 1px solid var(--border-default);
  padding: 8px 16px;
  border-radius: var(--radius-md);
  font-weight: 500;
  font-size: 0.875rem;
  transition: all 150ms ease;
}

.btn-secondary:hover {
  background: var(--bg-secondary);
  border-color: var(--border-strong);
}

/* Ghost Button - Minimal, no border */
.btn-ghost {
  background: transparent;
  color: var(--text-secondary);
  border: none;
  padding: 8px 12px;
  border-radius: var(--radius-md);
  font-weight: 500;
  font-size: 0.875rem;
  transition: all 150ms ease;
}

.btn-ghost:hover {
  background: var(--bg-hover);
  color: var(--text-primary);
}

/* Icon Button */
.btn-icon {
  width: 32px;
  height: 32px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: var(--radius-md);
  background: transparent;
  color: var(--text-secondary);
  transition: all 150ms ease;
}

.btn-icon:hover {
  background: var(--bg-hover);
  color: var(--text-primary);
}
```

### Input Fields

Clean, minimal inputs with warm colors

```css
/* Input Base */
.input {
  background: var(--bg-primary);
  border: 1px solid var(--border-default);
  border-radius: var(--radius-md);
  padding: 10px 12px;
  font-size: 0.9375rem;
  color: var(--text-primary);
  transition: all 150ms ease;
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
  box-shadow: 0 0 0 3px var(--accent-subtle);
}

/* With icon */
.input-with-icon {
  padding-left: 40px;
}

.input-icon {
  position: absolute;
  left: 12px;
  top: 50%;
  transform: translateY(-50%);
  color: var(--text-tertiary);
  pointer-events: none;
}
```

### Cards

Notion cards feel like paper — subtle, warm, slightly raised

```css
/* Page Card */
.card {
  background: var(--bg-primary);
  border: 1px solid var(--border-subtle);
  border-radius: var(--radius-lg);
  padding: 16px;
  transition: all 200ms ease;
}

.card:hover {
  border-color: var(--border-default);
  box-shadow: var(--shadow-hover);
}

/* Gallery Card */
.card-gallery {
  background: var(--bg-secondary);
  border-radius: var(--radius-lg);
  overflow: hidden;
  transition: all 200ms ease;
}

.card-gallery:hover {
  transform: translateY(-2px);
  box-shadow: var(--shadow-md);
}

/* Cover Image */
.card-cover {
  width: 100%;
  aspect-ratio: 3/2;
  object-fit: cover;
}
```

### Tags & Badges

```css
/* Property Tag */
.property-tag {
  display: inline-flex;
  align-items: center;
  gap: 4px;
  padding: 2px 8px;
  font-size: 0.75rem;
  font-weight: 500;
  border-radius: var(--radius-sm);
  background: var(--bg-tertiary);
  color: var(--text-secondary);
}

/* Status Badge - with dot */
.status-badge {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 4px 10px;
  font-size: 0.8125rem;
  font-weight: 500;
  border-radius: var(--radius-full);
  background: var(--bg-tertiary);
  color: var(--text-primary);
}

.status-dot {
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: var(--text-tertiary);
}

.status-badge.success .status-dot { background: var(--success); }
.status-badge.warning .status-dot { background: var(--warning); }
.status-badge.error .status-dot { background: var(--error); }
```

### Navigation

```css
/* Sidebar */
.sidebar {
  width: var(--sidebar-width);
  background: var(--bg-secondary);
  border-right: 1px solid var(--border-subtle);
  height: 100vh;
  position: fixed;
  left: 0;
  top: 0;
  overflow-y: auto;
}

/* Workspace Header */
.workspace-header {
  padding: 12px 16px;
  border-bottom: 1px solid var(--border-subtle);
}

/* Nav Item */
.nav-item {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 8px 12px;
  margin: 2px 8px;
  border-radius: var(--radius-md);
  color: var(--text-secondary);
  font-size: 0.875rem;
  font-weight: 400;
  transition: all 150ms ease;
  cursor: pointer;
}

.nav-item:hover {
  background: var(--bg-hover);
  color: var(--text-primary);
}

.nav-item.active {
  background: var(--bg-hover);
  color: var(--text-primary);
  font-weight: 500;
}

/* Page Link in Sidebar */
.page-link {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 6px 12px;
  margin: 1px 8px;
  border-radius: var(--radius-md);
  color: var(--text-secondary);
  font-size: 0.875rem;
  transition: all 150ms ease;
  cursor: pointer;
}

.page-link:hover {
  background: var(--bg-hover);
}

.page-link-icon {
  width: 18px;
  height: 18px;
  opacity: 0.7;
}
```

### Blocks (Content Building Blocks)

```css
/* Page Block */
.block {
  padding: 4px 0;
  border-radius: var(--radius-sm);
  transition: all 150ms ease;
}

.block:hover {
  background: var(--bg-secondary);
}

/* To-do Block */
.todo-block {
  display: flex;
  align-items: flex-start;
  gap: 8px;
  padding: 4px 0;
}

.todo-checkbox {
  width: 16px;
  height: 16px;
  border: 1.5px solid var(--border-default);
  border-radius: 3px;
  cursor: pointer;
  flex-shrink: 0;
  margin-top: 2px;
}

.todo-block.checked .todo-checkbox {
  background: var(--accent-primary);
  border-color: var(--accent-primary);
}

.todo-block.checked .todo-text {
  text-decoration: line-through;
  color: var(--text-tertiary);
}

/* Toggle Block */
.toggle {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 4px 0;
  cursor: pointer;
}

.toggle-icon {
  width: 20px;
  height: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--text-tertiary);
  transition: transform 150ms ease;
}

.toggle.open .toggle-icon {
  transform: rotate(90deg);
}

/* Callout Block */
.callout {
  display: flex;
  gap: 12px;
  padding: 16px;
  background: var(--bg-secondary);
  border-radius: var(--radius-lg);
  border: 1px solid var(--border-subtle);
}

.callout-icon {
  font-size: 1.25rem;
  flex-shrink: 0;
}
```

---

## Motion & Animation

Subtle, organic movements. Nothing jarring.

```css
/* Timing */
--duration-fast: 100ms;
--duration-normal: 150ms;
--duration-slow: 200ms;
--duration-slower: 300ms;

/* Easing - Soft and natural */
--ease-out: cubic-bezier(0.25, 0.46, 0.45, 0.94);
--ease-in-out: cubic-bezier(0.4, 0, 0.2, 1);

/* Hover transforms */
.hover-lift:hover {
  transform: translateY(-1px);
}

.hover-scale:hover {
  transform: scale(1.02);
}

/* Fade animations */
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

@keyframes slideDown {
  from {
    opacity: 0;
    transform: translateY(-4px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes expandHeight {
  from { opacity: 0; height: 0; }
  to { opacity: 1; height: var(--content-height); }
}
```

---

## Visual Principles

1. **Warmth over perfection** — Slight imperfections feel hand-crafted
2. **Generous whitespace** — Content breathes; nothing feels cramped
3. **Paper-like textures** — Subtle warmth in backgrounds, not stark white
4. **Ink-like interactions** — Buttons feel like ink, not plastic
5. **Editorial hierarchy** — Clear typographic scale, like a well-designed document
6. **Functional color** — Color communicates meaning, not decoration

---

## CSS Variables (Complete Set)

```css
:root {
  /* Colors - Warm neutrals */
  --bg-primary: #FFFFFF;
  --bg-secondary: #F7F6F3;
  --bg-tertiary: #EFECE8;
  --bg-hover: #E8E6E1;
  --bg-active: #DDD9D2;

  --text-primary: #37352F;
  --text-secondary: #787774;
  --text-tertiary: #9B9A97;
  --text-placeholder: #C5C4C0;

  --border-subtle: #E8E6E1;
  --border-default: #D9D7D4;
  --border-strong: #C4C2BD;

  --accent-primary: #2EAADC;
  --accent-hover: #238AB7;
  --accent-subtle: rgba(46, 170, 220, 0.1);

  --success: #0F7B6C;
  --warning: #B9710C;
  --error: #EB5757;

  /* Typography */
  --font-sans: 'Plus Jakarta Sans', -apple-system, BlinkMacSystemFont, sans-serif;
  --font-serif: 'Lora', Georgia, serif;

  /* Spacing */
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-5: 20px;
  --space-6: 24px;
  --space-8: 32px;
  --space-10: 40px;
  --space-12: 48px;

  /* Border Radius */
  --radius-sm: 4px;
  --radius-md: 6px;
  --radius-lg: 8px;
  --radius-xl: 12px;
  --radius-full: 9999px;

  /* Shadows */
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.04);
  --shadow-md: 0 2px 8px rgba(0, 0, 0, 0.08);
  --shadow-lg: 0 4px 16px rgba(0, 0, 0, 0.12);

  /* Transitions */
  --duration-fast: 100ms;
  --duration-normal: 150ms;
  --duration-slow: 200ms;
  --ease-out: cubic-bezier(0.25, 0.46, 0.45, 0.94);
}
```

---

## Usage Tips

- Use `#37352F` instead of pure black for text
- Use `#F7F6F3` for page backgrounds instead of pure white
- Add subtle border colors like `#E8E6E1` to define boundaries
- Keep border-radius small (4-8px) — Notion is not "bubbly"
- Use warm grays and subtle shadows, never harsh blacks
- Let content breathe with generous padding and margins