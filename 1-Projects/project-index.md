---
tags: [moc]
aliases: [project-index, Projects]
---

# project-index

> 🚀 当前活跃的项目

## 进行中

```dataview
TABLE status, date, tags
FROM "1-Projects"
WHERE contains(status, "active")
SORT date DESC
```

## 计划中

```dataview
TABLE status, date
FROM "1-Projects"
WHERE contains(status, "planning")
SORT date DESC
```

## 已完成

```dataview
TABLE date
FROM "1-Projects"
WHERE contains(status, "done")
SORT date DESC
```

---

[[home]] | [[4-Archives/archive-index|已归档项目]]
