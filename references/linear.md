---
name: linear-style
description: "Linear风格 - 极简深色科技风"
type: ui-style
---

# Linear Style Design System

## Overview

Linear风格是一种极简深色设计美学，专注于科技感和精确感。它代表了新一代SaaS产品的设计方向，以克制、内敛、功能驱动为核心原则。

**Brands**: Linear, Vercel, Raycast, Loom, Pitch

**Mood**: 精准、高端、沉浸式、高效、专业、克制

---

## Color Palette

### Dark Mode (Primary)

```css
/* Background Scale */
--bg-primary: #0D0D0F;      /* 最深背景 - 主页背景 */
--bg-secondary: #141416;     /* 卡片背景 */
--bg-tertiary: #1A1A1D;      /* 悬浮背景 */
--bg-elevated: #222225;      /* 模态框、下拉菜单 */

/* Surface & Borders */
--border-subtle: #2A2A2E;     /* 细分边界 */
--border-default: #3A3A3F;   /* 默认边界 */
--border-strong: #52525B;    /* 强调边界 */

/* Text Hierarchy */
--text-primary: #EDEDEF;     /* 主要文字 - 高对比度 */
--text-secondary: #8A8A8E;   /* 次要文字 - 辅助信息 */
--text-tertiary: #5C5C5F;    /* 弱化文字 - 禁用状态 */
--text-inverse: #0D0D0F;     /* 反色文字 */

/* Accent - Subtle Purple */
--accent-primary: #8B5CF6;   /* 主强调色 */
--accent-hover: #A78BFA;     /* 悬浮态 */
--accent-subtle: rgba(139, 92, 246, 0.15); /* 强调背景 */
--accent-muted: rgba(139, 92, 246, 0.4);   /* 中度强调 */

/* Semantic Colors */
--success: #10B981;          /* 成功状态 */
--success-subtle: rgba(16, 185, 129, 0.15);
--warning: #F59E0B;          /* 警告状态 */
--warning-subtle: rgba(245, 158, 11, 0.15);
--error: #EF4444;             /* 错误状态 */
--error-subtle: rgba(239, 68, 68, 0.15);
--info: #3B82F6;              /* 信息状态 */
--info-subtle: rgba(59, 130, 246, 0.15);
```

### Light Mode (Optional)

```css
--bg-primary-light: #FAFAFA;
--bg-secondary-light: #FFFFFF;
--text-primary-light: #18181B;
--text-secondary-light: #71717A;
--border-subtle-light: #E4E4E7;
```

### Tailwind Config

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        bg: {
          primary: '#0D0D0F',
          secondary: '#141416',
          tertiary: '#1A1A1D',
          elevated: '#222225',
        },
        border: {
          subtle: '#2A2A2E',
          default: '#3A3A3F',
          strong: '#52525B',
        },
        text: {
          primary: '#EDEDEF',
          secondary: '#8A8A8E',
          tertiary: '#5C5C5F',
        },
        accent: {
          DEFAULT: '#8B5CF6',
          hover: '#A78BFA',
        },
      },
      borderRadius: {
        'sm': '6px',
        'DEFAULT': '8px',
        'lg': '12px',
        'xl': '16px',
      },
    },
  },
}
```

---

## Typography

**Font Stack**:
- **Display/Headings**: `Inter` (variable weight) - 但建议换用更独特的：`Geist`, `Satoshi`, `Plus Jakarta Sans`
- **Body**: `Inter` (variable weight)
- **Mono**: `JetBrains Mono` - 代码、技术内容

**Type Scale** (based on 16px base):

```css
/* Font Sizes */
--text-xs: 0.75rem;     /* 12px - 标签、次要信息 */
--text-sm: 0.8125rem;  /* 13px - 次要文字、表格 */
--text-base: 0.875rem; /* 14px - 正文 */
--text-lg: 1rem;       /* 16px - 子标题 */
--text-xl: 1.25rem;    /* 20px - 标题 */
--text-2xl: 1.5rem;    /* 24px - 大标题 */
--text-3xl: 2rem;       /* 32px - 页面标题 */

/* Font Weights */
--font-normal: 400;
--font-medium: 500;
--font-semibold: 600;

/* Line Heights */
--leading-tight: 1.25;
--leading-normal: 1.5;
--leading-relaxed: 1.625;
```

### Typography in Tailwind

```css
/* Class mapping */
.text-xs { font-size: 0.75rem; line-height: 1rem; }
.text-sm { font-size: 0.8125rem; line-height: 1.25rem; }
.text-base { font-size: 0.875rem; line-height: 1.5rem; }
.text-lg { font-size: 1rem; line-height: 1.5rem; }
.text-xl { font-size: 1.25rem; line-height: 1.25; }
.text-2xl { font-size: 1.5rem; line-height: 1.25; }
.text-3xl { font-size: 2rem; line-height: 1.125; }

.font-medium { font-weight: 500; }
.font-semibold { font-weight: 600; }
```

---

## Spacing System

Base unit: `4px`

```css
/* Spacing Scale */
--space-0: 0;
--space-0.5: 2px;
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

/* Tailwind spacing */
.p-1 { padding: 4px; }
.p-2 { padding: 8px; }
.p-3 { padding: 12px; }
.p-4 { padding: 16px; }
.p-5 { padding: 20px; }
.p-6 { padding: 24px; }
.p-8 { padding: 32px; }

.gap-1 { gap: 4px; }
.gap-2 { gap: 8px; }
.gap-3 { gap: 12px; }
.gap-4 { gap: 16px; }
.gap-6 { gap: 24px; }
.gap-8 { gap: 32px; }
```

### Layout Rhythm

- **Tight groups**: 4-8px - 相关元素
- **Related items**: 12-16px - 同组元素
- **Section spacing**: 24-32px - 内容区块
- **Page margins**: 24-48px - 页面边距

---

## Border Radius

Minimal, precise radii. Never fully rounded.

```css
/* Border Radius Scale */
--radius-sm: 6px;     /* 小元素：标签、徽章 */
--radius-md: 8px;     /* 按钮、输入框 */
--radius-lg: 12px;    /* 卡片、面板 */
--radius-xl: 16px;    /* 大容器、模态框 */

/* Tailwind classes */
.rounded-sm { border-radius: 6px; }
.rounded-md { border-radius: 8px; }
.rounded-lg { border-radius: 12px; }
.rounded-xl { border-radius: 16px; }

/* No fully rounded - this is anti-pattern */
.rounded-full { border-radius: 9999px; /* AVOID */ }
```

---

## Shadow System

Subtle, layered shadows for depth without drama.

```css
/* Shadow Layers - Elevation System */

/* Level 0: Flat (default) */
--shadow-none: none;

/* Level 1: Subtle depth - cards */
--shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.4);
--shadow-md: 0 4px 12px rgba(0, 0, 0, 0.4);

/* Level 2: Elevated - dropdowns */
--shadow-lg: 0 8px 24px rgba(0, 0, 0, 0.5);

/* Level 3: Modal */
--shadow-xl: 0 16px 48px rgba(0, 0, 0, 0.6);

/* Colored shadows (accent glow) */
--shadow-accent: 0 0 0 1px rgba(139, 92, 246, 0.3), 0 4px 16px rgba(139, 92, 246, 0.2);

/* Tailwind */
.shadow-sm { box-shadow: 0 1px 2px rgba(0, 0, 0, 0.4); }
.shadow-md { box-shadow: 0 4px 12px rgba(0, 0, 0, 0.4); }
.shadow-lg { box-shadow: 0 8px 24px rgba(0, 0, 0, 0.5); }
.shadow-xl { box-shadow: 0 16px 48px rgba(0, 0, 0, 0.6); }
```

---

## Component Patterns

### Buttons

**Primary Button**: Solid accent with subtle glow on hover

```css
/* Primary Button */
.btn-primary {
  background: var(--accent-primary);
  color: white;
  font-weight: 500;
  font-size: 0.875rem;
  padding: 8px 16px;
  border-radius: var(--radius-md);
  border: none;
  transition: all 150ms ease;
}

.btn-primary:hover {
  background: var(--accent-hover);
  box-shadow: 0 0 0 1px rgba(139, 92, 246, 0.4), 0 4px 12px rgba(139, 92, 246, 0.3);
}

/* Secondary Button */
.btn-secondary {
  background: transparent;
  color: var(--text-secondary);
  border: 1px solid var(--border-subtle);
  padding: 8px 16px;
  border-radius: var(--radius-md);
  font-weight: 500;
  font-size: 0.875rem;
  transition: all 150ms ease;
}

.btn-secondary:hover {
  background: var(--bg-tertiary);
  border-color: var(--border-default);
  color: var(--text-primary);
}

/* Ghost Button - minimal */
.btn-ghost {
  background: transparent;
  color: var(--text-secondary);
  border: none;
  padding: 8px 12px;
  border-radius: var(--radius-md);
  transition: all 150ms ease;
}

.btn-ghost:hover {
  background: var(--bg-tertiary);
  color: var(--text-primary);
}

/* Danger Button */
.btn-danger {
  background: var(--error);
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: var(--radius-md);
  font-weight: 500;
  transition: all 150ms ease;
}

.btn-danger:hover {
  background: #DC2626;
}
```

### Input Fields

Minimal, single-pixel border, subtle background

```css
/* Input Base */
.input {
  background: var(--bg-secondary);
  border: 1px solid var(--border-subtle);
  border-radius: var(--radius-md);
  padding: 10px 12px;
  font-size: 0.875rem;
  color: var(--text-primary);
  transition: all 150ms ease;
  outline: none;
}

.input::placeholder {
  color: var(--text-tertiary);
}

.input:hover {
  border-color: var(--border-default);
}

.input:focus {
  border-color: var(--accent-primary);
  box-shadow: 0 0 0 3px var(--accent-subtle);
}

/* Textarea */
.textarea {
  min-height: 100px;
  resize: vertical;
}

/* Select */
.select {
  appearance: none;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='16' height='16' viewBox='0 0 24 24' fill='none' stroke='%238A8A8E' stroke-width='2'%3E%3Cpath d='M6 9l6 6 6-6'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right 12px center;
  padding-right: 40px;
}
```

### Cards

Flat, subtle border, no heavy shadows

```css
/* Card */
.card {
  background: var(--bg-secondary);
  border: 1px solid var(--border-subtle);
  border-radius: var(--radius-lg);
  padding: 20px;
  transition: all 200ms ease;
}

.card:hover {
  border-color: var(--border-default);
}

/* Interactive Card */
.card-interactive {
  cursor: pointer;
}

.card-interactive:hover {
  background: var(--bg-tertiary);
  border-color: var(--border-default);
}

/* Card with accent border */
.card-accent {
  border-left: 3px solid var(--accent-primary);
}
```

### Badges & Tags

```css
/* Badge */
.badge {
  display: inline-flex;
  align-items: center;
  padding: 4px 8px;
  font-size: 0.75rem;
  font-weight: 500;
  border-radius: var(--radius-sm);
  background: var(--bg-tertiary);
  color: var(--text-secondary);
}

/* Tag with accent */
.badge-accent {
  background: var(--accent-subtle);
  color: var(--accent-primary);
}

/* Status badges */
.badge-success {
  background: var(--success-subtle);
  color: var(--success);
}

.badge-warning {
  background: var(--warning-subtle);
  color: var(--warning);
}

.badge-error {
  background: var(--error-subtle);
  color: var(--error);
}
```

### Navigation

```css
/* Sidebar Nav Item */
.nav-item {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 10px 12px;
  border-radius: var(--radius-md);
  color: var(--text-secondary);
  font-size: 0.875rem;
  font-weight: 500;
  transition: all 150ms ease;
  cursor: pointer;
}

.nav-item:hover {
  background: var(--bg-tertiary);
  color: var(--text-primary);
}

.nav-item.active {
  background: var(--accent-subtle);
  color: var(--accent-primary);
}

/* Nav icon size */
.nav-item svg {
  width: 18px;
  height: 18px;
  stroke-width: 1.5;
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
  padding: 12px 16px;
  font-size: 0.75rem;
  font-weight: 600;
  color: var(--text-tertiary);
  text-transform: uppercase;
  letter-spacing: 0.05em;
  border-bottom: 1px solid var(--border-subtle);
}

.table td {
  padding: 12px 16px;
  font-size: 0.875rem;
  color: var(--text-primary);
  border-bottom: 1px solid var(--border-subtle);
}

.table tr:hover td {
  background: var(--bg-tertiary);
}

/* Compact table */
.table-compact td {
  padding: 8px 16px;
}
```

### Modals & Overlays

```css
/* Modal Overlay */
.modal-overlay {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.7);
  backdrop-filter: blur(4px);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 50;
}

/* Modal Content */
.modal-content {
  background: var(--bg-elevated);
  border: 1px solid var(--border-default);
  border-radius: var(--radius-xl);
  padding: 24px;
  max-width: 500px;
  width: 100%;
  max-height: 85vh;
  overflow-y: auto;
  box-shadow: var(--shadow-xl);
}

/* Dropdown */
.dropdown {
  background: var(--bg-elevated);
  border: 1px solid var(--border-default);
  border-radius: var(--radius-lg);
  padding: 8px;
  min-width: 200px;
  box-shadow: var(--shadow-lg);
}

.dropdown-item {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 10px 12px;
  border-radius: var(--radius-md);
  color: var(--text-secondary);
  font-size: 0.875rem;
  cursor: pointer;
  transition: all 150ms ease;
}

.dropdown-item:hover {
  background: var(--bg-tertiary);
  color: var(--text-primary);
}
```

---

## Motion & Animation

Precise, quick transitions. No bounce or elastic easing.

```css
/* Timing */
--duration-fast: 100ms;
--duration-normal: 150ms;
--duration-slow: 200ms;
--duration-slower: 300ms;

/* Easing - Smooth deceleration */
--ease-out: cubic-bezier(0.16, 1, 0.3, 1);
--ease-in-out: cubic-bezier(0.65, 0, 0.35, 1);

/* Transition utilities */
.transition-fast { transition: all var(--duration-fast) var(--ease-out); }
.transition-normal { transition: all var(--duration-normal) var(--ease-out); }
.transition-slow { transition: all var(--duration-slow) var(--ease-out); }

/* Hover transforms */
.hover-lift:hover {
  transform: translateY(-2px);
}

/* Fade animations */
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

@keyframes slideUp {
  from {
    opacity: 0;
    transform: translateY(8px);
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
```

---

## Visual Principles

1. **Depth through layering** - Background colors create spatial hierarchy, not shadows
2. **Accent as signal** - Purple accent used sparingly for interactive/focus states
3. **Typography hierarchy** - Clear size/weight contrast between content levels
4. **Minimal decoration** - No gratuitous visual elements; every pixel has purpose
5. **Dark-first** - Design for dark mode primary; light mode is alternative
6. **High contrast text** - Text is highly legible against dark backgrounds

---

## CSS Variables (Complete Set)

```css
:root {
  /* Colors */
  --bg-primary: #0D0D0F;
  --bg-secondary: #141416;
  --bg-tertiary: #1A1A1D;
  --bg-elevated: #222225;

  --border-subtle: #2A2A2E;
  --border-default: #3A3A3F;
  --border-strong: #52525B;

  --text-primary: #EDEDEF;
  --text-secondary: #8A8A8E;
  --text-tertiary: #5C5C5F;

  --accent-primary: #8B5CF6;
  --accent-hover: #A78BFA;
  --accent-subtle: rgba(139, 92, 246, 0.15);

  --success: #10B981;
  --success-subtle: rgba(16, 185, 129, 0.15);
  --warning: #F59E0B;
  --warning-subtle: rgba(245, 158, 11, 0.15);
  --error: #EF4444;
  --error-subtle: rgba(239, 68, 68, 0.15);
  --info: #3B82F6;
  --info-subtle: rgba(59, 130, 246, 0.15);

  /* Typography */
  --font-sans: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
  --font-mono: 'JetBrains Mono', 'Fira Code', monospace;

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
  --radius-sm: 6px;
  --radius-md: 8px;
  --radius-lg: 12px;
  --radius-xl: 16px;

  /* Shadows */
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.4);
  --shadow-md: 0 4px 12px rgba(0, 0, 0, 0.4);
  --shadow-lg: 0 8px 24px rgba(0, 0, 0, 0.5);
  --shadow-xl: 0 16px 48px rgba(0, 0, 0, 0.6);

  /* Transitions */
  --duration-fast: 100ms;
  --duration-normal: 150ms;
  --duration-slow: 200ms;
  --ease-out: cubic-bezier(0.16, 1, 0.3, 1);
}
```

---

## Usage Tips

- Use `bg-secondary` for cards and elevated surfaces
- Use `border-subtle` for internal divisions, `border-default` for external
- Accent color should appear on interactive elements: focus rings, active states, links
- Text hierarchy: primary for content, secondary for labels, tertiary for hints
- Keep spacing consistent with 4px base unit; use 8, 12, 16, 24, 32 sequence
- Prefer subtle background differences over heavy borders for hierarchy