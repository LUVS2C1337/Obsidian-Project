# WorkBuddy 售后工程师 — 面试准备

## 岗位理解
AI 编程助手出问题 → 排查 / 修 / 转研发 → 写文档

## 你的匹配优势
- Agent / RAG / Tool Calling → 亲手写过
- Python ✅
- 日志排查 → 14 条 ERROR_LOG
- 云部署 → AWS + Docker
- 文档沉淀 → ERROR_LOG + DISASTER_RECOVERY

## 高频问题

### AI 基础类
- 大模型怎么调？传 messages, 拿 content/tool_calls, 支持流式
- Tool Calling？LLM 返回 tool_calls → 解析 → 执行 → 回传
- RAG？文档转向量 → 搜 TOP-K → LLM 基于资料回答
- Agent vs Chatbot？Agent = Chatbot + Tools

### 排查类（你最强的）
- 用户说 Bot 不回了？看日志 → 查网络/API Key/进程/配置
- 回答质量差？看 prompt → 上下文 → RAG 检索结果

### 技术基础
- 排查工具：curl, docker logs, ps aux, grep, tail -f
- 网络排查：curl → 状态码 → 安全组 → 代理

## 排查五步法
1. 看日志/复现
2. 缩小范围（网络? 配置? 代码? Bug?）
3. 定位根因
4. 给出方案
5. 写文档（沉淀到知识库）