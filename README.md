---
date: "2026-07-12"
tags: [readme]
aliases: [README, 项目说明]
---

# 🧠 Obsidian 个人知识库

> Claude ↔ Obsidian ↔ 飞书 ↔ NotebookLM — AI 学习系统

一套以 **PARA** 方法组织、由 **Claude Code 经 MCP 直接读写**的个人学习知识库。
核心是一套「四工具协同学习系统」：Claude（思维/调度中枢）、飞书（执行系统）、
Obsidian（记忆系统）、NotebookLM（深度阅读系统）。

## 目录结构

```
├── .claude/               → Claude 元数据和桥接文档
│   ├── Claude 桥接说明.md
│   ├── Claude 对话索引.md
│   └── Claude 提示词库.md
├── .templates/             → 笔记模板
│   ├── t-笔记模板.md
│   ├── t-每日笔记模板.md
│   ├── t-项目笔记模板.md
│   ├── t-研究笔记模板.md
│   └── t-Claude对话模板.md
├── 0-Inbox/                → 快速捕获
│   ├── 收件箱.md
│   └── Claude-2026-06-16-搭建知识库.md
├── 1-Projects/             → 有 deadline 的事
│   ├── 项目索引.md
│   ├── p-雅思备考/         → 雅思备考（飞书 + Claude + Obsidian 闭环）
│   │   ├── 🎯 雅思备考.md
│   │   ├── 三工具协同工作流.md
│   │   ├── 三工具闭环工作流.md
│   │   ├── 错题本.md
│   │   ├── 模考记录.md
│   │   ├── 作文进化.md
│   │   └── 学习日志.md
│   ├── p-备考PMP/          → PMP 认证备考
│   │   ├── 🎯 备考PMP.md
│   │   ├── 12大原则.md / 49个过程矩阵.md / 8大绩效域.md
│   │   ├── 五大过程组（启动/规划/执行/监控/收尾）.md
│   │   ├── 十大知识领域（整合/范围/进度/成本/质量/资源/沟通/风险/采购/相关方）.md
│   │   ├── 敏捷与传统对比.md / 敏捷工具与技术.md
│   │   ├── 错题本.md / 学习日志.md
│   ├── p-备考AWS/          → AWS SAA → SAP 认证备考
│   │   ├── 🎯 备考AWS.md
│   │   ├── Well-Architected框架.md
│   │   ├── 计算/存储/网络/数据库/安全/治理/架构模式/集成/迁移/服务对比/分析.md
│   │   ├── 错题本.md / 学习日志.md
│   └── p-ai-agent/         → AI Agent 学习 + WorkBuddy 面试准备
│       ├── 🎯 AI Agent 学习.md       → 项目主页（status: active）
│       ├── 1-Learn-OpenClaw.md
│       ├── 2-AI-Knowledge-Hub.md
│       ├── 3-Git规范.md
│       ├── 4-Docker基础.md
│       ├── 5-AWS基础.md
│       └── WorkBuddy面试准备.md
├── 2-Areas/                → 持续关注
│   ├── 领域索引.md
│   ├── 面试反问问题清单.md
│   └── a-个人学习系统/
│       └── 🌱 个人学习系统.md
├── 3-Resources/            → 主题知识库
│   ├── 资源索引.md
│   ├── 学习方法/           → 完整方法论指南
│   │   ├── 🧠 AI学习操作系统.md
│   │   ├── 🚀 操作手册：快速上手.md
│   │   ├── 学习 SOP 每日执行清单.md
│   │   ├── 如何用四工具读透一本书.md
│   │   ├── 如何用四工具备考任何考试.md
│   │   ├── 如何用四工具学习一项新技能.md
│   │   ├── Claude技巧/Claude 高效学习完全指南.md
│   │   ├── Obsidian技巧/Obsidian 知识管理完全指南.md
│   │   ├── 飞书技巧/飞书 项目管理完全指南.md
│   │   └── NotebookLM技巧/NotebookLM 深度阅读完全指南.md
│   └── 雅思/
│       ├── 听力/听力 MOC.md
│       ├── 阅读/阅读 MOC.md
│       ├── 写作/写作 MOC.md
│       ├── 口语/口语 MOC.md
│       ├── 词汇/词汇 MOC.md
│       └── 语法/语法 MOC.md
├── 4-Archives/             → 已完成/暂停
│   └── 归档索引.md
├── 🏠 知库主页.md           → 总入口
├── 📊 知库总览.md           → Dataview 笔记总览视图
├── 🕒 最近更新.md           → Dataview 最近更新视图
└── 每日回顾.md
```

## 约定

- 项目笔记：`p-项目名.md`（位于 `1-Projects/p-项目名/`）
- 领域笔记：`a-领域名.md`（位于 `2-Areas/a-领域名/`）
- 资源笔记：位于 `3-Resources/主题/`
- 所有笔记统一 frontmatter：`date` / `tags` / `aliases`
- 重复笔记采用「单一信息源 + 重定向桩」方式去重

## Claude 集成

通过 `obsidian-local-rest-api` 插件，Claude Code 可直接读写本库。
已启用插件：`dataview`、`templater-obsidian`、`quickadd`、`calendar`。

> 说明：原 `.base` 视图已用 **Dataview** 重写为 `📊 知库总览.md` / `🕒 最近更新.md`，兼容 1.9 以下版本。

---

*最后更新: 2026-07-12*
