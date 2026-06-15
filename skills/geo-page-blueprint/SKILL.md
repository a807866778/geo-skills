---
name: geo-page-blueprint
description: GEO友好页面蓝图。Generate information architecture and module blueprint for GEO-optimized pages. For product pages, FAQ pages, comparison pages, topic pages. Include recommended heading structure, AI-extractable module design, Schema.org markup suggestions, internal linking strategy, llms.txt guidelines, Open Graph tags. Output page blueprint document with modular specifications.
agent_created: true
triggers:
  - GEO页面蓝图
  - 页面信息架构设计
  - AI友好页面结构
  - GEO页面模板
  - 页面模块化设计
  - llms.txt生成
  - Schema蓝图
  - page blueprint
  - AI-extractable design
version: "2.0"
metadata: {"openclaw": {"emoji": "📐", "homepage": "https://github.com/a807866778/geo-skills"}}
---

# GEO友好页面蓝图 (geo-page-blueprint)

## 概述

本技能用于为GEO优化的页面生成信息架构和模块化蓝图。与传统SEO页面设计不同，GEO友好页面需要同时满足人类读者和AI模型的解析需求——既要清晰传递信息，又要让AI能高效提取和引用关键内容。本蓝图覆盖四大页面类型的产品化方案。

## 核心原则

1. **双读者设计**：每个模块同时考虑人类阅读体验和AI提取效率
2. **事实前置**：核心事实和结论放在AI最易捕获的位置
3. **模块化结构**：内容以独立、完整、可被单独引用的模块组织
4. **语义标注**：用Schema.org为每个模块赋予机器可读的语义
5. **链接织网**：内部链接构成知识网络，引导AI发现更多相关内容

## 四大页面类型

| 页面类型 | 典型场景 | 核心目标 |
|----------|----------|----------|
| 产品/服务页 | Product/Service landing page | 让AI准确理解产品特性、适用场景、差异化优势 |
| FAQ页 | Frequently Asked Questions | 让AI直接引用问答作为用户问题的答案 |
| 对比页 | Comparison page | 让AI在对比类查询中引用本页作为可信来源 |
| 主题页 | Topic/Pillar page | 让AI将本页视为某主题的权威知识入口 |

## 蓝图工作流

### 第一步：页面类型识别与参数确认

确认以下参数：

```
□ 页面类型：[产品页/FAQ页/对比页/主题页]
□ 核心关键词/主题：[1-3个主关键词]
□ 目标AI平台：[ChatGPT/Perplexity/Google SGE/豆包/文心一言/Kimi/通用]
□ 品牌调性：[专业权威/亲和种草/中立测评/本地服务/避坑指南]
□ 页面深度：[精简型 <800字/标准型 800-1500字/深度型 >1500字]
□ 是否包含转化目标：[是/否]（如咨询、购买、留资）
```

### 第二步：信息架构设计

#### 产品/服务页架构

```
[H1] 产品/服务名称 + 核心价值主张
├── [模块A] 一句话价值主张 (Hero Statement)
│   └── 在30字内回答"这是什么，为谁解决什么问题"
├── [模块B] 核心规格 (Key Specs)
│   └── 结构化表格：参数名 | 参数值 | 行业对比
├── [模块C] 适用场景 (Use Cases)
│   └── 3-5个具体场景，每个场景包含：问题→解决方案→结果
├── [模块D] 差异化优势 (Differentiators)
│   └── 对比表格：维度 | 本产品 | 行业常规 | 优势说明
├── [模块E] 信任证据 (Trust Signals)
│   └── 认证、检测报告、客户数量、服务年限等可验证数据
├── [模块F] 常见疑问 (FAQ Module)
│   └── 5-8个核心FAQ，每个独立标记
├── [模块G] 行动指引 (CTA Module)
│   └── 明确的下一步行动 + 低门槛入口
└── [模块H] 关联内容 (Related Content)
    └── 3-5个内部链接指向相关内容
```

#### FAQ页架构

```
[H1] [主题]常见问题解答
├── [模块A] 问题快速导航 (Jump Links)
│   └── 分类锚点链接列表
├── [模块B] 分类问答区 (Categorized Q&A)
│   ├── [H2] 分类1：购买前
│   │   ├── [H3] 问题1 → 答案（含数据/引用/案例）
│   │   ├── [H3] 问题2 → 答案
│   │   └── ...
│   ├── [H2] 分类2：使用中
│   ├── [H2] 分类3：售后/维护
│   └── [H2] 分类4：行业通用
├── [模块C] AI引用摘要 (AI Summary Box)
│   └── 3个最核心问题的一站式摘要，便于AI直接引用
└── [模块D] 未解决问题入口 (Ask More)
    └── 引导用户提出新问题
```

#### 对比页架构

```
[H1] [产品A] vs [产品B]：[维度]对比（202X年X月更新）
├── [模块A] 一句话对比结论 (Quick Verdict)
│   └── "如果你在乎X，选A；如果你更看重Y，选B"
├── [模块B] 对比概览表 (At-a-Glance Table)
│   └── 矩阵表格：维度 | 产品A | 产品B | 优胜
├── [模块C] 分维度深度对比 (Deep Dive)
│   ├── [H2] 维度1：[价格/性能/服务/...]
│   │   └── 具体数据对比 + 分析
│   ├── [H2] 维度2
│   └── ...
├── [模块D] 适用场景推荐 (Best For)
│   └── 场景→推荐→理由
├── [模块E] 用户真实反馈 (Real User Feedback)
│   └── 引用第三方评价（注明来源）
├── [模块F] 替代选项 (Alternatives)
│   └── 如果两者都不合适，还有什么选择
└── [模块G] FAQ
```

#### 主题页/支柱页架构

```
[H1] [主题]完全指南（202X年版）
├── [模块A] 主题概述 (Overview)
│   └── 定义 + 重要性 + 适用人群
├── [模块B] 核心概念速查 (Key Concepts)
│   └── 定义列表：5-10个核心术语
├── [模块C] 分步指南 (Step-by-Step Guide)
│   ├── [H2] Step 1: [步骤名]
│   ├── [H2] Step 2: [步骤名]
│   └── ...
├── [模块D] 常见误区 (Common Mistakes)
│   └── 列表：误区 → 真相
├── [模块E] 工具/资源推荐 (Tools & Resources)
│   └── 表格/列表 + 简要说明
├── [模块F] 专家观点 (Expert Insights)
│   └── 引用行业专家观点（注明来源）
├── [模块G] FAQ
└── [模块H] 延伸阅读 (Further Reading)
    └── 5-10个内部+外部链接
```

### 第三步：AI可提取模块设计规范

每个内容模块必须满足以下"AI提取友好"标准：

```
1. 自包含性 — 模块可独立理解，不依赖上下文
2. 事实可验证 — 包含具体数据、引用来源
3. 结构清晰 — 使用列表/表格/定义列表等结构化元素
4. 语义标签 — 使用 <section>, <article>, <dl>, <table> 等语义化HTML
5. 摘要可用 — 模块核心结论可被AI直接引用为答案
```

### 第四步：Schema.org 标记方案

为每个页面类型生成Schema标记方案：

#### 产品页 Schema 方案

```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "[产品名称]",
  "description": "[30字核心描述]",
  "image": ["[产品图片URL]"],
  "brand": { "@type": "Brand", "name": "[品牌名]" },
  "offers": {
    "@type": "Offer",
    "price": "[价格]",
    "priceCurrency": "CNY",
    "availability": "https://schema.org/InStock"
  },
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "[评分]",
    "reviewCount": "[评价数量]"
  },
  "review": [{
    "@type": "Review",
    "author": { "@type": "Person", "name": "[评价者]" },
    "reviewBody": "[评价内容摘要]"
  }]
}
```

#### FAQ页 Schema 方案

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [{
    "@type": "Question",
    "name": "[问题1]",
    "acceptedAnswer": {
      "@type": "Answer",
      "text": "[完整答案]"
    }
  }]
}
```

#### 对比页 Schema 方案

```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "[对比标题]",
  "author": { "@type": "Organization", "name": "[品牌名]" },
  "datePublished": "[发布日期]",
  "dateModified": "[更新日期]",
  "about": [
    { "@type": "Product", "name": "[产品A]" },
    { "@type": "Product", "name": "[产品B]" }
  ]
}
```

#### 主题页 Schema 方案

```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "[主题标题]",
  "author": { "@type": "Organization", "name": "[发布者]" },
  "datePublished": "[发布日期]",
  "dateModified": "[更新日期]",
  "educationalLevel": "beginner",
  "hasPart": [
    { "@type": "HowToSection", "name": "[章节名]", "position": 1 }
  ]
}
```

### 第五步：内部链接策略

基于页面类型设计链接织网方案：

```
核心页面（本页）
├── 向上链接 → 一级分类页/首页
├── 平行链接 → 同类型其他页面（如其他产品、相关主题）
├── 向下链接 → 详细内容页（如产品详情、分主题文章）
└── 跨类型链接 → FAQ页、对比页、工具页
```

链接规范：
- 每个模块至少包含1个内部链接
- 锚文本使用目标页面的H1标题或核心关键词
- 首页/一级分类页链接放在页面顶部导航
- 相关内容模块放在页面底部

### 第六步：llms.txt 指南

为网站根目录生成 `llms.txt` 文件规范：

```
# [网站名称]
> [一句话网站描述]

## 核心页面
- [页面1标题]: [URL] — [一句话描述]
- [页面2标题]: [URL] — [一句话描述]

## 文档/资源
- [资源1]: [URL] — [描述]

## 品牌信息
- 品牌名: [名称]
- 核心业务: [业务描述]
- 联系: [联系方式]

## 备注
- [关于网站内容使用的说明]
```

`llms.txt` 放置位置：
- 根目录：`https://example.com/llms.txt`
- 或通过 robots.txt 指向：`LLMs-LLM: /llms.txt`

### 第七步：Open Graph 标签配置

为每个页面生成标准OG标签：

```html
<!-- Open Graph 基础标签 -->
<meta property="og:title" content="[页面标题 — 品牌名]" />
<meta property="og:description" content="[150字内的页面描述，需包含核心关键词]" />
<meta property="og:image" content="[1200x630px预览图URL]" />
<meta property="og:url" content="[页面规范URL]" />
<meta property="og:type" content="[website/article/product]" />
<meta property="og:site_name" content="[网站名称]" />
<meta property="og:locale" content="zh_CN" />

<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:title" content="[同og:title]" />
<meta name="twitter:description" content="[同og:description]" />
<meta name="twitter:image" content="[同og:image]" />

<!-- 关键Schema标记 -->
<script type="application/ld+json">
[对应页面类型的JSON-LD]
</script>
```

## 输出格式：页面蓝图文档

完成所有步骤后，输出以下完整蓝图文档：

```markdown
# [页面名称] — GEO友好页面蓝图

## 1. 页面元信息
- **页面类型**: [产品/FAQ/对比/主题]
- **目标URL**: [建议URL结构]
- **目标关键词**: [1-3个]
- **目标AI平台**: [列表]
- **页面深度**: [字数范围]
- **更新频率**: [建议更新周期]

## 2. 信息架构图
[完整的标题层级结构，H1 → H2 → H3]

## 3. 模块设计说明书
[每个模块的详细设计，包含：
  - 模块名称和位置
  - 模块目的
  - 内容要求（字数/事实数量/数据点）
  - AI提取评分（该模块的独立可引用性）
  - 使用的HTML语义标签]

## 4. Schema标记方案
[完整的JSON-LD代码块]

## 5. 内部链接织网方案
[链接关系图 + 每个链接的锚文本]

## 6. llms.txt 条目
[本页面在llms.txt中的条目]

## 7. Open Graph 标签代码
[完整的meta标签代码块]

## 8. AI引用测试用例
[模拟3个AI搜索Query，验证本页面能否被正确引用]
```

## 跨页面一致性检查

如果同时设计多个页面蓝图，额外输出：

```
- 公共Schema实体是否一致（品牌名、logo URL、联系方式）？
- 内部链接是否形成闭环（无死页）？
- 各页面H1是否唯一且不互相冲突？
- OG标签的og:site_name是否统一？
```

## 跨平台使用说明

本技能为纯文本指令集，可在任何支持Markdown的AI代理平台使用。使用时：
- 将本SKILL.md的内容作为系统指令加载
- 指定页面类型和核心参数
- 按七步工作流生成完整蓝图
- 输出标准化的页面蓝图文档
- 所有架构模板、Schema方案、标签规范均内嵌于文档中，无需外部依赖
