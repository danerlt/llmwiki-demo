---
title: 来源摘要:用 Python 构建 RAG 应用
type: source
sources: [raw/03-rag-with-python.md]
updated: 2026-06-13
---

# 来源摘要:用 Python 构建 RAG 应用

## 核心论点

RAG 通过"检索外部知识 → 拼入 prompt → 受控生成"缓解幻觉、突破知识
截止(raw/03-rag-with-python.md §1)。

## 要点

- [[rag]] 五步流水线:切块 → [[embedding]] → 入向量库 → Top-K 检索
  → 生成(§2)
- Python 工具选择:sentence-transformers 做嵌入,[[langchain]] /
  LlamaIndex 做编排;小项目可用 [[numpy]] 直接算余弦相似度(§3)
- 评估:检索看 recall@k,生成看 faithfulness(§3)
- 陷阱:chunk 切坏语义、Top-K 取舍、纯向量对专有名词弱 → 混合检索(§4)
- 作者观点:**注入私有/常更新知识时 RAG 优于微调**(§5)
  → ⚠️ 与 raw/02 §5 矛盾,详见 [[rag]] 页面的 CONFLICT 块

## 关联

- [[rag]]、[[embedding]]、[[langchain]] 页面由本来源首建
- §4 的混合检索陷阱与本仓库 LLM Wiki 报告中 nashsu 实现的
  "分词 + 向量混合检索"互相印证
