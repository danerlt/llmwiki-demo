---
title: AI + Python 学习路径
type: synthesis
sources: [raw/01-python-ml-stack.md, raw/02-transformer-attention.md, raw/03-rag-with-python.md]
updated: 2026-06-13
---

# AI + Python 学习路径

> 本页由 query「从零开始学 AI 开发,Python 这条线该怎么走?」的回答
> 沉淀而来——这正是 LLM Wiki 模式中"答案写回知识库"的示例。

## 阶段一:打地基(经典技术栈)

1. **[[numpy]]** — 重点不是 API,是向量化思维(raw/01 §2)
2. **pandas** — 数据清洗与处理(raw/01 §5)
3. **scikit-learn** — 借统一的 `fit/predict` 学会建模流程与评估方法论(raw/01 §3)

> 依据 raw/01 §5:跳过这三步直接学深度学习,会在数据处理与实验评估上反复踩坑。

## 阶段二:深度学习与 LLM 原理

4. **[[pytorch]]** — Tensor / autograd / nn.Module / DataLoader 四大抽象(raw/01 §4)
5. **手写 [[attention]]** — 约 20 行 scaled dot-product attention 建立直觉(raw/02 §4)
6. **理解 [[transformer]]** — 块结构、位置编码、预训练范式(raw/02 §1~§3)

## 阶段三:LLM 应用工程

7. **手写最小 [[rag]]** — 用 sentence-transformers + [[numpy]] 余弦相似度,
   不用框架,几十行(raw/03 §3)
8. **再上 [[langchain]] / LlamaIndex** — 项目复杂后引入编排框架(raw/03 §3)
9. **学会评估与避坑** — recall@k、faithfulness、混合检索(raw/03 §3~§4)

## 未决问题

- 领域知识注入选 RAG 还是微调?两来源观点冲突,见 [[rag]] 页 CONFLICT 块
- 知识缺口(lint 发现):缺少关于「模型评估与实验管理」的专门来源,
  建议补充资料后扩展本页阶段二
