# GEO优化师技能包 v2.0

GEO（生成式引擎优化）端到端工作流技能包，19个标准化AgentSkills，覆盖品牌采集→全景诊断→问题挖掘→内容生产→页面优化→知识资产→平台分发→多平台发布→效果监测全链路。

基于 [Yao GEO Skills](https://github.com/yaojingang/yao-geo-skills) 架构和 [GEOFlow](https://github.com/yaojingang/GEOFlow) 系统设计，完全兼容 AgentSkills 规范。

## 技能清单

### 战略诊断（3个）
| 技能 | 功能 |
|------|------|
| geo-brand-intake | 15字段品牌资料采集，事实校验，合规检查 |
| geo-panorama-audit | GEO全景诊断，5大AI平台品牌可见性基线 |
| geo-execution-roadmap | 30/60/90天三阶段执行路线图 |

### 研究拓词（2个）
| 技能 | 功能 |
|------|------|
| geo-question-discovery | 7维度AI搜索高频问题挖掘，TOP10排名 |
| geo-intent-miner | 意图集群扩展，追问链，监测提示词库 |

### 内容生产（5个）
| 技能 | 功能 |
|------|------|
| geo-title-optimizer | 标题候选库生成，四维评分，5平台风格变体 |
| geo-explainer-builder | 科普型文章，七段式结构 |
| geo-comparison-builder | 品牌对比文章，七维对比表 |
| geo-ranking-builder | 榜单评测文章，透明方法论文 |
| geo-content-refiner | 旧文GEO改造，实体标签注入 |

### 页面技术（2个）
| 技能 | 功能 |
|------|------|
| geo-page-audit | 网页GEO可抓取性六维诊断 |
| geo-page-blueprint | GEO友好页面信息架构蓝图 |

### 知识资产（2个）
| 技能 | 功能 |
|------|------|
| geo-brand-graph | 品牌实体关系图谱，Mermaid+JSON-LD |
| geo-knowledge-base | 品牌知识库，事实卡，FAQ数据库 |

### 运营分发（2个）
| 技能 | 功能 |
|------|------|
| geo-platform-strategy | 87平台匹配策略，⭐优先级评分 |
| geo-publisher | L1-L4四级发布引擎，定时发布 |

### 效果监测（2个）
| 技能 | 功能 |
|------|------|
| geo-tracking | 归因追踪，UTM方案，转化路径映射 |
| geo-monitoring | 日/周/月三级监测，自动告警 |

### 编排（1个）
| 技能 | 功能 |
|------|------|
| geo-end-to-end | 19技能全流程编排器，模式A/B双入口 |

## 安装

**直接对 OpenClaw 说这句话即可自动安装**：

> 解压这个 zip 文件，把所有 geo- 开头的文件夹复制到 ~/.agents/skills/ 下面

如果 Agent 没有文件操作权限，手动执行：

```bash
# 下载并安装
unzip geo-skills-openclaw-v2.0.zip -d ~/.agents/skills/
```

安装后无需重启，在新对话中直接说自然语言即可使用。

## 快速开始

```bash
# OpenClaw 安装
git clone https://github.com/a807866778/geo-skills.git /tmp/geo-skills/
mv /tmp/geo-skills/skills/geo-* ~/.agents/skills/

# 在对话中启动
启动GEO端到端工作流
```

## 结构

```
geo-skills/
├── skills/          # 19个技能，每个一个目录
├── registry/        # 技能注册清单
├── shared/          # 共享数据（平台库，AI平台规则）
├── docs/            # 文档
├── README.md        # 本文件
└── USAGE.md         # 详细使用手册
```

## 版本

v2.0 — 2026年6月（参考Yao GEO Skills + GEOFlow架构重构）
