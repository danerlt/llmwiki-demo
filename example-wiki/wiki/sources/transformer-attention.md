---
title: 来源摘要:Transformer 与注意力机制入门
type: source
sources: [raw/02-transformer-attention.md]
updated: 2026-06-13
---

# 来源摘要:Transformer 与注意力机制入门

## 核心论点

Transformer 用纯注意力取代 RNN 循环,解决长程依赖与并行训练问题,
是 GPT/BERT/Llama 的共同基础(raw/02-transformer-attention.md §1)。

## 要点

- [[attention]]:QKV 三向量,权重 = softmax(QK^T/√d_k);多头并行
  捕捉不同维度的关系(§2)
- [[transformer]] 块 = 注意力 + FFN + 残差 + 层归一化,需位置编码
  补充顺序信息(§3)
- 实践:[[pytorch]] 内置 `nn.MultiheadAttention`;教学建议手写一遍
  scaled dot-product attention;Hugging Face transformers 提供预训练
  模型一行加载(§4)
- 作者观点:**微调是让模型掌握领域新知识的最佳方式**(§5)
  → ⚠️ 与 raw/03 §5 矛盾,详见 [[rag]] 页面的 CONFLICT 块

## 关联

- [[attention]]、[[transformer]] 概念页由本来源首建
- §4 充实了 [[pytorch]] 实体页的"生态"小节
