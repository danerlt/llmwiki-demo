---
title: Transformer
type: concept
sources: [raw/02-transformer-attention.md]
updated: 2026-06-13
---

# Transformer

2017 年《Attention Is All You Need》提出的序列建模架构,用 [[attention]]
取代 RNN 循环,从而获得**长程依赖建模能力**与**完全并行的训练**
(raw/02-transformer-attention.md §1)。GPT、BERT、Llama 均为其变体。

## 结构

一个 Transformer 块 = 多头 [[attention]] + 前馈网络(FFN),配残差连接
与层归一化,堆叠 N 层。注意力本身不感知顺序,需位置编码注入位置信息(§3)。

## 实践入口

- [[pytorch]] 内置 `nn.MultiheadAttention`、`nn.TransformerEncoderLayer`(§4)
- 教学建议:手写一遍 scaled dot-product attention(约 20 行)建立直觉(§4)
- Hugging Face transformers:`from_pretrained()` 加载数千预训练模型(§4)

## 相关页面

[[attention]] · [[pytorch]] · [[rag]](将 Transformer 模型用于知识问答的工程模式)
