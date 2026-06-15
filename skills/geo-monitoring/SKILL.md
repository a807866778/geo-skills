---
name: geo-monitoring
description: GEO效果监测。三级监测体系：日报（工作日8:30品牌可见性快检+异常告警）、周报（周一9:00趋势分析+内容健康度+竞品动态+环比对比）、月报（每月1号10:00深度复盘+趋势图+算法影响评估+信源权威审计+下月优化计划）。输出各频次标准化报告模板。
agent_created: true
version: "2.0"
metadata: {"openclaw": {"emoji": "📊", "homepage": "https://github.com/a807866778/geo-skills"}}
triggers:
  - 效果监测
  - 日报
  - 周报
  - 月报
  - 品牌监测
  - 数据监控
  - monitoring
  - 数据报告
  - brand monitoring
  - AI可见性
  - 品牌体检
  - 效果报告
  - 趋势分析
---

# GEO Monitoring - GEO效果监测

## Skill Overview

GEO效果监测引擎提供三层级递进式监测体系，从工作日快速品牌体检到月度深度战略复盘，覆盖5大AI平台的全链路数据监控。自动化提醒异常波动，输出标准化报告模板，支撑数据驱动的GEO策略优化。

## 3-Tier Monitoring System

### Tier 1: Daily Monitor (日报)

- **频率**: 工作日 8:30 AM (北京时间)
- **耗时**: ~5分钟自动执行
- **范围**: 5大AI平台快速品牌可见性校验
- **输出**: 日报简报（异常告警 + 核心指标速览）

#### Daily Check Items

```yaml
daily_check:
  platforms: [文心一言, 通义千问, 豆包, Kimi, 元宝]
  
  for_each_platform:
    - 品牌提及是否存在 ✓/✗
    - 引用排名变化（vs 昨日）
    - 是否有负面内容出现
    - 是否有竞争对手新内容上线
    
  alert_if:
    - 品牌提及消失: P0 - 立即通知
    - 排名下降≥3位: P1 - 上午前通知
    - 负面内容出现: P0 - 立即通知 + 内容链接
    - 竞品新内容上线: P2 - 日报中标注
    - 异常流量下降: P1 - 上午前通知
```

#### Daily Report Template

```yaml
# 日报模板
report:
  type: daily
  date: 2026-06-15
  status: normal | warning | alert
  
  summary:
    文心一言: "品牌在Top3结果中可见"
    通义千问: "品牌在Top5结果中可见"
    豆包: "品牌引用排名下降2位 ⚠️"
    Kimi: "正常"
    元宝: "新增1条正面引用 ✓"
    
  alerts:
    - platform: 豆包
      severity: P1
      detail: "引用排名从第2位下降到第4位，建议关注"
      action: "检查是否有竞品新内容上线"
      
  quick_metrics:
    overall_visibility: 85%
    day_over_day: -5%
    citation_count: 14
    positive_rate: 92%
```

### Tier 2: Weekly Monitor (周报)

- **频率**: 每周一 9:00 AM (北京时间)
- **耗时**: ~30分钟（含人工审核）
- **范围**: 30天趋势分析 + 内容健康度 + 竞品动态
- **输出**: 周报（趋势图 + 分析 + 下周建议）

#### Weekly Analysis Dimensions

**1. 30-Day Trend Analysis**
```
指标趋势:
- 品牌可见度评分30天趋势线
- AI引用次数变化曲线
- 引用排名分布变化
- 各AI平台独立趋势图（5条线叠加对比）
```

**2. Content Health Check**
```yaml
content_health:
  检查项:
    - 哪些文章正在被AI高频引用？(Top 10)
    - 哪些文章引用率正在下降？(危险列表)
    - 是否有内容被AI"遗忘"（连续14天无引用）？
    - 新发布内容的首周引用表现
    - 引用内容的时效性分布（7天内/30天内/90天+）
    
  健康度评分:
    ≥80: 健康 - 内容矩阵活跃且持续
    60-79: 亚健康 - 部分内容需要更新
    40-59: 预警 - 核心内容存在风险
    <40: 危险 - 品牌AI存在感严重不足
```

**3. Competitor Dynamics**
```yaml
competitor_analysis:
  监测竞品:
    - 竞品A: 本周新增3篇内容，引用率+12%
    - 竞品B: 1篇旧文被AI遗忘，引用率-8%
    - 竞品C: 发起新Campaign，多个平台同步出现
    
  竞争态势:
    weekly_share_of_voice:
      品牌: 35% (vs 上周 38%, -3%)
      竞品A: 28% (vs 上周 25%, +3%) ⚠️ 上升
      竞品B: 20% (vs 上周 22%, -2%)
      竞品C: 17% (vs 上周 15%, +2%)
```

**4. Week-over-Week Comparison**
```yaml
wow_comparison:
  visibility_score: 78 → 82 (+5.1%)
  citation_count: 45 → 52 (+15.6%)
  negative_ratio: 8% → 5% (-3pp ✓)
  new_content_published: 5 → 8
  content_cited_new: 2 → 4
```

#### Weekly Report Template

```markdown
# GEO周报 | 2026年第24周 (6.9 - 6.15)

## 执行摘要
本周品牌AI可见度评分82（+5.1%），整体表现良好。豆包平台出现小幅排名波动，已安排内容补强。

## 1. 多平台可见度概览
[5平台30天趋势对比图]

## 2. 内容健康度报告
- 健康度评分: 78（亚健康，需关注）
- Top 5 高引文文章
- 3篇内容进入"遗忘预警"

## 3. 竞品动态
[声量份额饼图]
竞品A本周加大发力，声量上升3pp至28%。建议下周针对性发布2篇对比评测。

## 4. 环比对比
[关键指标周环比对比表]

## 5. 下周行动建议
1. 更新3篇遗忘预警内容
2. 针对竞品A发布对比评测
3. 豆包平台特化优化
```

### Tier 3: Monthly Monitor (月报)

- **频率**: 每月1号 10:00 AM (北京时间)
- **耗时**: ~2小时（含深度分析和策略制定）
- **范围**: 全维度深度复盘
- **输出**: 月报（深度分析 + 策略建议 + 下月计划）

#### Monthly Deep Review Items

**1. Trend Charts (趋势图表)**
```yaml
monthly_trends:
  charts:
    - 品牌可见度月度趋势（含趋势线预测）
    - 各AI平台引用份额堆叠面积图
    - 内容发布 vs 引用率散点图
    - 正面/负面/中性引用比例变化
    - 竞品品牌声量多线对比图
    - 转化漏斗月度变化（AI曝光→点击→转化）
```

**2. Content Health Scorecard**
```yaml
content_health_scorecard:
  dimensions:
    freshness: 8.2/10        # 内容时效性
    comprehensiveness: 7.5/10 # 内容覆盖度
    authority: 8.8/10        # 来源权威性
    engagement: 7.0/10       # 用户互动度
    citation_rate: 8.5/10    # AI引用率
  
  overall_score: 8.0/10      # 综合健康度
  
  highlights:
    - 本月新增8篇内容，其中5篇获得AI引用
    - 3篇旧内容更新后引用率回升
    - "选购指南"类型内容表现最佳
  
  risks:
    - 2篇核心内容超过90天未更新
    - 竞品在"对比评测"维度内容量超过我方
    - 部分长尾关键词内容缺失
```

**3. Algorithm Change Impact Assessment**
```yaml
algorithm_assessment:
  detected_changes:
    - platform: 文心一言
      change: "6月初更新，对百家号权重提升"
      impact: 正面 (+8%引用率)
    - platform: 豆包
      change: "5月底调整，对短视频引用增加"
      impact: 中性 (对文字型内容略降)
    
  adaptation_strategy:
    - 增加百家号内容发布频次
    - 补充短视频格式的GEO内容（抖音/B站）
```

**4. Source Authority Audit**
```yaml
source_authority_audit:
  top_sources:
    - 百家号: 引用12次，权威评分 9.2
    - 知乎: 引用8次，权威评分 8.5
    - 微信公众号: 引用7次，权威评分 8.8
    - 什么值得买: 引用5次，权威评分 7.2
  
  new_sources_added: 3
  sources_lost: 1 (某地方门户被AI降权)
  
  建议:
    - 维护现有高权威来源
    - 拓展2-3个新权威来源
    - 弃用已降权来源
```

**5. Next Month Optimization Plan**
```yaml
next_month_plan:
  priority_actions:
    - action: "更新2篇即将进入'遗忘期'的核心内容"
      expected_impact: +5% 引用率
    - action: "发布4篇针对竞品A的对比内容"
      expected_impact: +3pp 声量份额
    - action: "在豆包生态（头条号）增加3篇内容"
      expected_impact: 豆包引用率 +10%
    
  content_calendar:
    week1: ["选购指南更新", "竞品对比-性能篇"]
    week2: ["行业趋势解读", "用户案例-方法论篇"]
    week3: ["技术科普-深度版", "竞品对比-价格篇"]
    week4: ["FAQ补全", "视频版内容制作"]
```

## Key Metrics (核心指标体系)

### Metric 1: Brand Visibility Score

```
品牌可见度评分 = Σ(平台权重 × 平台可见度分数)

权重分配:
  文心一言: 0.30
  通义千问: 0.25
  豆包: 0.25
  Kimi: 0.10
  元宝: 0.10

可见度分数计算:
  - Top1结果出现: 10分
  - Top3: 8分
  - Top5: 6分
  - Top10: 4分
  - 有出现但Top10外: 2分
  - 未出现: 0分

示例:
  文心(Top1)10×0.30 + 千问(Top3)8×0.25 + 豆包(Top5)6×0.25 + Kimi(Top10)4×0.10 + 元宝(Top5)6×0.10
  = 3.0 + 2.0 + 1.5 + 0.4 + 0.6 = 7.5/10 = 75分
```

### Metric 2: AI Citation Rate

```
AI引用率 = AI平台引用品牌内容的次数 / 行业问题总搜索量(估算)

细分:
  - 正面引用率
  - 负面引用率
  - 中性引用率
```

### Metric 3: Source Authority Rank

```
来源权威度 = f(平台权威度, 内容质量, 引用频次, 更新频率)
```

### Metric 4: Content Health Index

```
内容健康度 = f(时效性, 覆盖度, 引用率, 互动度, 权威性)
```

### Metric 5: Conversion Rate

```
转化率 = 来自AI引用的转化数 / AI引用带来的总访问量
```

## Workflow

### Step 1: 选择监测层级
- daily / weekly / monthly

### Step 2: 自动执行数据采集
- 调用各AI平台API/爬取品牌相关搜索结果
- 采集各内容平台数据
- 汇总到监测数据库

### Step 3: 数据分析和异常检测
- 计算核心指标
- 与历史数据对比
- 识别异常和趋势变化

### Step 4: 生成报告
- 填充对应模板
- 生成可视化图表
- 附上行动建议

### Step 5: 通知派发
- 根据告警级别自动通知相关负责人
- 邮件/企业微信/钉钉多渠道推送
- 存档报告供历史追溯

## Scheduled Automation

```yaml
scheduled_tasks:
  daily:
    cron: "30 8 * * 1-5"  # 工作日8:30
    action: daily_visibility_check
    output: daily_report
    
  weekly:
    cron: "0 9 * * 1"     # 每周一9:00
    action: weekly_trend_analysis
    output: weekly_report
    
  monthly:
    cron: "0 10 1 * *"    # 每月1号10:00
    action: monthly_deep_review
    output: monthly_report
```

## Alert Escalation Rules

| 级别 | 触发条件 | 通知方式 | 响应时间 |
|------|---------|----------|----------|
| P0 | 品牌提及消失/大面积负面 | 电话+即时消息 | 1小时内 |
| P1 | 排名下降≥3位/新负面内容 | 即时消息 | 4小时内 |
| P2 | 竞品异常活跃/小幅波动 | 日报标注 | 下个工作日 |
| P3 | 正常波动/改善趋势 | 周报汇总 | 常规周期 |

## Notes

- AI平台数据采集频率需控制在合理范围，避免触发反爬机制
- 核心指标的目标值需根据行业和品牌阶段动态调整
- 月度算法影响评估需结合AI平台官方更新公告
- 所有报告建议同时保存HTML（展示用）和JSON（数据分析用）格式
