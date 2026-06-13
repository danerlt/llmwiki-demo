---
title: LangChain
type: entity
sources: [raw/03-rag-with-python.md]
updated: 2026-06-13
---

# LangChain

LLM 应用编排框架,为 [[rag]] 提供 loader、splitter、retriever 等标准
组件(raw/03-rag-with-python.md §3)。同类选择:LlamaIndex。

## 何时使用

- 多数据源、多步流水线、需要可替换组件时,框架收益明显
- 小项目可跳过框架:[[embedding]] + [[numpy]] 余弦相似度手写检索
  仅需几十行(§3)——先懂原理再上框架

## 相关页面

[[rag]] · [[embedding]] · [[numpy]]
