---
title: RAG(检索增强生成)
type: concept
sources: [raw/03-rag-with-python.md, raw/02-transformer-attention.md]
updated: 2026-06-13
---

# RAG(检索增强生成)

调用 LLM 前先从外部知识库检索相关内容拼入 prompt,让模型基于给定材料
作答,缓解幻觉并突破训练数据时间截止(raw/03-rag-with-python.md §1)。

## 流水线

1. 文档切块(500~1000 token,留重叠)
2. [[embedding]] 向量化
3. 入向量库(FAISS / Chroma / LanceDB)
4. 问题向量化 → Top-K 相似度检索
5. 命中内容拼入 prompt → 生成(§2)

## 工程要点

- 编排:[[langchain]] / LlamaIndex;小项目可用 [[numpy]] 手写余弦相似度(§3)
- 评估:检索 recall@k,生成 faithfulness(§3)
- 陷阱:chunk 切坏语义边界、Top-K 取舍、纯向量对专有名词弱
  → 用关键词 + 向量混合检索(§4)

> ⚠️ CONFLICT — 知识注入:RAG 还是微调?
>
> - raw/02-transformer-attention.md §5 认为:**微调是让模型掌握领域
>   新知识的最佳方式**(知识进权重,推理无外部依赖)
> - raw/03-rag-with-python.md §5 认为:**注入私有/常更新知识时 RAG
>   通常优于微调**(成本低、可即时更新、可溯源);微调更适合改风格
>   而非灌输事实
>
> 两来源观点直接冲突,待人工裁决。倾向性参考:raw/03 给出了成本、
> 时效、溯源三条具体论据,raw/02 仅为结论性断言。

## 相关页面

[[embedding]] · [[langchain]] · [[transformer]] · [[ai-python-learning-path]]
