# 最小化 LLM Wiki 示例(AI + Python 主题)

这是配套技术报告第 08 章「从零实现」的可运行示例:**零代码**,只有
一个文件夹、一份 Schema(`CLAUDE.md`)和一个 Agent。

## 这个示例演示了什么

| 模式要素 | 在哪里看 |
|---|---|
| 三层架构 | `CLAUDE.md`(Schema)/ `wiki/`(知识层)/ `raw/`(原始层,只读) |
| Ingest 摄入 | `wiki/sources/` 三个摘要页 + 被它们"摊开"更新的概念/实体页 |
| 知识交联 | 所有页面间的 `[[wikilink]]` 与 YAML frontmatter 的 `sources` 字段 |
| 矛盾标记 | `wiki/concepts/rag.md` 的 `⚠️ CONFLICT` 块(raw/02 与 raw/03 观点冲突,待人裁决) |
| 答案沉淀 | `wiki/synthesis/ai-python-learning-path.md`(由一次 query 的回答写回而来) |
| 可审计性 | `wiki/index.md`(目录 + 待办)与 `wiki/log.md`(操作流水账) |

## 怎么继续玩

在本目录下启动 Claude Code(或任意能读 `CLAUDE.md` 的 Agent):

```
# 摄入新资料:把文档丢进 raw/ 后
> ingest raw/04-你的新资料.md

# 查询(只读 wiki 作答,好答案会沉淀成新页面)
> query 手写一个最小 RAG 需要哪些步骤?

# 定期体检
> lint
```

也可以直接用 Obsidian 打开本目录浏览 wikilink 关系图。
