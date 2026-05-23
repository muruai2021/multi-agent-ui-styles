<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Multi-Agent UI Styles</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif; line-height: 1.6; color: #24292e; background: #f6f8fa; padding: 20px; }
        .container { max-width: 900px; margin: 0 auto; background: #fff; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1); overflow: hidden; }
        .header { background: linear-gradient(135deg, #fc466b 0%, #3f5efb 100%); color: #fff; padding: 40px; text-align: center; }
        .header h1 { font-size: 2.5em; margin-bottom: 10px; }
        .header p { font-size: 1.2em; opacity: 0.9; }
        .lang-switch { display: flex; justify-content: center; gap: 10px; padding: 20px; background: #f6f8fa; border-bottom: 1px solid #e1e4e8; }
        .lang-btn { padding: 10px 30px; border: 2px solid #3f5efb; background: #fff; color: #3f5efb; border-radius: 25px; cursor: pointer; font-weight: 600; transition: all 0.3s; }
        .lang-btn:hover { background: #3f5efb; color: #fff; }
        .lang-btn.active { background: #3f5efb; color: #fff; }
        .content { padding: 40px; }
        .content[lang="en"] { display: none; }
        h2 { color: #3f5efb; margin: 30px 0 15px; padding-bottom: 10px; border-bottom: 2px solid #3f5efb; }
        h3 { color: #333; margin: 20px 0 10px; }
        p { margin: 15px 0; }
        ul { margin: 15px 0; padding-left: 25px; }
        li { margin: 8px 0; }
        code { background: #f6f8fa; padding: 2px 6px; border-radius: 3px; font-family: Monaco, monospace; color: #e74c3c; }
        pre { background: #1e1e1e; color: #d4d4d4; padding: 20px; border-radius: 8px; overflow-x: auto; margin: 15px 0; font-size: 14px; }
        pre code { background: none; color: inherit; }
        table { width: 100%; border-collapse: collapse; margin: 15px 0; }
        th, td { border: 1px solid #e1e4e8; padding: 12px; text-align: left; }
        th { background: #3f5efb; color: #fff; }
        tr:nth-child(even) { background: #f6f8fa; }
        .badge { display: inline-block; padding: 4px 12px; border-radius: 20px; font-size: 0.85em; margin: 2px; }
        .badge-primary { background: #3f5efb; color: #fff; }
        .badge-success { background: #27ae60; color: #fff; }
        .footer { text-align: center; padding: 30px; color: #666; border-top: 1px solid #e1e4e8; }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>Multi-Agent UI Styles</h1>
            <p>多Agent协作设计风格工作流 | Multi-Agent Design Style Workflow</p>
        </div>
        <div class="lang-switch">
            <button class="lang-btn active" onclick="switchLang('zh')">中文</button>
            <button class="lang-btn" onclick="switchLang('en')">English</button>
        </div>
        <div class="content" lang="zh">
            <h2>概述</h2>
            <p>Multi-Agent UI Styles 是一个AI驱动的设计风格推荐和实现系统。通过主编调度研究员分析产品类型，设计师推荐风格，开发者输出Tailwind配置/CSS变量/设计令牌，实现从产品描述到完整设计系统的端到端生成。</p>
            <h3>核心特性</h3>
            <ul>
                <li>内置10个全球知名设计系统知识库</li>
                <li>智能产品类型→设计风格匹配</li>
                <li>直接输出可用的Tailwind/CSS代码</li>
                <li>支持快速查询和完整流程两种模式</li>
            </ul>
            <h2>工作流程</h2>
            <pre><code>用户说"帮我设计一个SaaS项目管理工具的UI"
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
主编组装最终交付物</code></pre>
            <h2>Agent团队</h2>
            <table>
                <tr><th>Agent</th><th>输出</th><th>职责</th></tr>
                <tr><td>主编</td><td>任务调度+最终交付</td><td>解析需求、协调Agent、组装产出</td></tr>
                <tr><td>研究员</td><td>产品分析报告</td><td>分析产品类型/用户/品牌调性，筛选候选设计系统</td></tr>
                <tr><td>设计师</td><td>风格推荐报告</td><td>从候选中推荐最佳风格，解释理由</td></tr>
                <tr><td>开发者</td><td>Tailwind配置+CSS变量+设计令牌</td><td>输出可直接使用的代码</td></tr>
            </table>
            <h2>设计系统知识库（10个）</h2>
            <table>
                <tr><th>风格</th><th>品牌</th><th>核心调性</th></tr>
                <tr><td>Linear</td><td>Linear, Vercel, Raycast</td><td>极简深色科技</td></tr>
                <tr><td>Notion</td><td>Notion, Obsidian</td><td>温暖极简创意</td></tr>
                <tr><td>Figma</td><td>Figma, Framer</td><td>工具美学B&W</td></tr>
                <tr><td>Supabase</td><td>Supabase, GitHub Desktop</td><td>终端美学</td></tr>
                <tr><td>Stripe</td><td>Stripe, Square</td><td>精致奢华金融</td></tr>
                <tr><td>Apple</td><td>Apple, macOS</td><td>戏剧极简</td></tr>
                <tr><td>Airbnb</td><td>Airbnb, Vrbo</td><td>温暖亲和旅行</td></tr>
                <tr><td>Spotify</td><td>Spotify, Discord</td><td>品牌驱动沉浸</td></tr>
                <tr><td>IBM</td><td>IBM, Oracle</td><td>企业规范Carbon</td></tr>
                <tr><td>Luxury</td><td>Louis Vuitton</td><td>奢侈克制象牙金</td></tr>
            </table>
            <h2>快速查询参考</h2>
            <pre><code>产品类型 → 推荐风格
SaaS/Tech → Linear, Supabase
Creative/Tools → Figma, Notion
Finance/Payment → Stripe, IBM
Travel/Lifestyle → Airbnb, Luxury
Entertainment → Spotify
Developer Tools → Linear, Supabase, IBM</code></pre>
            <p><span class="badge badge-primary">注意：快速查询仅返回风格推荐。需生成Tailwind/CSS配置时，触发完整多Agent流程。</span></p>
        </div>
        <div class="content" lang="en">
            <h2>Overview</h2>
            <p>Multi-Agent UI Styles is an AI-driven design style recommendation and implementation system. Through Editor-in-Chief orchestrating Researcher to analyze product type, Designer to recommend style, Developer to output Tailwind config/CSS variables/design tokens, it achieves end-to-end generation from product description to complete design system.</p>
            <h3>Core Features</h3>
            <ul>
                <li>Built-in knowledge base of 10 globally known design systems</li>
                <li>Intelligent product type to design style matching</li>
                <li>Direct output of usable Tailwind/CSS code</li>
                <li>Supports both quick query and full workflow modes</li>
            </ul>
            <h2>Workflow</h2>
            <pre><code>User says "Help me design UI for a SaaS project management tool"
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
Editor assembles final deliverable</code></pre>
            <h2>Agent Team</h2>
            <table>
                <tr><th>Agent</th><th>Output</th><th>Responsibilities</th></tr>
                <tr><td>Editor-in-Chief</td><td>Task scheduling + final delivery</td><td>Parse requirements, coordinate agents, assemble output</td></tr>
                <tr><td>Researcher</td><td>Product analysis report</td><td>Analyze product type/users/brand tone, filter candidates</td></tr>
                <tr><td>Designer</td><td>Style recommendation report</td><td>Recommend best style from candidates, explain reasoning</td></tr>
                <tr><td>Developer</td><td>Tailwind config + CSS variables + tokens</td><td>Output code ready to use</td></tr>
            </table>
            <h2>Design System Knowledge Base (10 Systems)</h2>
            <table>
                <tr><th>Style</th><th>Brands</th><th>Core Tone</th></tr>
                <tr><td>Linear</td><td>Linear, Vercel, Raycast</td><td>Minimal dark tech</td></tr>
                <tr><td>Notion</td><td>Notion, Obsidian</td><td>Warm minimal creative</td></tr>
                <tr><td>Figma</td><td>Figma, Framer</td><td>Tool aesthetics B&W</td></tr>
                <tr><td>Supabase</td><td>Supabase, GitHub Desktop</td><td>Terminal aesthetics</td></tr>
                <tr><td>Stripe</td><td>Stripe, Square</td><td>Refined luxury finance</td></tr>
                <tr><td>Apple</td><td>Apple, macOS</td><td>Dramatic minimal</td></tr>
                <tr><td>Airbnb</td><td>Airbnb, Vrbo</td><td>Warm approachable travel</td></tr>
                <tr><td>Spotify</td><td>Spotify, Discord</td><td>Brand-driven immersive</td></tr>
                <tr><td>IBM</td><td>IBM, Oracle</td><td>Enterprise standard Carbon</td></tr>
                <tr><td>Luxury</td><td>Louis Vuitton</td><td>Luxury restraint ivory gold</td></tr>
            </table>
            <h2>Quick Query Reference</h2>
            <pre><code>Product Type → Recommended Style
SaaS/Tech → Linear, Supabase
Creative/Tools → Figma, Notion
Finance/Payment → Stripe, IBM
Travel/Lifestyle → Airbnb, Luxury
Entertainment → Spotify
Developer Tools → Linear, Supabase, IBM</code></pre>
            <p><span class="badge badge-primary">Note: Quick query only returns style recommendation. To generate Tailwind/CSS config, trigger full multi-agent workflow.</span></p>
        </div>
        <div class="footer">
            <p>Multi-Agent UI Styles | MIT License</p>
        </div>
    </div>
    <script>
        function switchLang(lang) {
            document.querySelectorAll('.content').forEach(el => {
                el.style.display = el.getAttribute('lang') === lang ? 'block' : 'none';
            });
            document.querySelectorAll('.lang-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            event.target.classList.add('active');
        }
    </script>
</body>
</html>