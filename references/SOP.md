# UI Styles Skill — 原始SOP文档

> 记录UI设计风格系统的原始制作流程和数据来源

---

## 背景

AI生成前端页面时，需要准确的设计风格参考。现有的AI模型在生成UI时倾向于使用通用、模糊的设计系统，缺乏具体品牌的设计语言一致性。本技能将10个全球知名科技公司/产品的设计系统文档化，为AI生成提供精确的风格参照。

---

## 数据来源

每个设计系统的数据来源如下：

| 设计系统 | 来源 | 官方文档 |
|----------|------|----------|
| Linear | Linear官方设计系统 | https://linear.design |
| Figma | Figma官方设计指南 | https://figma.com |
| Apple | Apple Human Interface Guidelines | https://developer.apple.com/design |
| Stripe | Stripe Design System | https://stripe.com/design-system |
| Notion | Notion官方设计语言 | https://notion.so |
| Airbnb | Airbnb Design | https://airbnb.design |
| Spotify | Spotify Design | https://spotify.design |
| IBM | Carbon Design System | https://carbondesignsystem.com |
| Supabase | Supabase Brand | https://supabase.com/brand |
| Luxury | 奢侈品行业设计研究 | 内部研究整理 |

---

## 制作流程

### Step 1: 信息收集

对每个设计系统，收集以下信息：
- 主色调、辅色调、强调色
- 背景色阶（Primary/Secondary/Tertiary）
- 文字色阶（Primary/Secondary/Tertiary/Disabled）
- 边框色阶
- Semantic颜色（Success/Warning/Error/Info）
- 字体家族（Display/Body/Code）
- 字体大小阶梯
- 间距系统（4px/8px基准）
- 圆角系统
- 阴影系统
- 动效时序和缓动曲线
- 组件模式（Button/Input/Card/Modal等）
- Dark Mode完整变量集
- Light Mode完整变量集

### Step 2: 结构化文档

每个设计系统的文档结构统一为：
1. **Frontmatter**：name、description、type
2. **Overview**：品牌描述、适合场景、情感基调
3. **Color Palette**：完整CSS变量集
4. **Typography**：字体系统
5. **Spacing**：间距规范
6. **Border Radius**：圆角规范
7. **Shadow System**：阴影规范
8. **Components**：组件模式
9. **Motion**：动效规范
10. **Dark Mode** + **Light Mode**双版本
11. **Tailwind Config**：可直接使用的Tailwind扩展

### Step 3: 分类组织

在SKILL.md中按风格特征分为四类：
- **Dark & Tech**：Linear、Supabase、Spotify
- **Light & Warm**：Notion、Airbnb、Luxury
- **Professional & Enterprise**：Stripe、IBM
- **Tool & Functional**：Figma、Apple

### Step 4: 质量验证

- 每个设计系统CSS变量覆盖率≥90%
- 每个系统必须有Dark Mode + Light Mode双版本
- 每个系统必须有Tailwind配置片段
- CSS变量命名符合`--category-property`规范

---

## 文件结构

```
ui-10 styles/
├── SKILL.md              # 核心技能定义
├── metadata.yaml         # 元数据
├── SOP.md                # 本文档
├── test_cases.md         # 测试用例
├── config.yaml           # 运行时配置
├── linear.md             # Linear设计系统
├── figma.md              # Figma设计系统
├── apple.md              # Apple HIG
├── stripe.md             # Stripe设计系统
├── notion.md             # Notion设计语言
├── airbnb.md             # Airbnb设计系统
├── spotify.md            # Spotify品牌设计
├── ibm.md                # IBM Carbon设计系统
├── supabase.md           # Supabase品牌设计
└── luxury-restraint.md   # 奢侈品克制设计
```

---

## 更新日志

| 日期 | 版本 | 更新内容 |
|------|------|----------|
| 2026-05-21 | 1.0.0 | 初始版本，10个设计系统全部完成 |
| 2026-05-22 | 1.0.1 | 修复SKILL.md frontmatter、添加metadata.yaml、test_cases.md、SOP.md、config.yaml |
