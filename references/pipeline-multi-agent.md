# Multi-Agent UI Styles 流水线详解（主编调度手册）

> 本文档是 [SKILL.md](SKILL.md) 的完整流水线细节，供主编调度时参考。

---

## 流水线概览

```
用户提供产品描述
         ↓
主编解析，判断场景
         ↓
   ┌─────┴─────┐
   ↓           ↓
简单场景    复杂场景
直接推荐    完整流程
   ↓           ↓
   直接交付    研究员分析 → 设计师推荐 → 开发者输出
                  ↓
             主编组装最终交付
```

---

## 主编调度决策树

```
用户输入：[产品描述]

1. 是否提到具体竞品/品牌？
   是 → 直接匹配该品牌的设计系统
   否 → 继续判断

2. 是否要求生成Tailwind/CSS配置？
   是 → 完整流程（研究员→设计师→开发者）
   否 → 快速推荐（主编直接推荐风格）

3. 产品描述是否模糊/多选项？
   是 → 完整流程，研究员深度分析
   否 → 根据明确特征快速匹配
```

---

## 简单流程（快速推荐）

主编直接根据产品特征查表推荐：

```markdown
## 快速风格推荐

**产品**：[产品描述]
**推荐风格**：Linear

**推荐理由**：
1. 极简深色科技风，适合SaaS产品
2. 精准感、高端感，与项目管理工具调性匹配
3. Linear本身即是SaaS项目管理工具的行业标杆

**参考品牌**：Linear, Vercel, Raycast

**核心设计元素**：
- 深黑背景 #0D0D0F
- 紫色强调 #8B5CF6
- 无衬线字体 Inter
- 8px基础网格

如需生成Tailwind配置，请说"生成Tailwind配置"。
```

---

## 完整流程（主编调度4步）

### Step 1: 主编解析需求

主编收到产品描述后，解析关键特征并下达任务给研究员：

```markdown
## 研究员任务

请分析以下产品，产出产品分析报告：

**产品描述**：
[用户描述]

**分析要求**：
1. 提取产品类型、目标用户、品牌调性
2. 从10个设计系统中筛选2-3个候选
3. 每个候选给出匹配度分数和理由

**10个设计系统**：
Linear, Notion, Figma, Supabase, Stripe, Apple, Airbnb, Spotify, IBM, Luxury
```

### Step 2: 研究员产出分析报告

研究员分析后，主编将报告转发给设计师：

```markdown
## 设计师任务

请根据研究员的产品分析报告，推荐最佳设计系统：

**产品分析报告**：
[研究员产出]

**推荐要求**：
1. 从候选中选出最佳风格
2. 给出推荐理由（为什么这个最适合）
3. 描述视觉方向（色彩/字体/间距/组件风格）
4. 如需多风格组合，说明如何组合

**输出格式**：
- 推荐风格：[风格名]
- 推荐理由：[3条理由]
- 视觉方向：[色彩/字体/间距/组件描述]
- 设计系统详情：见references/[风格名].md
```

### Step 3: 设计师产出推荐报告

设计师完成后，主编将报告转发给开发者：

```markdown
## 开发者任务

请根据设计师的风格推荐，生成可直接使用的代码：

**风格推荐**：
[设计师产出]

**设计系统详情**：
请读取 references/[风格名].md 获取完整设计规范

**输出要求**：
1. Tailwind Config（tailwind.config.js格式）
2. CSS Variables（:root格式）
3. Design Tokens（JSON格式）

**代码规范**：
- 变量命名：语义化，如 --color-primary, --spacing-md
- 颜色格式：HEX（如 #0D0D0F）
- 间距单位：4px网格（如 4, 8, 12, 16, 24, 32）
```

### Step 4: 开发者输出代码

主编组装最终交付物，输出给用户。

---

## 输出格式规范

### Tailwind Config 格式

```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ['./src/**/*.{html,js}'],
  theme: {
    extend: {
      colors: {
        // 背景色
        'bg-primary': '#0D0D0F',
        'bg-secondary': '#141416',
        'bg-tertiary': '#1A1A1D',
        'bg-elevated': '#222225',
        // 文字色
        'text-primary': '#FFFFFF',
        'text-secondary': '#A1A1A1',
        'text-tertiary': '#6B6B6B',
        // 强调色
        'accent': '#8B5CF6',
        // 语义色
        'success': '#3ECF8E',
        'warning': '#F59E0B',
        'error': '#EF4444',
        'info': '#3B82F6',
      },
      fontFamily: {
        sans: ['Inter', 'system-ui', 'sans-serif'],
        mono: ['JetBrains Mono', 'monospace'],
      },
      borderRadius: {
        'sm': '4px',
        'DEFAULT': '6px',
        'md': '8px',
        'lg': '12px',
        'xl': '16px',
      },
      boxShadow: {
        'sm': '0 1px 2px rgba(0, 0, 0, 0.3)',
        'DEFAULT': '0 2px 8px rgba(0, 0, 0, 0.4)',
        'lg': '0 4px 16px rgba(0, 0, 0, 0.5)',
      },
    },
  },
}
```

### CSS Variables 格式

```css
:root {
  /* Background */
  --bg-primary: #0D0D0F;
  --bg-secondary: #141416;
  --bg-tertiary: #1A1A1D;
  --bg-elevated: #222225;

  /* Text */
  --text-primary: #FFFFFF;
  --text-secondary: #A1A1A1;
  --text-tertiary: #6B6B6B;

  /* Accent */
  --accent: #8B5CF6;
  --accent-hover: #7C3AED;

  /* Semantic */
  --success: #3ECF8E;
  --warning: #F59E0B;
  --error: #EF4444;
  --info: #3B82F6;

  /* Border */
  --border-subtle: rgba(255, 255, 255, 0.08);
  --border-default: rgba(255, 255, 255, 0.12);
  --border-strong: rgba(255, 255, 255, 0.2);

  /* Spacing */
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-6: 24px;
  --space-8: 32px;
  --space-12: 48px;

  /* Radius */
  --radius-sm: 4px;
  --radius-md: 6px;
  --radius-lg: 8px;

  /* Font */
  --font-sans: 'Inter', system-ui, sans-serif;
  --font-mono: 'JetBrains Mono', monospace;
}
```

### Design Tokens 格式

```json
{
  "color": {
    "bg": {
      "primary": { "value": "#0D0D0F", "description": "主背景" },
      "secondary": { "value": "#141416", "description": "卡片背景" },
      "tertiary": { "value": "#1A1A1D", "description": "悬浮背景" }
    },
    "text": {
      "primary": { "value": "#FFFFFF", "description": "主文字" },
      "secondary": { "value": "#A1A1A1", "description": "次要文字" }
    },
    "accent": {
      "default": { "value": "#8B5CF6", "description": "品牌强调色" }
    }
  },
  "spacing": {
    "1": { "value": "4px" },
    "2": { "value": "8px" },
    "3": { "value": "12px" },
    "4": { "value": "16px" },
    "6": { "value": "24px" },
    "8": { "value": "32px" }
  },
  "typography": {
    "fontFamily": {
      "sans": { "value": "Inter, system-ui, sans-serif" }
    },
    "fontSize": {
      "xs": { "value": "12px" },
      "sm": { "value": "14px" },
      "base": { "value": "16px" },
      "lg": { "value": "18px" },
      "xl": { "value": "20px" },
      "2xl": { "value": "24px" },
      "3xl": { "value": "30px" }
    }
  },
  "radius": {
    "sm": { "value": "4px" },
    "md": { "value": "6px" },
    "lg": { "value": "8px" }
  }
}
```

---

## 执行示例

**场景：** 用户需要为B2B SaaS项目管理工具选择设计风格

```
用户：帮我设计一个B2B SaaS项目管理工具的UI风格

① 主编解析：
   产品类型：SaaS
   目标用户：企业/团队
   品牌调性：专业、高效、科技感
   → 启动完整流程

② 研究员分析：
   候选1：Linear（95%匹配）
   候选2：IBM（80%匹配）
   候选3：Notion（60%匹配）

③ 设计师推荐：
   推荐：Linear
   理由：SaaS项目管理标杆，极简深色科技风

④ 开发者输出：
   Tailwind配置 + CSS变量 + Design Tokens

⑤ 主编交付：
   完整风格推荐报告 + 代码输出
```
