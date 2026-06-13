---
title: 来源摘要:Python 机器学习技术栈概览
type: source
sources: [raw/01-python-ml-stack.md]
updated: 2026-06-13
---

# 来源摘要:Python 机器学习技术栈概览

## 核心论点

Python 之于 AI 的价值在生态而非性能:计算下沉到 C/CUDA 层,Python 做胶水
(raw/01-python-ml-stack.md §1)。

## 要点

- [[numpy]] 是整个技术栈的地基,核心心智模型是**向量化优于 for 循环**(§2)
- scikit-learn 以 `fit / predict / transform` 统一 API 覆盖经典机器学习,
  不含深度学习(§3)
- [[pytorch]] 四大核心抽象:Tensor / autograd / nn.Module / DataLoader;
  动态图带来的调试体验是其胜出关键(§4)
- 推荐学习顺序:NumPy → pandas → scikit-learn → PyTorch,跳步者常在
  数据处理与评估上踩坑(§5)→ 已纳入 [[ai-python-learning-path]]

## 关联

- [[pytorch]] 的 Tensor 接口沿袭 [[numpy]] 习惯(§2、§4 交叉印证)
- 学习顺序建议是 [[ai-python-learning-path]] 的主要依据之一
