---
name: geo-end-to-end
description: GEO端到端工作流编排器 v2.0。串联品牌采集→全景审计→执行路线图→问题挖掘+意图识别→标题优化→文章生成→页面蓝图→品牌图谱+知识库→平台策略→发布→追踪+监测的全流程。支持从任意阶段部分入口，支持模式A（品牌直推）和模式B（种子关键词切入）。包含首次运行引导信息和自动化调度任务。
agent_created: true
version: "2.0"
metadata: {"openclaw": {"emoji": "🔄", "homepage": "https://github.com/a807866778/geo-skills"}}
triggers:
  - 端到端
  - 全流程
  - GEO全流程
  - 一键GEO
  - 自动化GEO
  - end to end
  - full workflow
  - geo workflow
  - 完整方案
  - 全链路
  - 编排
  - orchestrator
  - 从零开始
  - 全套
  - geo orchestration
  - 工作流编排
---

# GEO End-to-End Orchestrator v2.0

## Skill Overview

GEO端到端编排器是全流程GEO优化项目的主控引擎，将18个Skill串联成完整的7阶段工作流。支持从任意阶段入口的灵活编排，以及模式A（品牌直推）和模式B（种子关键词切入）两种创作模式。内置自动化调度，可驱动日报、周报、月报的定时执行。

## Onboarding Message

首次调用时展示以下引导信息：

```
╔══════════════════════════════════════════════════════════════╗
║           GEO End-to-End Orchestrator v2.0                 ║
║              GEO端到端工作流编排器                          ║
╚══════════════════════════════════════════════════════════════╝

欢迎使用GEO全流程编排引擎！本引擎将引导你完成从品牌资料采集
到效果监测的完整GEO优化流程。

📋 7阶段流程概览：
┌────────────────────────────────────────────────────────────┐
│ Phase 1: 品牌准备                                         │
│   ├── brand-intake      品牌资料采集与事实校验             │
│   ├── panorama-audit    品牌AI全景审计                     │
│   └── execution-roadmap 执行路线图生成                     │
│                                                            │
│ Phase 2: 问题挖掘                                         │
│   ├── question-discovery  AI搜索高频问题挖掘              │
│   └── intent-miner       用户意图深层挖掘                 │
│                                                            │
│ Phase 3: 内容规划                                         │
│   └── title-optimizer    GEO标题优化器                    │
│                                                            │
│ Phase 4: 内容生产                                         │
│   ├── article-explainer  解读型文章生成                   │
│   ├── article-comparison 对比型文章生成                   │
│   ├── article-ranking    排行榜型文章生成                 │
│   └── article-refiner    文章精修优化                     │
│                                                            │
│ Phase 5: 品牌基建                                         │
│   ├── page-blueprint     AI搜索落地页架构                 │
│   ├── brand-graph        品牌知识图谱构建                 │
│   └── knowledge-base     品牌知识库搭建                   │
│                                                            │
│ Phase 6: 分发策略                                         │
│   ├── platform-strategy  内容分发平台策略                 │
│   └── publisher          多平台发布引擎                   │
│                                                            │
│ Phase 7: 效果追踪                                         │
│   ├── tracking           归因追踪设计                     │
│   └── monitoring         效果监测（日/周/月）             │
└────────────────────────────────────────────────────────────┘

🔄 两种创作模式：
  Mode A - 品牌直推: 从品牌资料出发，系统化建设品牌AI存在
  Mode B - 种子关键词: 从特定搜索意图出发，精准突破热点问题

💡 你可以：
  - 运行完整7阶段流程：     "开启完整GEO流程"
  - 从某个阶段开始：         "从Phase 3内容规划开始"
  - 指定创作模式：           "使用Mode B，从问题挖掘开始"
  - 查看阶段进度：           "查看当前GEO进度"
  - 跳过已完成阶段：         "跳过品牌准备，直接开始内容生产"

准备好了吗？请输入指令或选择阶段开始 👇
```

## Complete 7-Phase Workflow

### Phase 1: Brand Preparation (品牌准备)

```
┌──────────────────────────────────────────────────────────────────┐
│ Phase 1: 品牌准备                                                │
├──────────────────────────────────────────────────────────────────┤
│                                                                  │
│  Skill 1: brand-intake                                          │
│  ├── 采集品牌核心信息（产品、定位、受众、竞品）                  │
│  ├── 建立结构化品牌事实资料包                                    │
│  └── 强制执行事实边界和合规检查                                  │
│                                                                  │
│  Skill 2: panorama-audit                                        │
│  ├── 品牌在各AI平台当前可见度扫描                                │
│  ├── 竞争品牌AI存在度对比                                        │
│  ├── 品牌正面/负面引用比例分析                                   │
│  └── 生成品牌AI全景审计报告                                      │
│                                                                  │
│  Skill 3: execution-roadmap                                     │
│  ├── 基于审计结果制定执行路线图                                  │
│  ├── 优先级排序（紧急/重要/常规）                                │
│  ├── 资源需求估算（内容量、人力、预算）                          │
│  └── 里程碑和交付时间线                                          │
│                                                                  │
├──────────────────────────────────────────────────────────────────┤
│ 输出物:                                                          │
│  ✓ brand_facts.json        品牌事实资料包                        │
│  ✓ panorama_audit_report.md  AI全景审计报告                      │
│  ✓ execution_roadmap.md     执行路线图                           │
└──────────────────────────────────────────────────────────────────┘
```

### Phase 2: Question Discovery (问题挖掘)

```
┌──────────────────────────────────────────────────────────────────┐
│ Phase 2: 问题挖掘                                                │
├──────────────────────────────────────────────────────────────────┤
│                                                                  │
│  Skill 4: question-discovery                                    │
│  ├── 基于品牌事实从7个维度推导高频搜索问题                       │
│  ├── 标注搜索意图/目标AI平台/竞争难度/转化价值                   │
│  └── 输出TOP10问题排名                                           │
│                                                                  │
│  Skill 5: intent-miner                                          │
│  ├── 挖掘每个问题的深层用户意图                                  │
│  ├── 理解用户搜索背后的真实需求                                  │
│  ├── 分析意图阶段（认知/考虑/决策/售后）                         │
│  └── 输出意图-内容匹配建议                                       │
│                                                                  │
├──────────────────────────────────────────────────────────────────┤
│ 输出物:                                                          │
│  ✓ question_ranking.json  TOP10高频问题（含意图标签）            │
│  ✓ intent_analysis.json   意图分析报告                           │
└──────────────────────────────────────────────────────────────────┘
```

### Phase 3: Content Planning (内容规划)

```
┌──────────────────────────────────────────────────────────────────┐
│ Phase 3: 内容规划                                                │
├──────────────────────────────────────────────────────────────────┤
│                                                                  │
│  Skill 6: title-optimizer                                       │
│  ├── 基于目标问题生成GEO优化标题                                 │
│  ├── 多种标题策略（提问式/数据式/对比式/清单式）                 │
│  ├── SEO + AI友好（关键词覆盖 + 语义清晰）                       │
│  └── A/B测试建议                                                 │
│                                                                  │
├──────────────────────────────────────────────────────────────────┤
│ 输出物:                                                          │
│  ✓ title_options.json      每篇文章3-5个候选标题                 │
└──────────────────────────────────────────────────────────────────┘
```

### Phase 4: Content Production (内容生产)

```
┌──────────────────────────────────────────────────────────────────┐
│ Phase 4: 内容生产                                                │
├──────────────────────────────────────────────────────────────────┤
│                                                                  │
│  4种文章类型（按需选择）:                                         │
│                                                                  │
│  Skill 7: article-explainer    解读型（"XX是什么/怎么工作"）     │
│  Skill 8: article-comparison   对比型（"A vs B 详细对比"）       │
│  Skill 9: article-ranking      排行榜型（"2024年Top10推荐"）     │
│  Skill 10: article-refiner     精修型（优化已有文章到GEO标准）   │
│                                                                  │
│  每篇文章遵循七段式+五维转化结构:                                 │
│  七段式: 钩子→问题→背景→方案→证据→对比→CTA                       │
│  五维:   权威性/专业性/全面性/可信度/可行动性                     │
│                                                                  │
├──────────────────────────────────────────────────────────────────┤
│ 输出物:                                                          │
│  ✓ articles/*.md           每篇文章Markdown源文件                │
└──────────────────────────────────────────────────────────────────┘
```

### Phase 5: Brand Infrastructure (品牌基建)

```
┌──────────────────────────────────────────────────────────────────┐
│ Phase 5: 品牌基建                                                │
├──────────────────────────────────────────────────────────────────┤
│                                                                  │
│  Skill 11: page-blueprint                                       │
│  ├── 设计GEO优化的品牌落地页架构                                 │
│  ├── 结构化数据标记（Schema.org / JSON-LD）                      │
│  ├── AI可读性优化（语义化HTML、清晰信息层级）                    │
│  └── 移动端适配（AMP / 响应式）                                  │
│                                                                  │
│  Skill 12: brand-graph                                          │
│  ├── 构建品牌知识图谱（实体-属性-关系）                          │
│  ├── 品牌实体注册（百度百科/维基百科 / Wikidata）                │
│  └── 知识图谱与AI平台的对接策略                                 │
│                                                                  │
│  Skill 13: knowledge-base                                       │
│  ├── 建立品牌自有可引用知识库                                   │
│  ├── FAQ体系搭建（覆盖长尾问题）                                 │
│  ├── 数据资产整理（白皮书/报告/案例）                            │
│  └── 知识库与AI搜索的对接策略                                   │
│                                                                  │
├──────────────────────────────────────────────────────────────────┤
│ 输出物:                                                          │
│  ✓ page_blueprint.json     落地页架构方案                        │
│  ✓ brand_graph.json        品牌知识图谱                          │
│  ✓ knowledge_base/*.md     知识库文章                            │
└──────────────────────────────────────────────────────────────────┘
```

### Phase 6: Distribution Strategy (分发策略)

```
┌──────────────────────────────────────────────────────────────────┐
│ Phase 6: 分发策略                                                │
├──────────────────────────────────────────────────────────────────┤
│                                                                  │
│  Skill 14: platform-strategy                                    │
│  ├── 基于品牌行业/区域/内容类型匹配87平台数据库                  │
│  ├── 平台优先级评分（1-5星）                                    │
│  ├── AI平台生态偏好考量                                         │
│  └── 4周分发节奏排期                                             │
│                                                                  │
│  Skill 15: publisher                                            │
│  ├── L1直链 / L2剪贴板 / L3浏览器自动化 / L4 API直发            │
│  ├── 定时发布（"明天9点发微信公众号"）                           │
│  ├── 安全规则（发送前审核/默认草稿/30s间隔）                     │
│  └── 发布状态报告                                                │
│                                                                  │
├──────────────────────────────────────────────────────────────────┤
│ 输出物:                                                          │
│  ✓ platform_strategy.json   平台策略报告                         │
│  ✓ schedule.json            分发排期                             │
│  ✓ publish_report.json      发布状态报告                         │
└──────────────────────────────────────────────────────────────────┘
```

### Phase 7: Tracking & Monitoring (效果追踪)

```
┌──────────────────────────────────────────────────────────────────┐
│ Phase 7: 效果追踪                                                │
├──────────────────────────────────────────────────────────────────┤
│                                                                  │
│  Skill 16: tracking                                             │
│  ├── 追踪方案制定（测什么/怎么测）                               │
│  ├── UTM参数方案设计                                             │
│  ├── 归因模型选择（首次/末次/多触点）                            │
│  └── 国内（百度统计）vs 国际（GA4）双轨                         │
│                                                                  │
│  Skill 17: monitoring                                           │
│  ├── Tier 1: 日报（工作日8:30 品牌快检）                        │
│  ├── Tier 2: 周报（周一9:00 趋势分析+竞品）                     │
│  ├── Tier 3: 月报（每月1号10:00 深度复盘）                      │
│  └── 5大指标: 可见度/引用率/权威度/健康度/转化率                │
│                                                                  │
├──────────────────────────────────────────────────────────────────┤
│ 输出物:                                                          │
│  ✓ tracking_plan.json       追踪方案                             │
│  ✓ utm_templates.csv        UTM模板                              │
│  ✓ monitoring_config.json   监测配置                             │
└──────────────────────────────────────────────────────────────────┘
```

## Two Operating Modes

### Mode A: Brand Direct (品牌直推)

```
适用场景: 品牌知名度建设、新品牌AI存在建立、整体品牌形象优化

启动: "使用Mode A，开始完整GEO流程"

流程特点:
  Phase 1 (品牌准备) → 完整执行
    - 深度品牌资料采集
    - 全面AI全景审计
    - 制定长期执行路线图

  Phase 2 (问题挖掘) → 7维度推导
    - 从品牌定位出发
    - 系统性挖掘所有相关搜索问题
    - 构建问题矩阵

  Phase 3-7 → 全量执行
    - 系统化覆盖所有问题
    - 建立完整品牌知识体系
    - 长期持续优化
```

### Mode B: Seed Keyword (种子关键词切入)

```
适用场景: 热点抢夺、竞品对标、特定搜索意图精准突破

启动: "使用Mode B，种子关键词=新能源车续航焦虑，开始GEO流程"

流程特点:
  Phase 2 (问题挖掘) → 种子词发散 ← 入口点
    - 从1-N个种子关键词出发
    - 发散关联问题和长尾变体
    - 标记意图和竞争难度

  Phase 3 (内容规划) → 精准聚焦
    - 仅针对种子词相关问题生成标题
    - 快速产出策略

  Phase 4 (内容生产) → 精准打击
    - 围绕种子词创作高质量内容
    - 重点优化AI引用概率

  Phase 5 (品牌基建) → 按需补充
    - 仅补充种子词相关落地页
    - 最小化基建投入

  Phase 6 (分发策略) → 精准投放
    - 选择与种子词最相关的平台
    - 聚焦而非广撒网

  Phase 7 (效果追踪) → 聚焦监测
    - 仅追踪种子词相关表现
    - 快速迭代优化
```

## Workflow Execution

### Full Run

```
用户: "开始完整GEO流程，Mode A，品牌=极氪汽车"

编排器:
  1. [Phase 1] 启动 brand-intake → panorama-audit → execution-roadmap
  2. [Phase 2] 启动 question-discovery + intent-miner (并行)
  3. [Phase 3] 启动 title-optimizer
  4. [Phase 4] 启动 article-explainer/comparison/ranking (并行)
  5. [Phase 5] 启动 page-blueprint → brand-graph + knowledge-base (并行)
  6. [Phase 6] 启动 platform-strategy → publisher
  7. [Phase 7] 启动 tracking + monitoring (并行)
  
  [完成] 输出最终项目报告 + 所有产物归档
```

### Partial Entry

```
用户: "从Phase 4内容生产开始，我已经有品牌资料和问题列表了"

编排器:
  1. 验证前置依赖：
     ✓ brand_facts.json 存在
     ✓ question_ranking.json 存在
     ✗ intent_analysis.json 缺失
  
  2. 提示用户: "检测到缺少 intent_analysis.json，是否先运行 intent-miner？"
  
  3. 用户确认后: 先运行 intent-miner，再继续 Phase 4
```

### Dependency Check

编排器在每阶段启动前自动检查前置依赖：

```yaml
dependencies:
  Phase 2 (question-discovery):
    requires: [brand_facts.json]
    
  Phase 3 (title-optimizer):
    requires: [question_ranking.json]
    
  Phase 4 (article-generation):
    requires: [question_ranking.json, intent_analysis.json, title_options.json]
    
  Phase 5 (brand-graph):
    requires: [brand_facts.json]
    
  Phase 6 (platform-strategy):
    requires: [articles/*.md or content_manifest.json]
    
  Phase 7 (tracking):
    requires: [execution_roadmap.json]
    
  Phase 7 (monitoring):
    requires: [tracking_plan.json, utm_templates.csv]
```

## Scheduled Automation Tasks

### Task 1: Daily AI Platform Briefing

```yaml
task:
  name: "GEO Daily AI Briefing"
  schedule: "工作日 8:30 AM"
  cron: "30 8 * * 1-5"
  actions:
    - skill: geo-monitoring
      mode: daily
    - skill: geo-publisher
      mode: check_pending  # 检查待发布的定时任务
  output:
    channel: 企业微信/钉钉
    format: 简报卡片
```

### Task 2: Weekly Visibility Monitoring

```yaml
task:
  name: "GEO Weekly Monitoring"
  schedule: "每周一 9:00 AM"
  cron: "0 9 * * 1"
  actions:
    - skill: geo-monitoring
      mode: weekly
    - skill: geo-tracking
      mode: weekly_attribution  # 周度归因报告
  output:
    channel: 邮件 + 企业微信
    format: 完整周报
```

### Task 3: Monthly Deep Review

```yaml
task:
  name: "GEO Monthly Deep Review"
  schedule: "每月1号 10:00 AM"
  cron: "0 10 1 * *"
  actions:
    - skill: geo-monitoring
      mode: monthly
    - skill: geo-tracking
      mode: monthly_attribution
  pre_actions:
    - skill: panorama-audit  # 重新运行全景审计获取最新数据
  output:
    channel: 邮件 + 管理看板
    format: 完整月报 + 下月优化计划
```

### Task 4: Content Health Auto-Maintenance

```yaml
task:
  name: "Content Health Auto-Check"
  schedule: "每周三 14:00"
  cron: "0 14 * * 3"
  actions:
    - skill: geo-monitoring
      mode: content_health_only
    - alert_if: any_content_health < 60
    - suggest: article-refiner targets
```

## Full Skill Inventory

```yaml
geo_skills_registry:
  phase_1_brand:
    - geo-brand-intake
    # panorama-audit (pending)
    # execution-roadmap (pending)
    
  phase_2_discovery:
    - geo-question-discovery
    # intent-miner (pending)
    
  phase_3_planning:
    # title-optimizer (pending)
    
  phase_4_production:
    # article-explainer (pending)
    # article-comparison (pending)
    # article-ranking (pending)
    # article-refiner (pending)
    
  phase_5_infrastructure:
    # page-blueprint (pending)
    # brand-graph (pending)
    # knowledge-base (pending)
    
  phase_6_distribution:
    - geo-platform-strategy
    - geo-publisher
    
  phase_7_tracking:
    - geo-tracking
    - geo-monitoring
```

## Notes

- 编排器支持断点续跑：如果某阶段中途中断，可从断点继续而非重新开始
- Phase 2 中的 question-discovery 和 intent-miner 可并行执行
- Phase 4 中的4种文章类型可按需独立或批量执行
- Mode B 可以随时升级到 Mode A（补齐品牌准备阶段）
- 所有自动化任务的结果自动归档到 `reports/` 目录
- 编排器日志记录所有Skill调用和状态变更，便于调试和审计
