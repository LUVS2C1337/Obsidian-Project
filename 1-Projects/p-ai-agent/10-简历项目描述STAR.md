# Learn-OpenClaw & AI Knowledge Hub — 简历项目描述（STAR法则）

> 用 STAR 法则（Situation-Task-Action-Result）写的简历项目描述。
> **人工润色版本**，尽量去掉 AI 腔。

---

## 项目一：Learn-OpenClaw

### 一句话简介

从零手写了一个 AI Agent 核心框架，不依赖 LangChain 等第三方库。

### STAR 描述

**Situation（背景）**
当时市面上的 Agent 框架（LangChain、CrewAI 等）封装层次太多，出了问题很难定位到根因。为了深入理解 Agent 底层原理，决定自己动手从零写一个。

**Task（任务）**
用纯 Python 实现一个可运行的 Agent 框架，核心代码控制在 500 行以内。需要完成 Node 编排、Tool Calling 循环、RAG 知识检索、Multi-Agent 并行协作这几个模块。同时要保证代码可测试、可部署。

**Action（行动）**
- 用 56 行代码实现了一个 Node + Flow 编排引擎。Node 通过 exec(payload) 返回 (action, new_payload)，Flow 根据 action 路由到下一个节点——这个模式和 LangGraph 底层原理一致，但自己写一遍才能理解。
- 手动实现了 Tool Calling 循环：LLM 返回 tool_calls → 解析参数 → 执行工具 → 结果回传 messages → 再次调用 LLM，直到 LLM 直接回复。
- 用 ChromaDB + Embedding API 搭了一套 RAG 流程：文档切块转向量 → 存库 → 查询时语义检索 TOP-K → LLM 基于资料回答。
- 设计了一个 Multi-Agent 团队：Coordinator 拆任务 → CodeAgent 和 TraceAgent 并行执行（ThreadPoolExecutor）→ ReviewAgent 审查 → Coordinator 汇总。
- 配了 38 个 pytest 单元测试、Docker 容器化部署。

**Result（结果）**
- 弄清楚了 Agent 的核心原理：它不是什么黑魔法，本质上就是一个编排系统。
- 项目放在 GitHub 上，带 README 架构图、英文文档和面试问答。
- 面试时可以拿这个项目讲清楚 Node/Flow/Tool Calling/Multi-Agent 的完整实现。

---

## 项目二：AI Knowledge Hub

### 一句话简介

基于 Agent 架构的飞书智能 Bot，打通飞书 IM 和 Obsidian 笔记库。

### STAR 描述

**Situation（背景）**
日常在飞书和 Obsidian 之间来回切换，查个资料要翻好几个地方。想着能不能做个 Bot，在飞书里发条消息就能同时查 Obsidian 笔记和飞书文档。

**Task（任务）**
搭一个三层架构的飞书 Bot：底层接 LLM，中间层做 Agent 编排，上层接飞书和 Obsidian。用户只需要在飞书群里发消息，Bot 自动判断查什么、调什么工具。还要部署到云服务器上 24 小时跑。

**Action（行动）**
- 三层架构：LLM 调用层（DeepSeek 异步客户端）→ Agent 编排层（Tool Calling 循环 + 工具注册）→ 连接器层（飞书 API + Obsidian API + MCP 客户端）。
- 用 lark-oapi 的 WebSocket 长连接接入飞书，用户@机器人发消息，Agent 自动调度工具。
- Obsidian 集成踩了个坑——中文文件名没做 URL 编码导致请求失败，加了一行 quote() 修好。
- 创建文档功能一开始走的 MCP 协议，发现需要用户授权太麻烦，改成了直接调飞书 Open API，用应用身份（tenant_access_token）搞定。
- 写了一个 ERROR_LOG.md 记录所有踩坑（14 条），一个 DISASTER_RECOVERY.md 做生产容错。
- 项目跑了 17 个测试，加了一个每 30 分钟打印一次的心跳日志用于监控。
- 部署在 AWS EC2 上（t3.micro），Docker 容器化，挂了会自动重启。

**Result（结果）**
- Bot 目前在 AWS 上跑了几个月，飞书群里发消息就能查笔记和文档。
- 面试时翻出手机打开飞书就能演示，比 PPT 管用。
- 构建 Agent 的经验踩出来的坑，后面排查类似问题基本一眼就能看出原因。

---

## 简历精简版（150字以内）

**Learn-OpenClaw**：从零手写 AI Agent 框架（~500 行 Python）。自研 Node+Flow 编排引擎、Tool Calling 循环、ChromaDB 实现 RAG、并行 Multi-Agent。配 38 个测试 + Docker 部署。

**AI Knowledge Hub**：基于 Agent 架构的飞书 Bot，集成 Obsidian 笔记与飞书 API。三层架构设计，WebSocket 长连接接入飞书，MCP 协议扩展。部署于 AWS EC2，Docker 容器化。面试可现场演示。

---

## 面试回答要点（STAR 版）

### "讲一下你的项目"

> "两个项目。第一个是自己手写了一个 Agent 框架，Node/Flow 只用了 56 行实现，Tool Calling、RAG、Multi-Agent 都做了——目的是真正理解 Agent 怎么工作的，而不是用别人的框架黑盒调。第二个基于这个理解做了个飞书 Bot，三层架构，接入了 Obsidian 和飞书 API，部署在 AWS 上，面试官您现在就可以发飞书消息试。"

### "遇到最大的坑是什么"

> "WebSocket 事件循环冲突。lark-oapi 的 on_message 在自己事件循环里跑，asyncio.run() 和 new_event_loop() 都会冲突。查了文档才发现要用 loop.create_task()。改了三版才跑通，这让我对 Python 异步编程的理解深了不少。"

### "你做过什么排查工作"

> "有 14 条 ERROR_LOG 记录。比如 Obsidian 中文文件名的问题——搜索一直返回空，笔记确实存在，最后发现是 httpx 没做 URL 编码，加了一行 quote() 搞定的。排查这事儿，我的步骤是先看日志确认现象，再缩小范围，最后定位根因修掉，修完写进文档。"
