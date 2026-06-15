---
name: geo-tracking
description: GEO归因追踪。设计后端GEO效果追踪方案，包括追踪计划制定、UTM参数方案设计、归因模型选择（首次/末次/多触点）、转化路径映射。区分国内追踪（百度统计/友盟）与国际追踪（GA4）。支持HTML/DOCX报告导出。
agent_created: true
version: "2.0"
metadata: {"openclaw": {"emoji": "🎯", "homepage": "https://github.com/a807866778/geo-skills"}}
triggers:
  - 归因追踪
  - 追踪方案
  - UTM
  - 归因模型
  - 转化追踪
  - 效果追踪
  - tracking
  - attribution
  - 流量来源
  - 数据埋点
  - 统计分析
  - GA4
  - 百度统计
---

# GEO Tracking - GEO归因追踪

## Skill Overview

GEO归因追踪引擎。为GEO优化项目设计完整的数据追踪与归因体系，从"AI平台看到品牌"到"用户最终转化"的每一步都可追踪、可度量、可归因。区分国内与国际两套追踪体系，适配不同的数据法规和分析平台。

## Core Capabilities

### 1. Tracking Plan Design

为每个GEO项目生成定制化追踪计划，明确"测什么"：

```yaml
tracking_plan:
  project: "新能源品牌GEO优化项目"
  tracking_period: "2026-Q3"
  
  key_metrics:
    awareness:
      - AI平台品牌提及次数
      - AI搜索结果品牌出现位置
      - 品牌曝光量（估算）
    engagement:
      - AI引用内容点击率
      - 落地页停留时间
      - 内容分享/收藏次数
    conversion:
      - AI渠道来源注册数
      - AI渠道来源购买转化
      - AI渠道来源线索量
    authority:
      - 品牌内容被AI引用频次
      - 引用来源权威度评分
      - 正面/负面引用比例
  
  data_collection_points:
    - AI平台搜索API（定期抓取）
    - 网站UTM参数（实时收集）
    - 百度统计/友盟/GGA4（事件上报）
    - CRM系统（转化回传）
    - 内容平台后台（阅读量/互动数据）
```

### 2. UTM Parameter Scheme

#### 标准UTM参数体系

```
https://brand.com/landing-page?
  utm_source={platform}&        # 流量来源平台
  utm_medium={medium}&          # 媒介类型
  utm_campaign={campaign}&      # 营销活动名称
  utm_content={content}&        # 内容标识
  utm_term={keyword}&           # 关键词
  utm_ai_platform={ai_platform}& # GEO扩展：来源AI平台
  utm_query={query_hash}&       # GEO扩展：AI搜索问题哈希
  utm_rank={rank_position}      # GEO扩展：引用排名位置
```

#### GEO专属UTM扩展

```yaml
GEO扩展参数:
  utm_ai_platform:
    取值: "wenxin" | "qianwen" | "doubao" | "kimi" | "yuanbao" | "chatgpt" | "gemini" | "perplexity"
    说明: 记录触发引用的AI平台
    
  utm_query:
    取值: 问题文本的MD5哈希前8位
    说明: 反向追溯产生转化的具体搜索问题
    
  utm_rank:
    取值: 1-10
    说明: 品牌在该问题下的引用排名位置
    
  utm_article_id:
    取值: 文章唯一ID
    说明: 追溯到产生引用的具体内容
```

#### UTM模板生成器

针对不同场景生成标准化的UTM模板：

**场景1: AI搜索引流**
```
utm_source=wenxin&utm_medium=ai_search&utm_campaign=2026q3_brand_geo
&utm_ai_platform=wenxin&utm_query=a1b2c3d4&utm_content=article_001
&utm_rank=2
```

**场景2: 内容平台引流**
```
utm_source=zhihu&utm_medium=social_content&utm_campaign=2026q3_brand_geo
&utm_content=article_001
```

**场景3: 广告协同**
```
utm_source=toutiao&utm_medium=cpc&utm_campaign=2026q3_brand_geo_ad
&utm_content=ad_001&utm_term=新能源车+推荐
```

### 3. Attribution Models

#### 三阶段归因模型

| 阶段 | 模型 | 适用场景 | 权重分配 |
|------|------|----------|----------|
| 初期 | First-Touch | 新品牌/新品推广 | 首次曝光100% |
| 中期 | Multi-Touch | 成熟品牌/长决策周期 | 首次30%/辅助30%/末次40% |
| 后期 | Last-Touch | 促销/临门一脚 | 最后触点100% |

#### Multi-Touch Attribution 详细权重

```
转化路径: 文心搜索(发现) → 知乎文章(了解) → 百家号(对比) → 小红书(决定) → 官网(购买)

权重分配:
  文心搜索: 30% (首次认知)
  知乎文章: 20% (深度了解)
  百家号:   10% (信息验证)
  小红书:   40% (最终决策)
  
归因结论: GEO流量贡献了100%的购买决策，其中AI搜索提供认知起点
```

#### 归因时间窗口

```yaml
attribution_window:
  first_touch: 30天  # 首次触达回溯窗口
  last_touch: 7天    # 末次触达回溯窗口
  multi_touch: 30天  # 多触点回溯窗口
  
  decay:
    model: exponential  # 指数衰减
    half_life: 14天     # 14天后权重减半
```

### 4. Domestic vs International Tracking

#### 国内追踪体系

| 组件 | 平台/工具 | 用途 |
|------|-----------|------|
| 网站分析 | 百度统计 | 全站流量分析、UTM解析 |
| APP分析 | 友盟+ | 移动端用户行为追踪 |
| 事件追踪 | 百度统计事件 | AI引用点击追踪 |
| AI监测 | 自建脚本 | 定期抓取AI平台引用数据 |
| CRM | 自建/第三方 | 转化回传与归因 |

**百度统计埋点示例:**
```javascript
// AI来源页面追踪
_hmt.push(['_trackPageview', '/landing/geo/wenxin']);
_hmt.push(['_trackEvent', 'geo_ai_referral', 'click', 'wenxin', 2]);
```

#### 国际追踪体系

| 组件 | 平台/工具 | 用途 |
|------|-----------|------|
| 网站分析 | Google Analytics 4 | 全站流量分析、UTM解析 |
| 事件追踪 | GA4 Events | AI引用点击追踪 |
| 用户ID | Google User-ID | 跨设备用户识别 |
| API传递 | Measurement Protocol | 服务端事件上报 |
| 隐私合规 | Consent Mode v2 | GDPR/CCPA合规 |

**GA4埋点示例:**
```javascript
// GA4事件追踪
gtag('event', 'geo_ai_referral', {
  'ai_platform': 'chatgpt',
  'query_topic': 'electric_vehicle_comparison',
  'citation_rank': 2,
  'article_id': 'article_001',
  'utm_campaign': '2026q3_brand_geo'
});
```

### 5. Conversion Path Mapping

```
用户旅程 → AI搜索 → 内容曝光 → 品牌认知 → 深度了解 → 决策比较 → 转化行动

映射追踪点:
  AI搜索   → utm_ai_platform / utm_query → AI引用事件
  内容曝光 → utm_source / landing_page → 页面访问事件
  品牌认知 → engagement_time → 深度浏览事件
  深度了解 → scroll_depth / pdf_download → 内容消费事件
  决策比较 → return_visit / compare → 回访/对比事件
  转化行动 → form_submit / purchase → 转化事件
```

全面转化路径追踪：

| 触点 | 追踪方式 | 归因标记 |
|------|----------|----------|
| AI平台触发 | UTM参数 | utm_ai_platform |
| 落地页浏览 | Session记录 | session_id |
| 内容消费 | 事件追踪 | content_consume |
| 线索表单 | 事件追踪 | lead_form |
| 购买转化 | 事件追踪 + CRM | purchase |
| 二次复购 | 用户ID关联 | user_id |

## Workflow

### Step 1: 需求分析
- 确认品牌追踪目标（品牌知名度 vs 直接转化）
- 确认目标市场（国内/海外/混合）
- 确认现有技术栈（网站平台、CRM系统）

### Step 2: 生成追踪方案
- 制定追踪指标体系
- 设计UTM参数方案
- 选择归因模型
- 输出技术实现指南

### Step 3: 输出埋点文档
- 网站埋点代码
- UTM链接生成模板
- 数据收集脚本配置

### Step 4: 归因分析框架
- 转化路径建模
- 归因权重计算逻辑
- 周期性归因报告模板

### Step 5: 导出报告
- HTML格式（美观、可交互）
- DOCX格式（正式汇报）

## Output Templates

### 追踪方案文档结构

```
1. Executive Summary
2. Tracking Objectives
3. KPI Framework
4. UTM Parameter Scheme
5. Attribution Model Selection
6. Technical Implementation Guide
   6.1 Domestic (百度统计/友盟)
   6.2 International (GA4)
7. Data Collection Schedule
8. Reporting Framework
9. Appendix: Tracking Code Snippets
```

### UTM Templates (可导出为CSV)

```csv
平台,UTM链接
微信公众号,https://brand.com/?utm_source=wechat&utm_medium=social_content&utm_campaign=geo_2026q3&utm_content=article_001
百家号,https://brand.com/?utm_source=baijiahao&utm_medium=seo_content&utm_campaign=geo_2026q3&utm_content=article_001&utm_ai_platform=wenxin
知乎,https://brand.com/?utm_source=zhihu&utm_medium=social_content&utm_campaign=geo_2026q3&utm_content=article_001
```

## Notes

- 国内追踪需注意《个人信息保护法》要求，用户数据脱敏处理
- 国际追踪需遵守GDPR/CCPA，实施Consent Mode
- AI平台引用数据存在延迟（通常1-7天），归因窗口需考虑此因素
- UTM参数命名规范：全小写、下划线分隔、避免中文
