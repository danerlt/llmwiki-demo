---
title: 向量嵌入(Embedding)
type: concept
sources: [raw/03-rag-with-python.md]
updated: 2026-06-13
---

# 向量嵌入(Embedding)

把文本编码为稠密向量,使"语义相似"可以用向量距离(余弦相似度等)
计算,是 [[rag]] 检索环节的基础(raw/03-rag-with-python.md §2~§3)。

## Python 实践

- 本地:sentence-transformers
- 或调用 embedding API
- 相似度计算本质是矩阵点积,小规模场景用 [[numpy]] 几十行即可实现(§3)

## 局限

纯向量检索对专有名词、编号类查询效果弱,工程上常与关键词检索组成
混合检索(§4)。

## 相关页面

[[rag]] · [[attention]](同为"相似度加权"思想)· [[numpy]]
