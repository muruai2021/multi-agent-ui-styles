---
name: multi-agent-ui-styles
description: Use when 需要为AI生成的前端页面选择设计风格，并生成对应的Tailwind/CSS设计令牌。一键触发多Agent协作：主编解析需求→研究员分析产品类型→设计师推荐风格→开发者输出Tailwind配置/CSS变量/设计令牌。
version: 1.0.0
author: Muru AI
license: MIT
platforms: [linux, macos, windows]
type: workflow
metadata:
  hermes:
    tags: [multi-agent, ui-design, design-system, tailwind, css-tokens, design-reference]
    related_skills: [claude-design, popular-web-designs, multi-agent-skill-factory]
business_domain: 前端开发 · UI设计
complexity: medium
status: production
---

# Multi-Agent UI Styles — 多Agent协作设计风格工作流

> 输入一个产品描述，输出匹配的设计系统和可直接使用的Tailwind/CSS配置。

## 工作流概览

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

## Agent团队配置

| Agent | 输出 | 职责 |
|-------|------|------|
| 主编 | 任务调度+最终交付 | 解析需求、协调Agent、组装产出 |
| 研究员 | 产品分析报告 | 分析产品类型/用户/品牌调性，筛选候选设计系统 |
| 设计师 | 风格推荐报告 | 从候选中推荐最佳风格，解释理由 |
| 开发者 | Tailwind配置+CSS变量+设计令牌 | 输出可直接使用的代码 |

## 设计系统知识库

10个完整设计系统（references/目录下）：

| 风格 | 文件 | 品牌 | 核心调性 |
|------|------|------|----------|
| Linear | [linear.md](references/linear.md) | Linear, Vercel, Raycast | 极简深色科技 |
| Notion | [notion.md](references/notion.md) | Notion, Obsidian | 温暖极简创意 |
| Figma | [figma.md](references/figma.md) | Figma, Framer | 工具美学B&W |
| Supabase | [supabase.md](references/supabase.md) | Supabase, GitHub Desktop | 终端美学 |
| Stripe | [stripe.md](references/stripe.md) | Stripe, Square | 精致奢华金融 |
| Apple | [apple.md](references/apple.md) | Apple, macOS | 戏剧极简 |
| Airbnb | [airbnb.md](references/airbnb.md) | Airbnb, Vrbo | 温暖亲和旅行 |
| Spotify | [spotify.md](references/spotify.md) | Spotify, Discord | 品牌驱动沉浸 |
| IBM | [ibm.md](references/ibm.md) | IBM, Oracle | 企业规范Carbon |
| Luxury | [luxury-restraint.md](references/luxury-restraint.md) | Louis Vuitton | 奢侈克制象牙金 |

详细设计规范见各reference文件。

## 模板文件

| 文件 | 说明 |
|------|------|
| [references/agents.md](references/agents.md) | 4个Agent的系统提示词模板 |
| [references/pipeline-multi-agent.md](references/pipeline-multi-agent.md) | 多Agent流水线详解 |
| [references/style-match-matrix.md](references/style-match-matrix.md) | 产品类型→设计风格匹配矩阵 |
| [references/output-templates.md](references/output-templates.md) | Tailwind/CSS/Token输出模板 |
| [references/test_pool.md](references/test_pool.md) | 测试用例池 |

## 核心工作流

### 标准流程（主编调度4步）

```
Step 1: 用户提供产品描述
         ↓
Step 2: 研究员分析 → 产出产品分析报告（产品类型/用户/调性/候选系统）
         ↓
Step 3: 设计师推荐 → 产出风格推荐报告（最佳风格+理由+视觉方向）
         ↓
Step 4: 开发者输出 → 产出Tailwind配置 + CSS变量 + 设计令牌
         ↓
主编组装最终交付
```

## 快速查询模式

简单匹配场景（单Agent，无需完整流程）：

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

## 输出格式

开发者Agent输出三种格式：

### 1. Tailwind Config
```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: { /* 风格颜色 */ },
      fontFamily: { /* 字体 */ },
      borderRadius: { /* 圆角 */ },
    },
  },
}
```

### 2. CSS Variables
```css
:root {
  /* 颜色系统 */
  --bg-primary: #XXXXXX;
  --bg-secondary: #XXXXXX;
  --accent: #XXXXXX;
  /* ... */
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

## 触发词

**完整多Agent流程触发：**
- "帮我设计这个产品的UI风格"
- "这个产品适合什么设计系统"
- "生成Tailwind配置"

**快速查询触发：**
- "SaaS项目管理工具用什么风格"
- "设计师风格推荐"

## Not For
- 需要完整实现一个可用的前端页面 → 用 `claude-design`
- 需要编写后端逻辑或API → 不是UI设计场景
- 需要品牌Logo或图标资源 → 只提供设计规范

## 目录结构

```
multi-agent-ui-styles/
├── SKILL.md                  ← 主入口（主编调度）
├── config.yaml               ← 运行时配置
├── metadata.yaml            ← 元数据
└── references/
    ├── linear.md             ← 10个设计系统文件
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
    ├── agents.md             ← 4个Agent模板
    ├── pipeline-multi-agent.md ← 多Agent流水线详解
    ├── style-match-matrix.md  ← 产品→风格匹配矩阵
    ├── output-templates.md    ← 输出模板
    └── test_pool.md          ← 测试用例池
```

## 验证清单

- [ ] description以"Use when"开头
- [ ] frontmatter包含完整字段（含type: workflow）
- [ ] references/目录包含agents.md + pipeline-multi-agent.md
- [ ] test_pool.md在references/目录下
- [ ] 4个Agent角色定义清晰
- [ ] 设计系统知识库完整（10个文件）
