# 用 Python 构建 RAG 应用

> 来源类型:实战教程笔记 · 收录日期:2026-06-13

## §1 什么是 RAG

检索增强生成(Retrieval-Augmented Generation):在调用 LLM 前,先从
外部知识库检索相关内容拼进 prompt,让模型基于"给定材料"作答,缓解
幻觉并突破训练数据的时间截止。

## §2 核心流水线

1. **加载与切块**:文档按 500~1000 token 切块(chunk),保留少量重叠
2. **向量化**:用 embedding 模型把每个 chunk 编码为稠密向量
3. **入库**:向量存入向量数据库(FAISS、Chroma、LanceDB 等)
4. **检索**:用户问题向量化后做相似度 Top-K 检索
5. **生成**:命中的 chunk 拼入 prompt,LLM 合成答案

## §3 Python 实现要点

- **embedding**:sentence-transformers 本地跑,或调用 API
- **编排框架**:LangChain / LlamaIndex 提供 loader、splitter、
  retriever 的标准组件;小项目也可以不用框架,直接 NumPy 算余弦
  相似度(几十行代码)
- **评估**:检索环节看 recall@k,生成环节看忠实度(faithfulness)

## §4 常见陷阱

- chunk 切坏语义边界 → 检索命中但上下文残缺
- Top-K 太小漏召回、太大引入噪声
- 纯向量检索对专有名词/编号弱 → 加关键词检索做混合(hybrid)

## §5 RAG 还是微调?

教程作者观点:**对于注入私有/常更新的知识,RAG 通常优于微调**——
成本低几个数量级、知识可即时更新、答案可溯源;微调更适合改变模型的
风格与输出格式,而非灌输事实。
