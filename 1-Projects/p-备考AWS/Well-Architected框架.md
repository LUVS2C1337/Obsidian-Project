---
date: "2026-06-28"
tags: [aws, well-architected, framework]
aliases: [Well-Architected, WA框架]
---

# 🏗️ Well-Architected 框架

> AWS 考试必考！5 大支柱，每个支柱的设计原则和关键问题要理解。

---

## 5 大支柱

| 支柱 | 关注点 | 核心问题 |
|------|--------|---------|
| **卓越运营 (O)** | 运行、监控、改进 | 如何运营？如何监控？如何优化？ |
| **安全 (S)** | 数据保护、权限、审计 | 如何保护？谁可以访问？如何审计？ |
| **可靠性 (R)** | 故障恢复、扩展 | 如何从故障恢复？如何扩展？ |
| **性能效率 (PE)** | 计算/存储/数据库/网络优化 | 如何选择合适的服务？如何优化？ |
| **成本优化 (CO)** | 省钱、匹配需求 | 如何花钱最聪明？如何避免浪费？ |

---

## 一、卓越运营

**设计原则：**
- 代码化操作 (Infrastructure as Code)
- 文档注释化
- 小而频繁的变更
- 频繁演练恢复流程
- 从故障中学习 (Post-mortem)

**关键 AWS 服务：** CloudFormation · CloudWatch · Config · SSM · X-Ray

## 二、安全

**设计原则：**
- 最小权限
- 强身份认证
- 安全处处 (所有层级)
- 数据分类 + 加密 (传输中/静态)
- 可追溯 (CloudTrail)

**关键 AWS 服务：** IAM · KMS · WAF · Shield · GuardDuty · Security Hub

## 三、可靠性

**设计原则：**
- 自动从故障恢复
- 测试恢复流程
- 水平扩展 (增加资源)
- 防止容量不足猜测
- 变更自动化管理

**关键 AWS 服务：** Auto Scaling · Route 53 · CloudWatch · RDS Multi-AZ · S3 跨区域复制

### ✅ 常见容灾策略 (DR)

| 策略 | RTO | RCO | 说明 |
|------|-----|-----|------|
| **备份+还原** | 高 | 低 | 从备份恢复，最便宜 |
| **暖备 (Pilot Light)** | 中 | 中 | 核心服务运行，灾难时扩展 |
| **双站点 (Standby)** | 低 | 高 | 备区全量运行被动等待 |
| **多站点 (Multi-site)** | 最低 | 最高 | 主动-主动，同时服务 |

**RTO = 恢复时间目标 · RPO = 恢复点目标**

## 四、性能效率

**设计原则：**
- 普及先进技术 (托管服务)
- 全球低延迟 (CloudFront 边缘)
- 无服务器架构
- 尝试新的实例/服务
- 异步 + 并发

**关键 AWS 服务：** Lambda · CloudFront · ElastiCache · DynamoDB · RDS 只读副本

## 五、成本优化

**设计原则：**
- 成本感知 (CloudWatch 成本分配标签)
- 按需付费，不要过度配置
- 衡量 ROI
- 使用托管服务 (降运维成本)
- 分析支出 (Cost Explorer)

**关键 AWS 服务：** Savings Plans · 预留实例 · Spot 实例 · Cost Explorer · 计算优化器

---

## 考试场景题应用

> **场景题思路：**
> 1. 问"最佳实践" → 优先选 Well-Architected 设计原则
> 2. 问"如何优化成本" → Cost Explorer + RI/Savings Plans + Spot
> 3. 问"如何提高可靠性" → 多 AZ + 自动故障切换 + 水平扩展
> 4. 问"如何加强安全" → IAM 最小权限 + 加密 + CloudTrail

---

*[[🎯 备考AWS|← 返回项目主页]]*
