---
name: spotify-style
description: "Spotify风格 - 品牌驱动沉浸娱乐"
type: ui-style
---

# Spotify Style Design System

## Overview

Spotify风格是「品牌驱动」设计的极致——它将品牌身份（绿色、沉浸式、动态）融入每个像素。深色沉浸式背景、标志性的绿色、高对比度的内容，构建出音乐驱动的体验。

**Brands**: Spotify, Discord, Twitch, YouTube Music, Apple Music

**Mood**: 沉浸、品牌驱动、音乐、活力、年轻、动感、活力、现代

---

## Color Palette

### Dark Immersive (Primary)

```css
/* Background Scale - Deep blacks with brand tint */
--bg-primary: #000000;
--bg-secondary: #121212;
--bg-tertiary: #181818;
--bg-elevated: #1F1F1F;
--bg-highlight: #282828;
--bg-hover: #2A2A2A;

/* Surface & Borders */
--border-subtle: rgba(255, 255, 255, 0.1);
--border-default: rgba(255, 255, 255, 0.2);

/* Text - High contrast on dark */
--text-primary: #FFFFFF;
--text-secondary: #B3B3B3;
--text-tertiary: #6A6A6A;
--text-disabled: #535353;
--text-inverse: #000000;

/* Spotify Green - The signature */
--accent-primary: #1DB954;
--accent-hover: #1ED760;
--accent-subtle: rgba(29, 185, 84, 0.15);
--accent-muted: rgba(29, 185, 84, 0.3);

/* Alternative accents - Brand supporting colors */
--accent-purple: #8B5CF6;
--accent-pink: #E91E63;
--accent-orange: #FF6B35;
--accent-yellow: #FFB800;

/* Semantic Colors */
--success: #1DB954;
--warning: #FFB800;
--error: #E91429;
--info: #1DA1F2;

/* Card overlays */
--overlay-gradient: linear-gradient(180deg, transparent 0%, rgba(0, 0, 0, 0.8) 100%);
```

### Light Mode (Alternative)

```css
--bg-primary-light: #FFFFFF;
--bg-secondary-light: #F8F8F8;
--bg-tertiary-light: #EFEFEF;
--text-primary-light: #000000;
--text-secondary-light: #6A6A6A;
--accent-primary-light: #1DB954;
```

### Tailwind Config

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        spotify: {
          green: '#1DB954',
          hover: '#1ED760',
        },
        bg: {
          primary: '#000000',
          secondary: '#121212',
          tertiary: '#181818',
          elevated: '#1F1F1F',
        },
        text: {
          primary: '#FFFFFF',
          secondary: '#B3B3B3',
        },
      },
    },
  },
}
```

---

## Typography

**Font Stack**:
- **Primary**: `Spotify Circular`, `Inter`, `Satoshi` (rounded sans)
- **Display**: Bold weights for impact
- **Fallback**: `-apple-system`, `system-ui`

**Important**: Spotify uses circular/geometric fonts with heavy weights. The aesthetic is bold and confident.

```css
/* Type Scale */
--text-xs: 0.6875rem;   /* 11px - metadata */
--text-sm: 0.75rem;     /* 12px */
--text-base: 0.875rem;  /* 14px */
--text-lg: 1rem;        /* 16px */
--text-xl: 1.125rem;    /* 18px */
--text-2xl: 1.5rem;     /* 24px */
--text-3xl: 1.75rem;    /* 28px */
--text-4xl: 2.25rem;    /* 36px */
--text-5xl: 3rem;       /* 48px */

/* Font Weights - Bold emphasis */
--font-normal: 400;
--font-medium: 500;
--font-bold: 700;
--font-black: 900;

/* Line Heights */
--leading-tight: 1.1;
--leading-normal: 1.4;
--leading-relaxed: 1.6;

/* Letter Spacing - Slight tracking */
--tracking-tight: -0.02em;
--tracking-normal: 0;
--tracking-wide: 0.02em;
```

### Typography Classes

```css
/* Hero title */
.title-hero {
  font-size: 3rem;
  font-weight: 900;
  line-height: 1.1;
  letter-spacing: -0.03em;
  color: var(--text-primary);
}

/* Section title */
.title-section {
  font-size: 1.5rem;
  font-weight: 700;
  line-height: 1.2;
  color: var(--text-primary);
}

/* Card title */
.title-card {
  font-size: 1rem;
  font-weight: 600;
  color: var(--text-primary);
  line-height: 1.3;
}

/* Body text */
.body {
  font-size: 0.875rem;
  color: var(--text-secondary);
  line-height: 1.5;
}

/* Metadata */
.meta {
  font-size: 0.6875rem;
  font-weight: 500;
  color: var(--text-tertiary);
  text-transform: uppercase;
  letter-spacing: 0.08em;
}

/* Now playing */
.now-playing {
  font-size: 0.75rem;
  font-weight: 500;
  color: var(--accent-primary);
  text-transform: uppercase;
  letter-spacing: 0.1em;
}
```

---

## Spacing System

Compact density for content-rich playlists. Base unit: `8px`

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

/* Grid */
--grid-gap: 16px;
--grid-item-width: 180px;
--grid-item-min-width: 140px;

/* Card */
--card-padding: 16px;
```

### Layout Characteristics

- **Content density** - Information-rich grid layouts
- **Playlists dominance** - Album art grids everywhere
- **Sidebar navigation** - Fixed left sidebar (240px)

---

## Border Radius

Rounded, modern, geometric

```css
/* Border Radius - Rounded, modern */
--radius-sm: 4px;
--radius-md: 8px;
--radius-lg: 12px;
--radius-xl: 16px;
--radius-2xl: 24px;
--radius-full: 9999px;

/* Album art */
.radius-album {
  border-radius: var(--radius-md);
}

/* Cards */
.radius-card {
  border-radius: var(--radius-lg);
}
```

---

## Shadow System

Subtle depth on dark surfaces

```css
/* Shadow Layers */
--shadow-sm: 0 2px 4px rgba(0, 0, 0, 0.4);
--shadow-md: 0 4px 12px rgba(0, 0, 0, 0.5);
--shadow-lg: 0 8px 24px rgba(0, 0, 0, 0.6);

/* Card hover glow - Spotify green */
--shadow-card-hover: 0 8px 24px rgba(29, 185, 84, 0.2);

/* Album art shadow */
--shadow-album: 0 4px 60px rgba(0, 0, 0, 0.6);
```

---

## Component Patterns

### Buttons

Green-accented, bold buttons

```css
/* Primary Button - Green */
.btn-primary {
  background: var(--accent-primary);
  color: var(--text-inverse);
  font-weight: 700;
  font-size: 0.875rem;
  padding: 12px 24px;
  border-radius: var(--radius-full);
  border: none;
  transition: all 200ms ease;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.btn-primary:hover {
  background: var(--accent-hover);
  transform: scale(1.05);
}

.btn-primary:active {
  transform: scale(0.98);
}

/* Secondary Button */
.btn-secondary {
  background: transparent;
  color: var(--text-primary);
  font-weight: 700;
  font-size: 0.875rem;
  padding: 12px 24px;
  border-radius: var(--radius-full);
  border: 1px solid var(--border-default);
  transition: all 200ms ease;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.btn-secondary:hover {
  border-color: var(--text-primary);
  background: rgba(255, 255, 255, 0.1);
}

/* Ghost Button */
.btn-ghost {
  background: transparent;
  color: var(--text-secondary);
  font-weight: 500;
  font-size: 0.875rem;
  padding: 8px 16px;
  border-radius: var(--radius-md);
  border: none;
  transition: all 200ms ease;
}

.btn-ghost:hover {
  color: var(--text-primary);
}

/* Icon Button */
.btn-icon {
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: var(--radius-full);
  background: var(--bg-highlight);
  color: var(--text-primary);
  transition: all 200ms ease;
}

.btn-icon:hover {
  background: var(--bg-hover);
  transform: scale(1.1);
}

/* Play button - Album card */
.btn-play {
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: var(--radius-full);
  background: var(--accent-primary);
  color: var(--text-inverse);
  transition: all 200ms ease;
  box-shadow: var(--shadow-md);
  position: absolute;
  bottom: 8px;
  right: 8px;
  opacity: 0;
  transform: translateY(8px);
}

.btn-play:hover {
  transform: scale(1.1);
  background: var(--accent-hover);
}

/* Card hover - show play button */
.card:hover .btn-play {
  opacity: 1;
  transform: translateY(0);
}
```

### Cards

Album art cards with hover effects

```css
/* Card - Album/Playlist */
.card {
  background: var(--bg-elevated);
  border-radius: var(--radius-lg);
  padding: 16px;
  transition: all 200ms ease;
  cursor: pointer;
}

.card:hover {
  background: var(--bg-highlight);
}

/* Card Image */
.card-image {
  aspect-ratio: 1;
  border-radius: var(--radius-md);
  overflow: hidden;
  position: relative;
  box-shadow: var(--shadow-album);
  margin-bottom: 16px;
}

.card-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 300ms ease;
}

.card:hover .card-image img {
  transform: scale(1.05);
}

/* Play button overlay */
.card-play-overlay {
  position: absolute;
  inset: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgba(0, 0, 0, 0.4);
  opacity: 0;
  transition: all 200ms ease;
}

.card:hover .card-play-overlay {
  opacity: 1;
}

/* Card Content */
.card-title {
  font-size: 1rem;
  font-weight: 600;
  color: var(--text-primary);
  margin-bottom: 4px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

.card-description {
  font-size: 0.875rem;
  color: var(--text-tertiary);
  line-height: 1.4;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}

/* Artist card */
.card-artist {
  background: var(--bg-elevated);
  border-radius: var(--radius-lg);
  padding: 20px;
  text-align: center;
  transition: all 200ms ease;
}

.card-artist:hover {
  background: var(--bg-highlight);
}

.card-artist-image {
  width: 160px;
  height: 160px;
  border-radius: var(--radius-full);
  overflow: hidden;
  margin: 0 auto 16px;
}

.card-artist-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
```

### Input Fields

```css
/* Input */
.input {
  background: var(--bg-elevated);
  border: 1px solid transparent;
  border-radius: var(--radius-full);
  padding: 12px 20px;
  font-size: 0.875rem;
  color: var(--text-primary);
  transition: all 200ms ease;
  outline: none;
  width: 100%;
}

.input::placeholder {
  color: var(--text-tertiary);
}

.input:focus {
  background: var(--bg-highlight);
  border-color: var(--accent-primary);
}

/* Search */
.search-input {
  background: var(--bg-secondary);
  border: 1px solid var(--border-subtle);
  padding: 12px 16px 12px 44px;
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
/* Sidebar */
.sidebar {
  width: 240px;
  background: var(--bg-primary);
  height: 100vh;
  position: fixed;
  left: 0;
  top: 0;
  padding: 8px;
  overflow-y: auto;
}

/* Sidebar Logo */
.sidebar-logo {
  padding: 16px;
  margin-bottom: 8px;
}

.sidebar-logo svg {
  width: 100px;
  height: 32px;
}

/* Sidebar Section */
.sidebar-section {
  margin-bottom: 24px;
}

/* Sidebar Item */
.sidebar-item {
  display: flex;
  align-items: center;
  gap: 16px;
  padding: 12px 16px;
  border-radius: var(--radius-md);
  color: var(--text-secondary);
  font-size: 0.875rem;
  font-weight: 500;
  transition: all 200ms ease;
}

.sidebar-item:hover {
  color: var(--text-primary);
  background: var(--bg-secondary);
}

.sidebar-item.active {
  color: var(--text-primary);
}

.sidebar-item svg {
  width: 24px;
  height: 24px;
  flex-shrink: 0;
}

/* Library section */
.sidebar-library {
  background: var(--bg-secondary);
  border-radius: var(--radius-lg);
  padding: 8px;
}

/* Nav Item with count */
.sidebar-item-count {
  margin-left: auto;
  font-size: 0.75rem;
  color: var(--text-tertiary);
}
```

### Playlist Row

```css
/* Track row */
.track-row {
  display: grid;
  grid-template-columns: 16px 1fr 80px 80px;
  align-items: center;
  gap: 16px;
  padding: 8px 16px;
  border-radius: var(--radius-md);
  transition: all 200ms ease;
}

.track-row:hover {
  background: rgba(255, 255, 255, 0.1);
}

.track-number {
  font-size: 0.875rem;
  color: var(--text-tertiary);
  text-align: center;
}

.track-info {
  display: flex;
  align-items: center;
  gap: 16px;
}

.track-image {
  width: 40px;
  height: 40px;
  border-radius: var(--radius-sm);
  overflow: hidden;
  flex-shrink: 0;
}

.track-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.track-title {
  font-size: 0.875rem;
  font-weight: 500;
  color: var(--text-primary);
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

.track-artist {
  font-size: 0.875rem;
  color: var(--text-secondary);
}

.track-album {
  font-size: 0.875rem;
  color: var(--text-tertiary);
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

.track-duration {
  font-size: 0.875rem;
  color: var(--text-tertiary);
  text-align: right;
}
```

### Now Playing Bar

```css
/* Now Playing Bar */
.now-playing-bar {
  height: 90px;
  background: var(--bg-secondary);
  border-top: 1px solid var(--border-subtle);
  display: grid;
  grid-template-columns: 240px 1fr 240px;
  align-items: center;
  padding: 0 16px;
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  z-index: 100;
}

/* Now playing track info */
.now-playing-track {
  display: flex;
  align-items: center;
  gap: 16px;
}

.now-playing-image {
  width: 56px;
  height: 56px;
  border-radius: var(--radius-sm);
  overflow: hidden;
}

.now-playing-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.now-playing-info {
  overflow: hidden;
}

.now-playing-title {
  font-size: 0.875rem;
  font-weight: 500;
  color: var(--text-primary);
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

.now-playing-artist {
  font-size: 0.75rem;
  color: var(--text-secondary);
}

/* Controls */
.now-playing-controls {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
}

.control-buttons {
  display: flex;
  align-items: center;
  gap: 16px;
}

.control-btn {
  width: 32px;
  height: 32px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--text-secondary);
  transition: all 200ms ease;
}

.control-btn:hover {
  color: var(--text-primary);
  transform: scale(1.1);
}

.control-btn.play {
  width: 40px;
  height: 40px;
  background: var(--text-primary);
  color: var(--bg-primary);
  border-radius: var(--radius-full);
}

.control-btn.play:hover {
  transform: scale(1.1);
}

/* Progress bar */
.progress-bar {
  width: 100%;
  height: 4px;
  background: var(--bg-hover);
  border-radius: var(--radius-full);
  overflow: hidden;
  cursor: pointer;
}

.progress-fill {
  height: 100%;
  background: var(--text-primary);
  border-radius: var(--radius-full);
  transition: width 100ms linear;
}
```

---

## Motion & Animation

Smooth, responsive, music-driven

```css
/* Timing */
--duration-fast: 100ms;
--duration-normal: 200ms;
--duration-slow: 300ms;
--duration-slower: 500ms;

/* Easing */
--ease-out: cubic-bezier(0.16, 1, 0.3, 1);
--ease-spring: cubic-bezier(0.34, 1.56, 0.64, 1);

/* Hover scale */
.hover-scale {
  transition: transform var(--duration-normal) var(--ease-out);
}

.hover-scale:hover {
  transform: scale(1.05);
}

/* Play button reveal */
.play-reveal {
  opacity: 0;
  transform: translateY(8px);
  transition: all var(--duration-normal) var(--ease-out);
}

.card:hover .play-reveal {
  opacity: 1;
  transform: translateY(0);
}

/* Fade in */
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

.animate-fadeIn {
  animation: fadeIn var(--duration-normal) var(--ease-out);
}

/* Pulse animation for playing */
@keyframes pulse {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.05); }
}

.is-playing {
  animation: pulse 2s ease-in-out infinite;
}
```

---

## Visual Principles

1. **Brand-first** - Spotify green (#1DB954) everywhere as accent
2. **Immersive dark** - Pure black background for content focus
3. **Album art dominant** - Large images, grid layouts
4. **Play button reveal** - Cards show play button on hover
5. **Now playing bar** - Persistent bottom player
6. **Rounded everything** - Cards, buttons, images all rounded

---

## CSS Variables (Complete Set)

```css
:root {
  /* Colors */
  --bg-primary: #000000;
  --bg-secondary: #121212;
  --bg-tertiary: #181818;
  --bg-elevated: #1F1F1F;
  --bg-highlight: #282828;

  --text-primary: #FFFFFF;
  --text-secondary: #B3B3B3;
  --text-tertiary: #6A6A6A;

  --border-subtle: rgba(255, 255, 255, 0.1);
  --border-default: rgba(255, 255, 255, 0.2);

  --accent-primary: #1DB954;
  --accent-hover: #1ED760;
  --accent-subtle: rgba(29, 185, 84, 0.15);

  /* Typography */
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
  --radius-md: 8px;
  --radius-lg: 12px;
  --radius-xl: 16px;
  --radius-full: 9999px;

  /* Shadows */
  --shadow-sm: 0 2px 4px rgba(0, 0, 0, 0.4);
  --shadow-md: 0 4px 12px rgba(0, 0, 0, 0.5);
  --shadow-lg: 0 8px 24px rgba(0, 0, 0, 0.6);
  --shadow-album: 0 4px 60px rgba(0, 0, 0, 0.6);

  /* Transitions */
  --duration-fast: 100ms;
  --duration-normal: 200ms;
  --ease-out: cubic-bezier(0.16, 1, 0.3, 1);
  --ease-spring: cubic-bezier(0.34, 1.56, 0.64, 1);
}
```

---

## Usage Tips

- Use pure black (#000000) as background
- Spotify green (#1DB954) for primary actions and accents
- Rounded cards with album art as primary visual
- Play button reveals on card hover
- Persistent bottom now-playing bar
- Bold typography with heavy weights (700-900)
- Playlist tracks with hover highlighting