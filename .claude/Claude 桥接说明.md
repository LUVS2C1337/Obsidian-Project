---
tags: [claude, integration, setup]
aliases: [Claude桥接, 桥接说明]
---

# Claude 桥接说明

## 工作原理

```
┌─────────────────────┐         ┌──────────────────────────┐
│   Claude Code (D:\CC)│  ←───→  │  Obsidian Project        │
│   + 记忆系统         │  双向   │  (D:\Obsidian Project)   │
└─────────────────────┘         └──────────────────────────┘
```

**Claude 可以直接：**
- ✅ 读取 Obsidian 库中任何笔记
- ✅ 在库中创建、编辑笔记
- ✅ 搜索笔记内容
- ✅ 更新笔记的 frontmatter 元数据
- ✅ 维护 [[wikilinks]] 双向链接

## 约定

### Claude 操作目录

Claude 主要在以下位置创建/编辑文件：
- `0-Inbox/` — 来自对话的临时笔记、想法
- `.claude/` — Claude 元数据、索引文件
- `3-Resources/` — 研究结果、参考资料

用户主动整理到 `1-Projects/`、`2-Areas/` 等长期目录。

### 文件命名

- 项目笔记: `p-项目名.md`
- 领域笔记: `a-领域名.md`  
- 资源笔记: `r-主题名.md`
- 对话记录: `Claude-YYYY-MM-DD-话题.md`
- 每日笔记: `YYYY-MM-DD.md`

### Frontmatter 规范

Claude 写入的所有笔记必须包含：

```yaml
---
date: "YYYY-MM-DD"
tags: [tag1, tag2]
aliases: [别名1, 别名2]
---
```

## 命令约定

在 Claude 对话中说：

| 你说 | Claude 做 |
|------|----------|
| "保存到 Obsidian" | 将当前对话摘要写入 `0-Inbox/` |
| "记录这个想法" | 写入新笔记到 `0-Inbox/` |
| "查找关于 X 的笔记" | 搜索 Obsidian Vault |
| "创建项目 X" | 在 `1-Projects/` 创建项目笔记 |
| "更新资源 X" | 在 `3-Resources/` 更新资源笔记 |
| "归档项目 X" | 将项目移至 `4-Archives/` |

## 高级：Obsidian 侧连接

安装以下插件以获得最佳体验：
- **Templater** — 高级模板支持
- **Dataview** — 动态查询笔记
- **QuickAdd** — 快速捕获
- **Calendar** — 日历视图看每日笔记
- **Excalidraw** — 绘图

## Claude Code 内存系统

Claude 有自己的持久化内存（`~/.claude/projects/D--CC/memory/`），会记住：
- 你的偏好和习惯
- 项目上下文
- 重要决策

这部分是独立于 Obsidian 的，但 Claude 可以在两端同步关键信息。

---

*创建日期: 2026-06-16*
