# Multi-Agent UI Styles — 多Agent协作设计风格工作流

> 输入一个产品描述，输出匹配的设计系统和可直接使用的Tailwind/CSS配置。

## 概述

Multi-Agent UI Styles 是一个AI驱动的设计风格推荐和实现系统。通过主编调度研究员分析产品类型，设计师推荐风格，开发者输出Tailwind配置/CSS变量/设计令牌，实现从产品描述到完整设计系统的端到端生成。

**核心特性：**
- 内置10个全球知名设计系统知识库
- 智能产品类型→设计风格匹配
- 直接输出可用的Tailwind/CSS代码
- 支持快速查询和完整流程两种模式

## 工作流程

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

## Agent团队

| Agent | 输出 | 职责 |
|-------|------|------|
| 主编 | 任务调度+最终交付 | 解析需求、协调Agent、组装产出 |
| 研究员 | 产品分析报告 | 分析产品类型/用户/品牌调性，筛选候选设计系统 |
| 设计师 | 风格推荐报告 | 从候选中推荐最佳风格，解释理由 |
| 开发者 | Tailwind配置+CSS变量+设计令牌 | 输出可直接使用的代码 |

## 设计系统知识库（10个）

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

## 快速查询参考

```
产品类型 → 推荐风格
SaaS/Tech → Linear, Supabase
Creative/Tools → Figma, Notion
Finance/Payment → Stripe, IBM
Travel/Lifestyle → Airbnb, Luxury
Entertainment → Spotify
Developer Tools → Linear, Supabase, IBM
```

## 输出格式

### Tailwind Config
```javascript
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

### CSS Variables
```css
:root {
  --bg-primary: #XXXXXX;
  --bg-secondary: #XXXXXX;
  --accent: #XXXXXX;
}
```

### Design Tokens
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
    ├── agents.md             ← 4个Agent模板
    ├── pipeline-multi-agent.md ← 多Agent流水线详解
    ├── style-match-matrix.md  ← 产品→风格匹配矩阵
    ├── output-templates.md    ← 输出模板
    └── test_pool.md          ← 测试用例池
```

## License

MIT
