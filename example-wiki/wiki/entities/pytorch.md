---
title: PyTorch
type: entity
sources: [raw/01-python-ml-stack.md, raw/02-transformer-attention.md]
updated: 2026-06-13
---

# PyTorch

研究界与工业界主流的深度学习框架(raw/01-python-ml-stack.md §4)。

## 核心抽象

- `Tensor`:GPU 加速 + 自动微分的多维数组,接口沿袭 [[numpy]] 习惯
- `autograd`:动态计算图,自动反向传播
- `nn.Module`:模型组件化
- `DataLoader`:批量数据加载流水线

动态图(define-by-run)的调试体验是其赢得研究社区的关键(§4)。

## 生态(来自 raw/02 §4)

- 内置 `nn.MultiheadAttention`、`nn.TransformerEncoderLayer`,
  可直接搭建 [[transformer]]
- Hugging Face transformers 基于其上,提供海量预训练模型

## 相关页面

[[numpy]] · [[transformer]] · [[attention]] · [[ai-python-learning-path]]
