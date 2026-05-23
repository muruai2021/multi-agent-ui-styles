# Multi-Agent UI Styles — 测试用例池

**技能名称**：multi-agent-ui-styles
**测试日期**：2026-05-22
**测试版本**：v1.1.0（多Agent协作版）

---

## 测试用例

### 语法验证

| 用例ID | 测试项 | 输入 | 预期结果 | 通过条件 |
|--------|--------|------|----------|----------|
| TC-SYNTAX-001 | frontmatter格式 | SKILL.md内容 | YAML格式正确 | 以`---`开头和结尾 |
| TC-SYNTAX-002 | 必需字段 | frontmatter | 包含name/description/version/author/license/platforms/type/metadata | 8个字段都存在 |
| TC-SYNTAX-003 | description长度 | description内容 | ≤1024字符 | `len <= 1024` |
| TC-SYNTAX-004 | description开头 | description内容 | 以"Use when"开头 | startswith("Use when") |
| TC-SYNTAX-005 | type字段 | frontmatter.metadata | type为workflow | `type == "workflow"` |
| TC-SYNTAX-006 | references/目录 | 目录结构 | 包含agents.md/pipeline-multi-agent.md/test_pool.md | 3个核心文件存在 |

### 功能测试

| 用例ID | 测试项 | 输入 | 预期结果 | 通过条件 |
|--------|--------|------|----------|----------|
| TC-FUNC-001 | 快速推荐 | "SaaS项目管理工具用什么风格" | 直接返回Linear推荐 | 主编直接输出，不调用研究员 |
| TC-FUNC-002 | 竞品匹配 | "Stripe风格" | 返回Stripe设计系统 | 主编直接匹配 |
| TC-FUNC-003 | 完整流程触发 | "帮我设计一个B2B电商平台的UI" | 主编→研究员→设计师→开发者 | 完整4步流程执行 |
| TC-FUNC-004 | 研究员分析 | 提供产品描述 | 产出产品分析报告 | 包含产品类型/用户/调性/候选 |
| TC-FUNC-005 | 设计师推荐 | 研究员产出 | 产出风格推荐报告 | 包含推荐风格/理由/视觉方向 |
| TC-FUNC-006 | 开发者输出 | 设计师产出 | 产出Tailwind+CSS+Token | 三种格式代码都有 |

### 设计系统知识库测试

| 用例ID | 测试项 | 输入 | 预期结果 | 通过条件 |
|--------|--------|------|----------|----------|
| TC-KB-001 | 10个设计系统 | 检查references/目录 | 10个md文件都存在 | 10个文件 |
| TC-KB-002 | Linear文件完整性 | linear.md | 包含Color/Typography/Spacing/Radius/Shadow/Components | 6个章节 |
| TC-KB-003 | Notion文件完整性 | notion.md | 同上 | 6个章节 |
| TC-KB-004 | CSS变量格式 | linear.md | CSS变量格式正确 | var(--xxx)格式 |
| TC-KB-005 | Tailwind配置 | linear.md | 包含tailwind.config.js片段 | 符合标准格式 |

### 输出格式测试

| 用例ID | 测试项 | 输入 | 预期结果 | 通过条件 |
|--------|--------|------|----------|----------|
| TC-OUT-001 | Tailwind Config格式 | 开发者输出 | 符合module.exports结构 | 有colors/fontFamily/borderRadius |
| TC-OUT-002 | CSS Variables格式 | 开发者输出 | 符合:root语法 | --variable-name: #hex |
| TC-OUT-003 | Design Tokens格式 | 开发者输出 | 符合JSON schema | 有meta/name/color/spacing |

### 边界测试

| 用例ID | 测试项 | 输入 | 预期结果 | 通过条件 |
|--------|--------|------|----------|----------|
| TC-BOUND-001 | 模糊产品描述 | "做一个App" | 主编触发完整流程 | 研究员深度分析 |
| TC-BOUND-002 | 多个竞品 | "类似Notion和Linear之间的风格" | 主编推荐融合方案 | 给出组合建议 |
| TC-BOUND-003 | 不存在的设计系统 | "找一个XXX风格" | 返回10个可用系统列表 | 不崩溃 |

---

## 测试报告模板

```markdown
# 测试报告

**技能名称**：multi-agent-ui-styles
**版本**：v1.1.0
**测试日期**：[日期]

## 测试结果汇总

| 测试类型 | 用例数 | 通过 | 失败 | 通过率 |
|----------|--------|------|------|--------|
| 语法验证 | X | X | X | X% |
| 功能测试 | X | X | X | X% |
| 知识库测试 | X | X | X | X% |
| 输出格式测试 | X | X | X | X% |
| 边界测试 | X | X | X | X% |
| **总计** | **X** | **X** | **X** | **X%** |

## 失败用例详情

### TC-XXX-XXX
- **测试项**：[名称]
- **预期**：[预期结果]
- **实际**：[实际结果]
- **修复建议**：[建议]

## 结论

- [ ] 语法验证通过
- [ ] 功能测试通过
- [ ] 知识库完整
- [ ] 输出格式正确
- [ ] **可进入评审阶段**
```

---

## 已发现问题追踪

| 问题 | 严重程度 | 状态 | 备注 |
|------|----------|------|------|
| test_pool.md在根目录 | P0 | ✅ 已修复 | 已移至references/ |
| 缺type:workflow字段 | P0 | ✅ 已修复 | frontmatter已添加 |
| 原版非多Agent工作流 | P0 | ✅ 已修复 | 重构为4Agent协作 |
| 缺agents.md模板 | P0 | ✅ 已修复 | 已创建4个Agent模板 |
| 缺pipeline-multi-agent.md | P0 | ✅ 已修复 | 已创建主编调度手册 |
