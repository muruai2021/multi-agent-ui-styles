# Multi-Agent UI Styles

[English](#english) | [中文](#中文)

---

## English

### Overview

**Multi-Agent UI Styles** is an AI-driven design style recommendation and implementation system. Through Editor-in-Chief orchestrating Researcher to analyze product type, Designer to recommend style, Developer to output Tailwind config/CSS variables/design tokens, it achieves end-to-end generation from product description to complete design system.

**Core Features:**
- Built-in knowledge base of 10 globally known design systems
- Intelligent product type → design style matching
- Direct output of usable Tailwind/CSS code
- Supports both quick query and full workflow modes

### Workflow

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

### Agent Team

| Agent | Output | Responsibilities |
|-------|--------|------------------|
| Editor-in-Chief | Task scheduling + final delivery | Parse requirements, coordinate agents, assemble output |
| Researcher | Product analysis report | Analyze product type/users/brand tone, filter candidates |
| Designer | Style recommendation report | Recommend best style from candidates, explain reasoning |
| Developer | Tailwind config + CSS variables + tokens | Output code ready to use |

### Design System Knowledge Base (10 Systems)

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

### Quick Query Reference

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

---

## 中文

### 概述

**Multi-Agent UI Styles** 是一个AI驱动的设计风格推荐和实现系统。通过主编调度研究员分析产品类型，设计师推荐风格，开发者输出Tailwind配置/CSS变量/设计令牌，实现从产品描述到完整设计系统的端到端生成。

**核心特性：**
- 内置10个全球知名设计系统知识库
- 智能产品类型→设计风格匹配
- 直接输出可用的Tailwind/CSS代码
- 支持快速查询和完整流程两种模式

### 工作流程

```
用户说"帮我设计一个SaaS项目管理工具的UI"
         ↓
主编接收，解析产品类型
         ↓
   ┌─────┴─────┐
   ↓           ↓
研究员        设计师
分析产品     候选风格
类型+用户    2-3个
   ↓           ↓
   └─────┬─────┘
         ↓
开发者输出
Tailwind配置 + CSS变量 + 设计令牌
         ↓
主编组装最终交付物
```

### Agent团队

| Agent | 输出 | 职责 |
|-------|------|------|
| 主编 | 任务调度+最终交付 | 解析需求、协调Agent、组装产出 |
| 研究员 | 产品分析报告 | 分析产品类型/用户/品牌调性，筛选候选设计系统 |
| 设计师 | 风格推荐报告 | 从候选中推荐最佳风格，解释理由 |
| 开发者 | Tailwind配置+CSS变量+设计令牌 | 输出可直接使用的代码 |

### 设计系统知识库（10个）

| 风格 | 品牌 | 核心调性 |
|------|------|----------|
| Linear | Linear, Vercel, Raycast | 极简深色科技 |
| Notion | Notion, Obsidian | 温暖极简创意 |
| Figma | Figma, Framer | 工具美学B&W |
| Supabase | Supabase, GitHub Desktop | 终端美学 |
| Stripe | Stripe, Square | 精致奢华金融 |
| Apple | Apple, macOS | 戏剧极简 |
| Airbnb | Airbnb, Vrbo | 温暖亲和旅行 |
| Spotify | Spotify, Discord | 品牌驱动沉浸 |
| IBM | IBM, Oracle | 企业规范Carbon |
| Luxury | Louis Vuitton | 奢侈克制象牙金 |

### 快速查询参考

```
产品类型 → 推荐风格
SaaS/Tech → Linear, Supabase
Creative/Tools → Figma, Notion
Finance/Payment → Stripe, IBM
Travel/Lifestyle → Airbnb, Luxury
Entertainment → Spotify
Developer Tools → Linear, Supabase, IBM
```

**注意**：快速查询仅返回风格推荐。需生成Tailwind/CSS配置时，触发完整多Agent流程。

---

MIT License