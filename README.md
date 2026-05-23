# Multi-Agent UI Styles — 多Agent协作设计风格工作流

> 输入一个产品描述，输出匹配的设计系统和可直接使用的Tailwind/CSS配置。

---

# English Version

# Multi-Agent UI Styles — Multi-Agent Design Style Workflow

> Input a product description, output a matching design system and ready-to-use Tailwind/CSS configuration.

## Overview

Multi-Agent UI Styles is an AI-driven design style recommendation and implementation system. Through Editor-in-Chief orchestrating Researcher to analyze product type, Designer to recommend style, Developer to output Tailwind config/CSS variables/design tokens, it achieves end-to-end generation from product description to complete design system.

**Core Features:**
- Built-in knowledge base of 10 globally known design systems
- Intelligent product type → design style matching
- Direct output of usable Tailwind/CSS code
- Supports both quick query and full workflow modes

## Workflow

```
User says "Help me design UI for a SaaS project management tool"
         ↓
Editor receives, parses product type
         ↓
   ┌─────┴─────┐
   ↓           ↓
 Researcher   Designer
 analyzes    recommends 2-3
 product     candidate styles
 type+users
   ↓           ↓
   └─────┬─────┘
         ↓
Developer outputs
Tailwind config + CSS variables + design tokens
         ↓
Editor assembles final deliverable
```

## Agent Team

| Agent | Output | Responsibilities |
|-------|--------|------------------|
| Editor-in-Chief | Task scheduling + final delivery | Parse requirements, coordinate agents, assemble output |
| Researcher | Product analysis report | Analyze product type/users/brand tone, filter candidate design systems |
| Designer | Style recommendation report | Recommend best style from candidates, explain reasoning |
| Developer | Tailwind config + CSS variables + design tokens | Output code ready to use |

## Design System Knowledge Base (10 Systems)

| Style | Brands | Core Tone |
|-------|--------|-----------|
| Linear | Linear, Vercel, Raycast | Minimal dark tech |
| Notion | Notion, Obsidian | Warm minimal creative |
| Figma | Figma, Framer | Tool aesthetics B&W |
| Supabase | Supabase, GitHub Desktop | Terminal aesthetics |
| Stripe | Stripe, Square | Refined luxury finance |
| Apple | Apple, macOS | Dramatic minimal |
| Airbnb | Airbnb, Vrbo | Warm approachable travel |
| Spotify | Spotify, Discord | Brand-driven immersive |
| IBM | IBM, Oracle | Enterprise standard Carbon |
| Luxury | Louis Vuitton | Luxury restraint ivory gold |

## Quick Query Reference

```
Product Type → Recommended Style
SaaS/Tech → Linear, Supabase
Creative/Tools → Figma, Notion
Finance/Payment → Stripe, IBM
Travel/Lifestyle → Airbnb, Luxury
Entertainment → Spotify
Developer Tools → Linear, Supabase, IBM
```

**Note**: Quick query only returns style recommendation. To generate Tailwind/CSS config, trigger full multi-agent workflow.

## Output Formats

### 1. Tailwind Config
```javascript
module.exports = {
  theme: {
    extend: {
      colors: { /* style colors */ },
      fontFamily: { /* fonts */ },
      borderRadius: { /* radius */ },
    },
  },
}
```

### 2. CSS Variables
```css
:root {
  --bg-primary: #XXXXXX;
  --bg-secondary: #XXXXXX;
  --accent: #XXXXXX;
}
```

### 3. Design Tokens
```json
{
  "color": { "...token": "value" },
  "spacing": { "...token": "value" },
  "typography": { "...token": "value" }
}
```

## Trigger Words

**Full multi-agent workflow triggers:**
- "帮我设计这个产品的UI风格" / "Help me design this product's UI style"
- "这个产品适合什么设计系统" / "What design system fits this product"
- "生成Tailwind配置" / "Generate Tailwind config"

**Quick query triggers:**
- "SaaS项目管理工具用什么风格" / "What style for SaaS project management tool"
- "设计师风格推荐" / "Designer style recommendation"

## Directory Structure

```
multi-agent-ui-styles/
├── SKILL.md                  ← Main entry (Editor-in-Chief scheduling)
├── config.yaml               ← Runtime configuration
├── metadata.yaml            ← Metadata
└── references/
    ├── linear.md             ← 10 design system files
    ├── notion.md
    ├── figma.md
    ├── apple.md
    ├── airbnb.md
    ├── spotify.md
    ├── stripe.md
    ├── supabase.md
    ├── ibm.md
    ├── luxury-restraint.md
    ├── SOP.md
    ├── agents.md             ← 4 Agent templates
    ├── pipeline-multi-agent.md ← Multi-agent pipeline details
    ├── style-match-matrix.md  ← Product → style matching matrix
    ├── output-templates.md    ← Output templates
    └── test_pool.md          ← Test case pool
```

## Related Skills

- `claude-design` - Complete front-end page implementation
- `popular-web-designs` - Popular design references
- `multi-agent-skill-factory` - Multi-agent SOP packaging

## License

MIT
