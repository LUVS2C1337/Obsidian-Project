---
date: "2026-07-09"
tags: [project, ai-agent]
aliases: [1-Learn-OpenClaw]
---

## 核心公式

- Workflow = Node + Node
- Chatbot = Workflow + Loop
- Agent = Chatbot + Tools = Workflow + Loop + Tools

## Node
- 最小处理单元，60 行代码
- exec(payload) → (action, new_payload)
- a >> b = 走默认路线
- a - "action" >> b = 走指定路线
- Flow 按 action 路由

## Tool Calling
1. LLM 返回 tool_calls
2. 解析 name + arguments
3. 执行工具
4. 结果放回 messages
5. 再调 LLM

## RAG
文档 → 切块 → Embedding → ChromaDB
问题 → 向量 → 搜 TOP-3 → LLM 基于资料回答

## Multi-Agent
Coordinator → CodeAgent + TraceAgent(并行) → ReviewAgent → Coordinator