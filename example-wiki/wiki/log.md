# 操作日志

- 2026-06-13 [init] 建立 Wiki:CLAUDE.md(schema)、purpose.md、目录骨架
- 2026-06-13 [ingest raw/01-python-ml-stack.md] 新建 sources/python-ml-stack,
  新建 entities/numpy、entities/pytorch;index 登记
- 2026-06-13 [ingest raw/02-transformer-attention.md] 新建
  sources/transformer-attention、concepts/transformer、concepts/attention;
  更新 entities/pytorch(补充 §4 生态);index 登记
- 2026-06-13 [ingest raw/03-rag-with-python.md] 新建 sources/rag-with-python、
  concepts/rag、concepts/embedding、entities/langchain;更新 entities/numpy
  (RAG 中的角色);**检测到矛盾**:raw/02 §5 与 raw/03 §5 在「知识注入选
  微调还是 RAG」上观点冲突 → 在 concepts/rag 标记 CONFLICT 待裁决;index 登记
- 2026-06-13 [query 学习路径] 回答「从零学 AI 开发的 Python 路线」,答案
  沉淀为 synthesis/ai-python-learning-path;index 登记
- 2026-06-13 [lint] 全库体检:0 死链 / 0 孤儿页 / 1 个未决 CONFLICT(rag 页)/
  1 个知识缺口(模型评估与实验管理,已记入 index 待办)
