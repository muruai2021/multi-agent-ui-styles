---
name: supabase-style
description: "Supabase风格 - 终端美学开发者风"
type: ui-style
---

# Supabase Style Design System

## Overview

Supabase风格是「终端美学」与开发者文化的融合——它将IDE、终端、数据库工具的美学带入Web界面。深色背景、绿色主调、monospace元素，构建出开发者熟悉且信任的数字工作空间。

**Brands**: Supabase, GitHub Desktop, VS Code, DBeaver, TablePlus

**Mood**: 技术、终端、开发者友好、数据库、代码、专业、高效

---

## Color Palette

### Terminal Dark (Primary)

```css
/* Background Scale - Deep terminal black */
--bg-primary: #0D0D0D;           /* 最深背景 */
--bg-secondary: #141414;          /* 卡片背景 */
--bg-tertiary: #1A1A1A;           /* 悬浮背景 */
--bg-elevated: #1E1E1E;           /* 模态框、下拉 */
--bg-code: #0A0A0A;              /* 代码块背景 */

/* Surface & Borders */
--border-subtle: #262626;
--border-default: #333333;
--border-strong: #404040;

/* Text - High contrast green on dark */
--text-primary: #E4E4E7;
--text-secondary: #A1A1AA;
--text-tertiary: #71717A;
--text-muted: #52525B;

/* Terminal Green - Primary accent */
--accent-primary: #3ECF8E;        /* Supabase green */
--accent-hover: #5ED9A4;
--accent-subtle: rgba(62, 207, 142, 0.15);
--accent-muted: rgba(62, 207, 142, 0.4);
--accent-text: #3ECF8E;

/* Alternative accent - Orange for warnings */
--accent-orange: #F97316;
--accent-orange-subtle: rgba(249, 115, 22, 0.15);

/* Semantic Colors */
--success: #3ECF8E;
--success-subtle: rgba(62, 207, 142, 0.15);
--warning: #FBBF24;
--warning-subtle: rgba(251, 191, 36, 0.15);
--error: #EF4444;
--error-subtle: rgba(239, 68, 68, 0.15);
--info: #60A5FA;
--info-subtle: rgba(96, 165, 250, 0.15);

/* Code specific */
--code-string: #A5D6FF;
--code-keyword: #C792EA;
--code-function: #82AAFF;
--code-variable: #F78C6C;
--code-comment: #5C6370;
--code-number: #F78C6C;
```

### Light Mode (Developer preference)

```css
--bg-primary-light: #FAFAFA;
--bg-secondary-light: #F4F4F5;
--text-primary-light: #18181B;
--text-secondary-light: #71717A;
--accent-primary-light: #10B981;
```

### Tailwind Config

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        bg: {
          primary: '#0D0D0D',
          secondary: '#141414',
          tertiary: '#1A1A1A',
          elevated: '#1E1E1E',
        },
        terminal: {
          green: '#3ECF8E',
          orange: '#F97316',
        },
        border: {
          subtle: '#262626',
          DEFAULT: '#333333',
          strong: '#404040',
        },
        text: {
          primary: '#E4E4E7',
          secondary: '#A1A1AA',
          tertiary: '#71717A',
        },
        code: {
          string: '#A5D6FF',
          keyword: '#C792EA',
          function: '#82AAFF',
          variable: '#F78C6C',
        },
      },
      fontFamily: {
        mono: ['JetBrains Mono', 'Fira Code', 'monospace'],
      },
    },
  },
}
```

---

## Typography

**Font Stack**:
- **Primary**: `JetBrains Mono` - 代码优先，终端感
- **Fallback**: `Fira Code`, `Consolas`, monospace
- **UI Labels**: `Inter` (rarely, for longer prose)
- **Chinese**: `Source Han Sans`, `Noto Sans SC`

**Important**: Supabase风格以monospace为主，数字和代码元素天然突出

```css
/* Type Scale - Monospace dominant */
--text-xs: 0.75rem;     /* 12px */
--text-sm: 0.8125rem;   /* 13px */
--text-base: 0.875rem;   /* 14px - monospace base */
--text-lg: 1rem;         /* 16px */
--text-xl: 1.125rem;     /* 18px */
--text-2xl: 1.375rem;    /* 22px */
--text-3xl: 1.75rem;     /* 28px */

/* Font Weights */
--font-normal: 400;
--font-medium: 500;
--font-semibold: 600;

/* Line Heights */
--leading-tight: 1.25;
--leading-normal: 1.5;
--leading-relaxed: 1.625;

/* Letter Spacing - Slightly expanded for mono */
--tracking-tight: -0.01em;
--tracking-normal: 0;
--tracking-wide: 0.05em;
```

### Typography Classes

```css
/* Terminal text */
.terminal-text {
  font-family: var(--font-mono);
  font-size: var(--text-sm);
  color: var(--accent-primary);
}

/* Code block */
.code-block {
  font-family: var(--font-mono);
  font-size: var(--text-sm);
  background: var(--bg-code);
  padding: 16px;
  border-radius: var(--radius-md);
  border: 1px solid var(--border-subtle);
  overflow-x: auto;
}

/* Prompt */
.prompt {
  font-family: var(--font-mono);
  font-size: var(--text-sm);
  color: var(--text-secondary);
}

.prompt-prefix {
  color: var(--accent-primary);
}

/* Table data - monospace */
.table-mono {
  font-family: var(--font-mono);
  font-size: var(--text-sm);
}
```

---

## Spacing System

Base unit: `4px` with compact density for data-heavy interfaces

```css
/* Spacing Scale */
--space-1: 4px;
--space-2: 8px;
--space-3: 12px;
--space-4: 16px;
--space-5: 20px;
--space-6: 24px;
--space-8: 32px;
--space-10: 40px;
--space-12: 48px;

/* Grid */
--grid-gap: 16px;

/* Table */
--cell-padding: 12px;
--row-height: 44px;
```

### Layout Characteristics

- **Compact density**: Information-rich tables and grids
- **Code-first layout**: Visual hierarchy built around code blocks
- **Database table aesthetic**: Grid-heavy, data-focused

---

## Border Radius

Minimal, functional radii. Terminal heritage.

```css
/* Border Radius - Sharp, minimal */
--radius-sm: 4px;
--radius-md: 6px;
--radius-lg: 8px;
--radius-xl: 10px;

/* No full rounding - terminals don't round */
--radius-full: 9999px;
```

---

## Shadow System

Subtle, precise shadows for data panels

```css
/* Shadow Layers */
--shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.4);
--shadow-md: 0 2px 8px rgba(0, 0, 0, 0.4);
--shadow-lg: 0 4px 16px rgba(0, 0, 0, 0.5);
--shadow-xl: 0 8px 32px rgba(0, 0, 0, 0.6);

/* Terminal glow */
--shadow-glow: 0 0 0 1px var(--accent-primary), 0 0 20px rgba(62, 207, 142, 0.3);

/* Code block glow */
--shadow-code: inset 0 0 0 1px var(--border-subtle);
```

---

## Component Patterns

### Buttons

Terminal-style buttons with clear hierarchy

```css
/* Primary Button - Green accent */
.btn-primary {
  background: var(--accent-primary);
  color: var(--bg-primary);
  font-family: var(--font-mono);
  font-weight: 500;
  font-size: 0.8125rem;
  padding: 8px 16px;
  border-radius: var(--radius-md);
  border: none;
  transition: all 150ms ease;
  display: inline-flex;
  align-items: center;
  gap: 8px;
}

.btn-primary:hover {
  background: var(--accent-hover);
  box-shadow: var(--shadow-glow);
}

/* Secondary Button - Outline */
.btn-secondary {
  background: transparent;
  color: var(--text-primary);
  font-family: var(--font-mono);
  border: 1px solid var(--border-default);
  padding: 8px 16px;
  border-radius: var(--radius-md);
  font-weight: 500;
  font-size: 0.8125rem;
  transition: all 150ms ease;
}

.btn-secondary:hover {
  background: var(--bg-tertiary);
  border-color: var(--accent-primary);
}

/* Ghost Button */
.btn-ghost {
  background: transparent;
  color: var(--text-secondary);
  font-family: var(--font-mono);
  border: none;
  padding: 8px 12px;
  border-radius: var(--radius-md);
  font-size: 0.8125rem;
  transition: all 150ms ease;
}

.btn-ghost:hover {
  background: var(--bg-tertiary);
  color: var(--accent-primary);
}

/* Danger Button */
.btn-danger {
  background: var(--error);
  color: white;
  font-family: var(--font-mono);
  border: none;
  padding: 8px 16px;
  border-radius: var(--radius-md);
  font-weight: 500;
  font-size: 0.8125rem;
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
  background: var(--bg-tertiary);
  color: var(--accent-primary);
}
```

### Input Fields

Monospace inputs with terminal feel

```css
/* Input Base */
.input {
  background: var(--bg-code);
  border: 1px solid var(--border-subtle);
  border-radius: var(--radius-md);
  padding: 10px 12px;
  font-family: var(--font-mono);
  font-size: 0.8125rem;
  color: var(--text-primary);
  transition: all 150ms ease;
  outline: none;
  width: 100%;
}

.input::placeholder {
  color: var(--text-muted);
}

.input:hover {
  border-color: var(--border-default);
}

.input:focus {
  border-color: var(--accent-primary);
  box-shadow: 0 0 0 3px var(--accent-subtle);
}

/* Database input styling */
.input-database {
  font-family: var(--font-mono);
  text-transform: uppercase;
}

/* Textarea */
.textarea {
  font-family: var(--font-mono);
  min-height: 100px;
}

/* Select */
.select {
  appearance: none;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='16' height='16' viewBox='0 0 24 24' fill='none' stroke='%2371717A' stroke-width='2'%3E%3Cpath d='M6 9l6 6 6-6'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right 12px center;
  padding-right: 40px;
  font-family: var(--font-mono);
}
```

### Code Block

Signature component for terminal aesthetic

```css
/* Code Block */
.code-block {
  background: var(--bg-code);
  border: 1px solid var(--border-subtle);
  border-radius: var(--radius-md);
  padding: 16px;
  font-family: var(--font-mono);
  font-size: 0.8125rem;
  line-height: 1.6;
  overflow-x: auto;
}

/* Syntax highlighting wrapper */
.code-highlight {
  background: var(--bg-code);
  border-radius: var(--radius-md);
  overflow: hidden;
}

/* Inline code */
.code-inline {
  font-family: var(--font-mono);
  font-size: 0.875em;
  background: var(--bg-tertiary);
  padding: 2px 6px;
  border-radius: var(--radius-sm);
  color: var(--accent-primary);
}

/* Terminal output */
.terminal-output {
  font-family: var(--font-mono);
  font-size: 0.8125rem;
  color: var(--text-secondary);
  background: var(--bg-primary);
  padding: 16px;
  border-radius: var(--radius-md);
  border: 1px solid var(--border-subtle);
}

.terminal-line {
  display: flex;
  gap: 12px;
}

.terminal-prompt {
  color: var(--accent-primary);
  flex-shrink: 0;
}

.terminal-command {
  color: var(--text-primary);
}

.terminal-result {
  color: var(--text-secondary);
  margin-top: 8px;
}
```

### Data Tables

```css
/* Table */
.table {
  width: 100%;
  border-collapse: collapse;
  font-family: var(--font-mono);
  font-size: 0.8125rem;
}

.table th {
  text-align: left;
  padding: var(--cell-padding);
  font-weight: 600;
  color: var(--text-secondary);
  border-bottom: 1px solid var(--border-default);
  background: var(--bg-secondary);
  text-transform: uppercase;
  letter-spacing: 0.05em;
  font-size: 0.75rem;
}

.table td {
  padding: var(--cell-padding);
  color: var(--text-primary);
  border-bottom: 1px solid var(--border-subtle);
}

.table tr:hover td {
  background: var(--bg-tertiary);
}

/* Table with monospace cells */
.table-mono td {
  font-family: var(--font-mono);
}

/* Row selection */
.table tr.selected td {
  background: var(--accent-subtle);
}

/* Schema table */
.schema-table {
  font-family: var(--font-mono);
}

.schema-table .column-name {
  color: var(--accent-primary);
}

.schema-table .column-type {
  color: var(--code-keyword);
}
```

### Navigation

```css
/* Sidebar */
.sidebar {
  width: 240px;
  background: var(--bg-secondary);
  border-right: 1px solid var(--border-subtle);
  height: 100vh;
  position: fixed;
  left: 0;
  top: 0;
  overflow-y: auto;
}

/* Sidebar Header */
.sidebar-header {
  padding: 16px;
  border-bottom: 1px solid var(--border-subtle);
}

/* Nav Item */
.nav-item {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 10px 16px;
  color: var(--text-secondary);
  font-family: var(--font-mono);
  font-size: 0.8125rem;
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
  border-left: 2px solid var(--accent-primary);
}

/* Nav icon */
.nav-item svg {
  width: 18px;
  height: 18px;
  stroke-width: 1.5;
}
```

### Badges

```css
/* Badge - Terminal style */
.badge {
  display: inline-flex;
  align-items: center;
  gap: 4px;
  padding: 4px 8px;
  font-family: var(--font-mono);
  font-size: 0.6875rem;
  font-weight: 500;
  border-radius: var(--radius-sm);
  background: var(--bg-tertiary);
  color: var(--text-secondary);
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

/* Type badge */
.badge-type {
  background: var(--accent-subtle);
  color: var(--accent-primary);
}

/* Status badge */
.badge-status {
  background: var(--success-subtle);
  color: var(--success);
}

/* Count badge */
.badge-count {
  min-width: 20px;
  height: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0 6px;
  background: var(--accent-primary);
  color: var(--bg-primary);
  font-size: 0.6875rem;
  font-weight: 600;
  border-radius: 10px;
}
```

---

## Motion & Animation

Functional, quick transitions that feel like terminal operations

```css
/* Timing */
--duration-fast: 100ms;
--duration-normal: 150ms;
--duration-slow: 200ms;

/* Easing */
--ease-out: cubic-bezier(0.16, 1, 0.3, 1);

/* Terminal-style blinks */
@keyframes cursor-blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}

.cursor-blink {
  animation: cursor-blink 1s infinite;
}

/* Typewriter effect */
@keyframes typewriter {
  from { width: 0; }
  to { width: 100%; }
}

/* Fade in terminal style */
@keyframes terminalFadeIn {
  from { opacity: 0; transform: translateY(-4px); }
  to { opacity: 1; transform: translateY(0); }
}

.terminal-fade-in {
  animation: terminalFadeIn var(--duration-normal) var(--ease-out);
}
```

---

## Visual Principles

1. **Monospace dominant** - Everything feels like code/terminal
2. **Terminal green** - Accent color is always green (#3ECF8E)
3. **Dark first** - Dark mode is primary, light is alternative
4. **Data-focused** - Tables, grids, code blocks everywhere
5. **Uppercase labels** - Terminal heritage, for types and status
6. **Terminal glow** - Green glow for active/focus states

---

## CSS Variables (Complete Set)

```css
:root {
  /* Colors */
  --bg-primary: #0D0D0D;
  --bg-secondary: #141414;
  --bg-tertiary: #1A1A1A;
  --bg-elevated: #1E1E1E;
  --bg-code: #0A0A0A;

  --border-subtle: #262626;
  --border-default: #333333;
  --border-strong: #404040;

  --text-primary: #E4E4E7;
  --text-secondary: #A1A1AA;
  --text-tertiary: #71717A;
  --text-muted: #52525B;

  --accent-primary: #3ECF8E;
  --accent-hover: #5ED9A4;
  --accent-subtle: rgba(62, 207, 142, 0.15);
  --accent-orange: #F97316;

  --success: #3ECF8E;
  --warning: #FBBF24;
  --error: #EF4444;
  --info: #60A5FA;

  /* Code colors */
  --code-string: #A5D6FF;
  --code-keyword: #C792EA;
  --code-function: #82AAFF;
  --code-variable: #F78C6C;

  /* Typography */
  --font-mono: 'JetBrains Mono', 'Fira Code', monospace;
  --font-sans: 'Inter', -apple-system, sans-serif;

  /* Spacing */
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-6: 24px;
  --space-8: 32px;

  /* Border Radius */
  --radius-sm: 4px;
  --radius-md: 6px;
  --radius-lg: 8px;

  /* Shadows */
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.4);
  --shadow-md: 0 2px 8px rgba(0, 0, 0, 0.4);
  --shadow-glow: 0 0 0 1px var(--accent-primary), 0 0 20px rgba(62, 207, 142, 0.3);

  /* Transitions */
  --duration-fast: 100ms;
  --duration-normal: 150ms;
  --ease-out: cubic-bezier(0.16, 1, 0.3, 1);
}
```

---

## Usage Tips

- Use `JetBrains Mono` as primary font everywhere
- Terminal green (#3ECF8E) is the signature accent
- Dark backgrounds with high contrast text
- Monospace for labels, tables, and code blocks
- Uppercase badges and type labels
- Code block styling for any "terminal" sections
- Grid-based layouts for data display