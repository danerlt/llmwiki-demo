---
title: 注意力机制(Attention)
type: concept
sources: [raw/02-transformer-attention.md]
updated: 2026-06-13
---

# 注意力机制(Attention)

让序列中每个 token 直接"看到"所有其他 token 的机制,是 [[transformer]]
的核心组件(raw/02-transformer-attention.md §2)。

## 计算方式

每个 token 生成三个向量:

| 向量 | 含义 |
|---|---|
| Query | 我在找什么 |
| Key | 我能提供什么 |
| Value | 我的实际内容 |

注意力权重 = `softmax(QK^T / √d_k)`,再对 Value 加权求和。

**多头注意力**:并行多组 QKV 投影,同时捕捉语法、语义、位置等不同
维度的关系(§2)。

## 直觉类比

[[rag]] 的向量检索本质上也是"Query 与 Key 求相似度再取 Value",
可视为注意力思想在系统层面的放大——一个在权重内,一个在数据库里
(综合 raw/02 §2 与 raw/03 §2 的结构对照)。

## 相关页面

[[transformer]] · [[embedding]] · [[pytorch]]
