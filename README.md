# LLM Wiki 技术报告

一份交互式 HTML 技术报告,从零讲清 **LLM Wiki** 这一知识管理模式:

- 概念定义与思想源头(Karpathy 的 Gist、1945 年的 Memex)
- 三层架构:Schema / Wiki / Raw Sources
- 三大核心操作:Ingest / Query / Lint(动画工作流图)
- 两个开源实现拆解:[nashsu/llm_wiki](https://github.com/nashsu/llm_wiki) 与 [lucasastorian/llmwiki](https://github.com/lucasastorian/llmwiki)
- 与传统 RAG 的本质区别(query-time vs write-time 计算)、优缺点与选型建议
- 零代码的最小可行实现指南(CLAUDE.md Schema 示例)

## 在线阅读

通过 GitHub Pages 自动部署:**https://danerlt.github.io/llmwiki-demo/**

> 首次启用:仓库 Settings → Pages → Source 选择 **GitHub Actions**(workflow 已尝试自动启用,如部署失败请手动设置一次)。

## 最小化示例

[`example-wiki/`](example-wiki/) 是一个零代码的最小 LLM Wiki 实例(AI + Python 主题):
3 份原始资料 + Schema(`CLAUDE.md`)+ LLM 维护的知识层(来源摘要、概念页、实体页、
综合页、index/log),并演示了 wikilink 交联、CONFLICT 矛盾标记与"答案沉淀为页面"。
详见 [example-wiki/README.md](example-wiki/README.md)。

## 本地预览

```bash
python3 -m http.server 8080
# 打开 http://localhost:8080
```

纯静态单文件(`index.html`),无任何构建步骤与外部依赖。

## 参考资料

1. [Andrej Karpathy — LLM Wiki Gist](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
2. [nashsu/llm_wiki](https://github.com/nashsu/llm_wiki) — Tauri 桌面端实现
3. [lucasastorian/llmwiki](https://github.com/lucasastorian/llmwiki) — MCP + FastAPI 实现
