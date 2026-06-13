---
title: NumPy
type: entity
sources: [raw/01-python-ml-stack.md, raw/03-rag-with-python.md]
updated: 2026-06-13
---

# NumPy

Python 数值计算基座,提供 ndarray 与向量化运算,整个 AI 技术栈的地基
(raw/01-python-ml-stack.md §2)。

## 核心心智模型

**避免 Python 层 for 循环,用广播与向量化把计算下沉到 C 层**(§2)。
pandas、scikit-learn、[[pytorch]] 的接口设计都沿袭其 API 习惯。

## 在 LLM 应用中的角色

小规模 [[rag]] 场景可不依赖框架,直接用 NumPy 计算 [[embedding]]
余弦相似度,几十行代码即可(raw/03-rag-with-python.md §3)——
理解向量化后,RAG 检索环节并无黑魔法。

## 相关页面

[[pytorch]] · [[embedding]] · [[ai-python-learning-path]]
