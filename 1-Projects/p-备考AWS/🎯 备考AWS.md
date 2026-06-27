---
date: "2026-06-28"
tags: [project, aws]
status: active
aliases: [AWS, AWS认证, AWSCert]
deadline: ""
target_cert: SAA-C03 → SAP-C02
---

# ☁️ 备考 AWS 认证

## 目标认证路径

```
SAA-C03  (Solutions Architect Associate)   →  目标: 2-3 个月
    ↓
SAP-C02  (Solutions Architect Professional) → 目标: +3-4 个月
    ↓
(专项) Security / DevOps / Data Analytics / Networking
```

## 当前进度

| 认证 | 状态 | 学习进度 | 模拟考平均 |
|------|------|---------|-----------|
| SAA-C03 | ⏳ 未开始 | 0% | -- |
| SAP-C02 | ⏳ 未开始 | 0% | -- |

## 🔧 三工具闭环工作流

```
         ┌──────────────────────────┐
         │     Claude (中央枢纽)      │
         │    分析·整理·刷题·归档     │
         └──┬──────────────┬────────┘
            │ MCP          │ 文件读写
   ┌────────▼──┐      ┌───▼─────────┐
   │   飞书     │      │  Obsidian   │
   │  · 任务    │      │  · 知识库   │
   │  · 提醒    │      │  · 错题本   │
   │  · 进度表  │      │  · 架构图   │
   └───────────┘      └─────────────┘
```

### 推荐飞书记置
- **学习进度多维表格** — 按服务分类追踪完成度
- **每周学习任务** — 周一三五视频 + 周二四动手 + 周末刷题
- **考试倒计时提醒** — 注册考试后设置

## 📁 知识库导航

### 🏛️ 顶层框架
- [[p-备考AWS/Well-Architected框架|🏗️ Well-Architected 框架（5 支柱）]]
- [[p-备考AWS/架构模式|🏗️ 架构设计模式（HA/DR/缓存）]]

### 🔧 核心服务

| 类别 | 笔记 |
|------|------|
| **计算** | [[p-备考AWS/计算|🖥️ EC2 / Lambda / Auto Scaling / ELB]] |
| **存储** | [[p-备考AWS/存储|💾 S3 / EBS / EFS / Storage Gateway]] |
| **数据库** | [[p-备考AWS/数据库|🗄️ RDS / DynamoDB / Aurora / ElastiCache]] |
| **网络** | [[p-备考AWS/网络|🌐 VPC / Route 53 / CloudFront / Direct Connect]] |
| **安全** | [[p-备考AWS/安全|🔒 IAM / KMS / WAF / Shield / Cognito]] |
| **分析** | [[p-备考AWS/分析|📊 Athena / EMR / Kinesis / Redshift]] |
| **集成** | [[p-备考AWS/集成|🔗 SQS / SNS / Step Functions / API Gateway]] |
| **治理** | [[p-备考AWS/治理|📋 CloudWatch / CloudTrail / Config / Organizations]] |
| **迁移** | [[p-备考AWS/迁移|🚚 DMS / SMS / DataSync / Migration Hub]] |

### 📋 考试准备
- [[p-备考AWS/服务对比|🔄 易混淆服务对比]]
- [[p-备考AWS/错题本|❌ 错题本]]
- [[p-备考AWS/学习日志|📅 学习日志]]

---

*关联: [[三工具闭环工作流]] · [[🎯 雅思备考]] · [[🎯 备考PMP]]*
