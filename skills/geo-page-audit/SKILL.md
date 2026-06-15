---
name: geo-page-audit
description: GEO页面诊断器。Audit webpage for AI crawlability and extractability. Check robots.txt rules, sitemap presence, Schema markup quality, heading hierarchy (H1-H3), content signal strength (facts vs fluff), authority evidence (citations, certifications, external links), AI extractability (can AI parse key info from the page?). Output GEO page scorecard (0-100), prioritized fix list, before/after recommendations.
agent_created: true
triggers:
  - GEO页面诊断
  - 页面AI可爬取性检查
  - AI可提取性审计
  - Schema标记检查
  - 页面GEO评分
  - GEO页面审计
  - page audit
  - AI crawlability
version: "2.0"
metadata: {"openclaw": {"emoji": "🔬", "homepage": "https://github.com/a807866778/geo-skills"}}
---

# GEO页面诊断器 (geo-page-audit)

## 概述

本技能用于审计网页对AI搜索引擎（如ChatGPT、Perplexity、Google SGE、豆包、文心一言等）的可爬取性和可提取性。AI搜索引擎与传统搜索引擎对页面解析逻辑不同——它们更依赖结构化数据、清晰的层级关系和高密度的事实信息。本诊断器评估页面在AI时代的"可被引用性"。

## 核心原则

1. **AI视角优先**：以AI模型解析页面的视角进行审计，而非传统SEO爬虫视角
2. **事实密度 > 关键词密度**：AI更重视具体事实、数据和可验证信息，而非重复关键词
3. **结构化可解析**：Schema标记、标题层级、列表结构直接影响AI提取效率
4. **权威可溯源**：引用来源、认证标识、外部链接构成AI判断可信度的依据

## 诊断维度（6维评分体系）

每个维度满分100，按权重加权计算总分：

| 维度 | 权重 | 核心检查项 |
|------|------|-----------|
| 1. 可爬取性 (Crawlability) | 15% | robots.txt规则、sitemap、页面状态码、JavaScript渲染依赖 |
| 2. Schema标记质量 (Schema Quality) | 20% | JSON-LD结构、类型完整性、属性丰富度、字段准确性 |
| 3. 标题层级 (Heading Hierarchy) | 10% | H1唯一性、H1-H3层级逻辑、关键实体在标题中的分布 |
| 4. 内容信号强度 (Content Signal) | 25% | 事实密度vs填充内容、数据具体性、术语准确性、可操作信息量 |
| 5. 权威证据 (Authority Evidence) | 15% | 引用来源、认证资质、外部链接质量、机构背书 |
| 6. AI可提取性 (AI Extractability) | 15% | 关键信息定位效率、结构化程度、摘要友好度、实体标注 |

### 综合评分计算

```
总分 = Crawlability×0.15 + Schema×0.20 + Heading×0.10 + Content×0.25 + Authority×0.15 + AI Extract×0.15
```

### 等级映射

| 总分 | 等级 | 含义 |
|------|------|------|
| 90-100 | A+ | 卓越——AI极易引用，为典范页面 |
| 80-89 | A | 优秀——AI可高效提取，少量优化即可 |
| 70-79 | B | 良好——基本可被AI引用，存在改进空间 |
| 60-69 | C | 勉强及格——AI可能遗漏关键信息 |
| 40-59 | D | 较差——AI难以准确提取和引用 |
| 0-39 | F | 严重问题——AI几乎无法引用此页面 |

## 诊断工作流

### 第一步：获取页面数据

支持三种输入方式：

1. **URL输入**：`请诊断 https://example.com/product-page`
2. **HTML源码输入**：用户直接粘贴HTML
3. **浏览器截图+内容**：提供页面截图和文本内容

对于URL输入，执行以下抓取检查：
- 检查 `robots.txt`（如 `https://example.com/robots.txt`）
- 检查 `sitemap.xml`（如 `https://example.com/sitemap.xml`）
- 抓取页面HTML完整内容
- 提取并解析所有JSON-LD Script标签
- 记录HTTP响应状态码和渲染条件

### 第二步：六维诊断

#### 维度1：可爬取性 (Crawlability) 诊断清单

```
□ robots.txt是否存在？规则是否阻止AI爬虫？
  - 检查是否阻止常见AI Bot：GPTBot、CCBot、Anthropic-AI、Bytespider等
□ sitemap.xml是否存在且格式正确？
□ 页面HTTP状态码是否为200？
□ 页面是否为客户端渲染（CSR）？是否需要JS执行才能获取内容？
  - 检查 <noscript> 标签是否包含核心内容
  - 检查关键内容是否存在于HTML源码（非JS注入）
□ 页面加载速度（影响AI爬虫的超时风险）
□ 是否存在规范的 <link rel="canonical"> 标签？
```

#### 维度2：Schema标记质量 (Schema Quality) 诊断清单

```
□ 是否存在JSON-LD格式的Schema标记？
□ Schema类型是否正确匹配页面内容？
  - 产品页 → Product
  - 文章页 → Article / BlogPosting
  - FAQ页 → FAQPage
  - 本地商家 → LocalBusiness
  - 组织页 → Organization
□ Schema属性是否丰富？
  - 产品：name, description, image, sku, brand, offers, aggregateRating, review
  - 文章：headline, author, datePublished, dateModified, image, publisher
  - FAQ：mainEntity > Question > name + acceptedAnswer > text
□ 字段值是否准确、非空、非默认占位符？
□ 是否存在冗余或冲突的Schema标记？
□ 嵌套Schema是否正确（如 Product > Review > Rating）？
```

#### 维度3：标题层级 (Heading Hierarchy) 诊断清单

```
□ 页面是否只有一个 <h1>？
□ H1是否包含页面核心主题/目标关键词？
□ H1 → H2 → H3 层级是否逻辑递进（不跳级）？
□ H2是否有效划分了内容模块？
□ H3是否覆盖了足够的细节和长尾问题？
□ 关键实体/术语是否分布在各级标题中？
□ 标题中是否包含具体事实/数据（优于泛化标题）？
```

#### 维度4：内容信号强度 (Content Signal) 诊断清单

```
□ 事实密度检查：估算页面中可验证的事实陈述数量
  - 具体数字/统计（>5个 → 优秀）
  - 具体日期/时间线
  - 具体产品参数/规格
  - 具体价格/成本数据
  - 具体案例/场景描述
□ 填充内容检查：识别占位符、空洞口号、无信息量的套话
□ 术语准确性：专业术语使用是否正确且恰当？
□ 可操作信息量：用户读完能否获得明确的下一步行动指引？
□ 内容是否有明显的重复段落或堆砌关键词？
□ 内容是否回答了一个或多个明确的问题？
```

#### 维度5：权威证据 (Authority Evidence) 诊断清单

```
□ 是否有外部高质量链接的引用（.gov, .edu, 权威媒体）？
□ 是否展示了相关认证/资质/获奖记录？
□ 是否有可验证的第三方评价/评分？（非自评）
□ 是否标注了内容作者及作者资质？
□ 是否有明确的发布日期和最近更新日期？
□ 是否有引用来源标注（脚注/参考文献）？
□ 品牌/组织信息是否完整（名称、Logo、联系方式）？
```

#### 维度6：AI可提取性 (AI Extractability) 诊断清单

```
□ AI能否在无需渲染JS的情况下提取页面核心信息？
□ 页面核心问题是否能在首个视口（above the fold）找到？
□ 关键信息是否以结构化形式呈现（列表、表格、定义列表）？
□ 是否有清晰的摘要/要点区域可供AI直接引用？
□ 图片是否有准确的alt文本描述关键信息？
□ 页面是否使用了语义化HTML5标签（main, article, section, aside）？
□ 内容是否按"问题-答案"或"主张-证据"结构组织？
```

### 第三步：生成GEO页面评分卡

输出格式：

```markdown
## GEO页面评分卡

**诊断页面**: [URL]
**诊断日期**: YYYY-MM-DD
**综合评分**: XX/100 — [等级]

### 六维评分明细

| 维度 | 得分 | 权重 | 加权分 | 关键发现 |
|------|------|------|--------|----------|
| 可爬取性 | XX/100 | 15% | XX | [一句话关键发现] |
| Schema标记 | XX/100 | 20% | XX | [一句话关键发现] |
| 标题层级 | XX/100 | 10% | XX | [一句话关键发现] |
| 内容信号 | XX/100 | 25% | XX | [一句话关键发现] |
| 权威证据 | XX/100 | 15% | XX | [一句话关键发现] |
| AI可提取性 | XX/100 | 15% | XX | [一句话关键发现] |

### 优先修复清单（按优先级排序）

1. **[Critical]** [问题描述] → [修复建议]
2. **[High]** [问题描述] → [修复建议]
3. **[Medium]** [问题描述] → [修复建议]
4. **[Low]** [问题描述] → [修复建议]

### Before/After 对照

| 诊断项 | 当前状态 (Before) | 建议状态 (After) | 预期提升 |
|--------|-------------------|-------------------|----------|
| [诊断项] | [当前值/状态] | [建议值/状态] | +X分 |
```

## 诊断优化分级标准

### Critical（必须修复，影响AI爬取）

- robots.txt 阻止了AI爬虫
- 页面返回非200状态码
- 核心内容完全依赖JS渲染
- Schema标记缺失或类型错误

### High（强烈建议，显著影响AI引用质量）

- H1缺失或重复
- 关键Schema属性缺失
- 内容事实密度过低（可验证事实<3个）
- 无任何权威证据

### Medium（建议修复，提升AI引用完整性）

- 标题层级跳级
- Schema字段不完整
- 缺少规范canonical标签
- alt文本缺失或质量差

### Low（锦上添花，边际提升）

- Schema属性可进一步丰富
- 可增加更多数据点强化事实密度
- 可优化图片alt文本措辞

## 特殊场景处理

### 单页应用 (SPA) 诊断

- 额外检查服务端渲染(SSR)状态
- 检查预渲染/动态渲染方案
- 评估Google Search Console的渲染截图

### 多语言页面诊断

- 检查 hreflang 标签是否正确
- 检查各语言版本Schema是否独立且正确
- 评估内容本地化质量

### 电商产品页诊断

- 额外检查 Product Schema（价格、库存、评价）
- 检查变体(Variant)标记的完整性
- 检查商品图片的alt和结构化数据

## 批量诊断模式

支持批量URL诊断：

```
请诊断以下页面：
- https://example.com/product-1
- https://example.com/product-2
- https://example.com/faq
```

输出批量比较报告，包含：
- 各页面综合评分排名
- 共性问题汇总
- 按影响面排序的修复优先级

## 跨平台使用说明

本技能为纯文本指令集，可在任何支持Markdown的AI代理平台使用。使用时：
- 将本SKILL.md的内容作为系统指令加载
- 提供页面URL或HTML源码
- 按六维诊断体系逐项评估
- 输出标准化GEO评分卡和修复清单
- 所有规则和评分标准均内嵌于文档中，无需外部依赖
