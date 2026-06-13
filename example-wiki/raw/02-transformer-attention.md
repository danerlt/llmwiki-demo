# Transformer 与注意力机制入门

> 来源类型:技术文章笔记 · 收录日期:2026-06-13

## §1 背景

2017 年论文《Attention Is All You Need》提出 Transformer 架构,用
纯注意力机制取代 RNN 的循环结构,解决了长程依赖与无法并行训练两大
痛点。GPT、BERT、Llama 等现代大模型都是 Transformer 的变体。

## §2 自注意力机制

自注意力(self-attention)让序列中每个 token 直接"看到"所有其他
token。每个 token 生成三个向量:Query(我在找什么)、Key(我能提供
什么)、Value(我的实际内容)。注意力权重 = softmax(QK^T / √d_k),
再加权求和 Value。

多头注意力(multi-head)并行运行多组 QKV 投影,让模型同时关注
语法、语义、位置等不同维度的关系。

## §3 整体架构

Transformer 块 = 多头注意力 + 前馈网络(FFN),配合残差连接与层归一化
堆叠 N 层。由于注意力本身不感知顺序,需要位置编码(positional
encoding)注入 token 的位置信息。

## §4 用 PyTorch 实现

PyTorch 提供 `nn.MultiheadAttention` 与 `nn.TransformerEncoderLayer`
开箱即用;教学场景建议手写一遍 scaled dot-product attention(约 20 行
代码)以建立直觉。Hugging Face 的 transformers 库则提供数千个预训练
模型,`from_pretrained()` 一行加载。

## §5 预训练与下游使用

大模型先在海量语料上预训练,再通过微调(fine-tuning)适配下游任务。
笔记作者观点:**想让模型掌握领域新知识,微调是最佳方式**——把知识
"烧"进权重,推理时无需外部依赖。
